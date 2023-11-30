---
title: "Create the AWS CardDemo application PDS Library" # MODIFY THIS TITLE
chapter: true
weight: 31 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

## Create the AWS CardDemo application PDS Library

#### 1. Build the PDS Structure for OpenFrame
AWS CardDemo application uses a mainframe like Partitioned Dataset (PDS) structure to store program load modules, control cards and PROCs. 

To avoid any change in JCL/PROC you will be required to build those required PDS at OpenFrame. 

#### :star:   3 PDS required for this process are:

| Library        | PDS           |
| -------------  |:-------------:| 
| Load           | AWS.M2.CARDDEMO.LOADLIB |
| Control Card   | AWS.M2.CARDDEMO.CNTL      |
| Proc           | AWS.M2.CARDDEMO.PROC      |



{{% notice tip %}}
**pdsgen Utility for Automation :**
`pdsgen` is an OpenFrame utility to create PDS at server (command) level. 
Pdsgen is used for mass migration during the actual project 
JCL and OFManager are used after the production migration (Business As Usual Process).
{{% /notice %}}

{{% notice note %}}
OpenFrame browser application OFManager can also be used to create datasets (PS, PDS, GDG, VSAM). This is covered later in this lab.
{{% /notice %}}

**Follow the below process**

---

:key: Login to OpenFrame EC2 server by clicking on the Connect button from the console

Refer to [Getting into the Lab environment](/introduction/02-environment) section to understand how to login to the Linux Terminal using the public IP


:information_source: Get into the help menu 

Go to the directory `cd /opt2/tmaxapp/` by executing the below command  

```shell
cd /opt2/tmaxapp/
```

**:white_check_mark:** Execute pdsgen command now at command line

```shell
pdsgen
```

**:white_check_mark:** Hit enter to see help menu.

![PDS Gen](/images/build-and-migrate/01-Build-application/pdsgen.png)

#### 2. Create the PDS

**:white_check_mark:** In order to create the PDS, execute the set-up script  


```shell
sh /opt2/tmaxapp/awsdemo/setup/2_pdsgen.sh
```

![PDS Gen](/images/build-and-migrate/01-Build-application/pds1.png)

