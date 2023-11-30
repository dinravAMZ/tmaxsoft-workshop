---
title: "CICS region setup" # MODIFY THIS TITLE
chapter: true
weight: 35 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---


# AWS CardDemo application CICS region setup

#### **:one: Load the CICS system definition (CSD) in OpenFrame.**

In order to setup the CICS region, you have to load the AWS CardDemo application CICS system definition (CSD) in OpenFrame.

:white_check_mark: Get into the directory where the file is present at EC2 instance and list the files by executing commands 
	  

```shell
cd /opt2/tmaxapp/awsdemo/csd
ll
```

![User Functions](/images/build-and-migrate/05-cics-setup/csd5.png)

#### **:two: Load the AWS CARDDEMO CSD** into the current OpenFramce CICS region

:white_check_mark: Take a dump / copy of OpenFrame CICS region CSD file by executing the command below

```shell
oscsddump -r OSCOIVP1 oivp.dump
ll
```

![User Functions](/images/build-and-migrate/05-cics-setup/dump.png)

{{% notice tip %}}  
In above screenshot, **OSCOIVP1** is predefined OpenFrame CICS region 
{{% /notice %}}

#### **:three:** Copy the **AWS CardDemo application CSD** to **OpenFrame CICS region**  

:white_check_mark: Execute the command and hit enter


```shell
cat CARDDEMO.CSD >> oivp.dump
```
#####
![User Functions](/images/build-and-migrate/05-cics-setup/dump3.png)

#### **:four: Modify the CSD List** 

You have to add AWS CardDemo application CSD group `CARDDEMO` in CSD `LIST`

:white_check_mark: Open `oivp.dump` file in `vi` editor by executing the below command 

```shell
vi oivp.dump
```

:white_check_mark: Type `/` to get into SEARCH mode

:white_check_mark: search for `OIVPLIST`

```shell
OIVPLIST
```

Hit `ENTER` Key, and you will be able to locate the `OIVPLIST` in the file.


![User Functions](/images/build-and-migrate/05-cics-setup/search.png)

**Move the cursor** to the end of line of `ADD GROUP(PIVP) LIST(OIVPLIST)`
#####
:white_check_mark: Enter into **Insert Mode** on the line where it is high lighted by

:white_check_mark: Type **`I`** to enter into Insert mode

:white_check_mark: Now hit **Enter** to Insert a Blank line. 

:white_check_mark: You would be able to see a blank line.

![User Functions](/images/build-and-migrate/05-cics-setup/insert.png)
#####

#### **:five: Add AWS CardDemo application CSD group `CARDDEMO` in `CSD LIST`**

:white_check_mark: Add CARDDEMO Group in the blank line with below statement

```shell
ADD GROUP(CARDDEMO) LIST(OIVPLIST)
```

**come out of the edit mode.** 

:white_check_mark: Type **Esc** Key

:white_check_mark: Save the file by issuing the Write and Quit command `:wq`

#####
![User Functions](/images/build-and-migrate/05-cics-setup/save.png)
#####

#### **:six: Reload the file into Openframe CICS Region configuration file**
:white_check_mark: Run the Openframe CICS System definition Generator with oscsdgen command given below
	
```shell
oscsdgen -c -r OSCOIVP1 oivp.dump
```
#####
![User Functions](/images/build-and-migrate/05-cics-setup/sysdef.png)
#####

#### **:seven: CICS Set-up is complete!!**
