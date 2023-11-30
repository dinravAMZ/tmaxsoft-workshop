---
title: "Migrate Application data" # MODIFY THIS TITLE
chapter: true
weight: 33 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

## Migrate data sources - PS/VSAM/GDG
OpenFrame has like-for-like concept for PDS/PS/GDG/VSAM as in Mainframes. This ensures that no change is needed for JCL/PROC or programming languages. 
#### Data Set Migration Flow Chart


{{% notice info %}}
Below Flow chart explains how GDG,PDS,Copybook,VSAM can be migrated with utilities like dsmigin, pdsgen, cobgen utilities
{{% /notice %}}

![User Functions](/images/build-and-migrate/02-migrate-data/build.png)

#### Mainframe dataset migration process to OpenFrame follows below steps –
:one:	Migration target identification and source extraction

:two:	Mainframe dataset Transfer (FTP or other) in Binary format to OpenFrame EC2 instance

:three:	Data set layout analysis

:four:	Data set migration schema creation

:five:	Target data set migration

:six:   Data set migration verification

:seven: GDG BASE creation and VSAM migration

----------

### :one: Migration target identification and source extraction


> **:star: Best Practice: :star:** Before implementing a migration project, make a list of the data sets which needs to be migrated.Data set names must not be duplicated, an accurate list of **seed files / datasets** should be finalized in discussion with application SMEs during the discovery process.


{{% notice info %}} 
:white_check_mark: :white_check_mark: Sources are already identified; **No Action Required in this step :heavy_exclamation_mark:** 
{{% /notice %}}

For AWS CardDemo application, list of datasets to be migrated are given below [github link](https://github.com/aws-samples/aws-mainframe-modernization-carddemo)

![User Functions](/images/build-and-migrate/02-migrate-data/files.png)

----------

### :two: Mainframe dataset Transfer  

{{% notice info %}} 
:white_check_mark: :white_check_mark: For AWS CardDemo application - datasets are already extracted in EBCDIC format to OpenFrame; **No Action Required in this step :heavy_exclamation_mark:**
{{% /notice %}}

The source data sets should be extracted from the mainframe to OpenFrame EC2 instance. 

The data sets should be extracted in the **EBCDIC** format as-is in mainframes to avoid conversion errors (Like the conversion of special characters such as SOSI or 2-byte characters) 

Extract mainframe datasets via FTP or AWS Transfer family in **Binary format**

AWS CardDemo application datasets are already extracted in EBCDIC format to OpenFrame EC2 instance under folder - /opt2/tmaxapp/awsdemo/data

---------------

### :three: Data set layout analysis  

{{% notice info %}} 
:white_check_mark: :white_check_mark: For AWS CardDemo application - layouts/copybooks are already identified **No Action Required in this step:heavy_exclamation_mark:** 
{{% /notice %}}

Dataset analysis can be done by COBOL copybook or database schema. 

Copybooks corresponding to the file should be identified before the dataset migration process.

-----------

### :four: Data set migration schema creation
As a **one-time** process for dataset migrations, Mainframe copybooks must be converted into standard COBOL/PLI or other source language format. 

OpenFrame utility `cobgensch` will be used to create the data set migration schema file from a COBOL Copybook. 
> Languages like **PLI** have its own utility - `pligensch`
#####
:white_check_mark: Go to the directory where the aws card demo reside by executing command  

```shell
cd /opt2/tmaxapp/awsdemo/cpy
```

:white_check_mark: Run the command cobgensch to see the help menu of the utility  

```shell
cobgensch
```

![User Functions](/images/build-and-migrate/02-migrate-data/cobgen.png)

Let’s convert one copybook manually. 

:white_check_mark: To convert AWS card demo copybook `CVACT01Y`, run the command   

```shell
cobgensch CVACT01Y -d
```

**In the above command**
>    -d is for debugging message, helping you to understand how the utility read the copybook.

This execution generated a dataset conversion schema under folder `/opt/tmaxapp/OpenFrame/schema/CVACT01Y.conv`

![User Functions](/images/build-and-migrate/02-migrate-data/dsconv.png)

To generate the **OpenFrame migration schema file** for all AWS CardDemo application datasets

:white_check_mark: Go to the Set-up script directory by running the command  

```shell
cd /opt2/tmaxapp/awsdemo/setup
```

:white_check_mark: Run the script  

```shell
sh /opt2/tmaxapp/awsdemo/setup/3_cobgensch.sh
```
You would be able to see as shown below post the execution..

![User Functions](/images/build-and-migrate/02-migrate-data/mass.png)

--------

### :five: Target data set migration

For AWS Carddemo dataset conversion, the OpenFrame dsmigin tool require the **source dataset** and the OpenFrame **migration schema file** generated in the previous step.

Go to the set-up script folder location  

:white_check_mark: Run the Data set migration utility `dsmigin` to get the **Help Text**    


```shell
cd /opt2/tmaxapp/awsdemo/setup
dsmigin
```

![User Functions](/images/build-and-migrate/02-migrate-data/dsmig.png)

**Convert all the AWS CardDemo datasets** 

:white_check_mark: Run the Migration script `4_dsmigin.sh` and save the log file   

```shell
sh /opt2/tmaxapp/awsdemo/setup/4_dsmigin.sh > dsmigin.log
```

![User Functions](/images/build-and-migrate/02-migrate-data/dsmig2.png)

{{% notice info %}} 
Copying Source Assets can also be done Using OFManager (Browser based) which is covered later in this workshop
{{% /notice %}}

{{% notice tip %}} 
One example of **dsmigin** command for the AWS card demo dataset AWS.M2.CARDDEMO.ACCTDATA.PS using the copybook CVACT01Y. 
It has already been migrated by the script 4_dsmigin.sh.
**:heavy_exclamation_mark:The below given explanation for dsmigin is Informational only and NO ACTION REQUIRED**:heavy_exclamation_mark: 
{{% /notice %}}

    dsmigin [Source Dataset] [output OpenFrame catalog dataset] -s [migration schema file] [dsmigin Parameters]

    [Source Dataset]                   : /opt2/tmaxapp/awsdemo/data/EBCDIC/AWS.M2.CARDDEMO.ACCTDATA.PS
    [output OpenFrame catalog dataset] : AWS.M2.CARDDEMO.ACCTDATA.PS
    [migration schema file]            : /opt2/tmaxapp/OpenFrame/schema/CVACT01Y.conv
    [dsmigin Parameters]               : Any other parameters required

The command should be like:

    dsmigin /opt2/tmaxapp/awsdemo/data/EBCDIC/AWS.M2.CARDDEMO.ACCTDATA.PS AWS.M2.CARDDEMO.ACCTDATA.PS -s /opt2/tmaxapp/OpenFrame/schema/CVACT01Y.conv -f FB -D 2 -sosi 6

    The parameters passed are as below

    -f      : Dataset record format; If not passed, dsmigin utility will pick from copybook layout.

    -D      : Debugging option for validating any errors in dataset migration.

    -sosi   : Shift Out / Shift In delimiter 


**Validate the Log file**

:white_check_mark: Open Log file dsmigin.log by executing  

```shell
cat dsmigin.log
```
:white_check_mark: Scroll up and validate. Check if there are any errors.

> Validate the conversion error count is ZERO for all datasets migrated as shown below...


![User Functions](/images/build-and-migrate/02-migrate-data/log.png)
 
------------
### :six: Data set migration verification

OpenFrame `dslist` or `listcat` tool will be used to verify that the datasets have been successfully registered in the OpenFrame. 

File Catalog information is stored in an RDBMS acting as an index for better performance when running batch and transactions. 

:white_check_mark: execute the command to list the datasets  

```shell
dslist
```

![User Functions](/images/build-and-migrate/02-migrate-data/dslist.png)


:white_check_mark: Execute the command for catalog Listing

```shell
listcat -l AWS.M2.CARDDEMO.ACCTDATA.PS
```

![User Functions](/images/build-and-migrate/02-migrate-data/listcat.png)

:white_check_mark: Verify the registration
> View the data in the data sets using the `dsview`  

```shell
dsview AWS.M2.CARDDEMO.ACCTDATA.PS
```

:white_check_mark: Check the result 
![User Functions](/images/build-and-migrate/02-migrate-data/listv.png)

{{% notice note %}}
Alternatively, OFManager can be used for checking the result which will be covered later
{{% /notice %}}

**:white_check_mark: Quit the dsview panel without saving with below instructions**

> :white_check_mark: Hit `Esc` Key 

> :white_check_mark: Type `:q!` and hit Enter


--------------

#### :seven: VSAM Copy Book migration
For AWS Card Demo VSAM dataset migration, the VSAM copybooks must be at OpenFrame platform under folder – `/opt2/tmaxapp/OpenFrame/tsam/copybook`

> VSAM data migration will be done using the JCL, here in this step we are migrating the Copy Books for VSAM

Here is AWS CardDemo application datasets/copybook mapping.
####
![User Functions](/images/build-and-migrate/02-migrate-data/dsmap.png)
####
:white_check_mark: Run the script to copy AWS CardDemo application VSAM copybooks
 

```shell
sh /opt2/tmaxapp/awsdemo/setup/5_tsam.sh
```


{{% notice tip %}} 
OpenFrame VSAM data is stored at RDBMS underneath so can be exposed to enterprise distributed applications directly via JDBC/ODBC connections for data analytics or other business needs
{{% /notice %}}