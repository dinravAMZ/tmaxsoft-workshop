---
title: "Copy AWS Card Demo Applications Dataset Library to Openframe" # MODIFY THIS TITLE
chapter: true
weight: 32 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

## Copy AWS Card Demo Applications Dataset Library to Openframe


{{% notice tip %}}
Copying Source Assets can also be done Using OFManager (Browser based) which is covered later in this workshop
{{% /notice %}}

#### 1. Copy Components

Run the script to copy the AWS Card Demo application components 

| Component      | new Openframe PDS directory              |
| -------------  |:-------------                            | 
| PROC           | AWS.M2.CARDDEMO.PROC                     |
| Control Card   | AWS.M2.CARDDEMO.CNTL                     |
| JCL            | SYS1.JCLLIB                              |


**:white_check_mark:** Execute the set-up script to copy   

```shell
sh /opt2/tmaxapp/awsdemo/setup/6_cpysource.sh
```

:information_source: You can use the linux `vi` command or `cat` command to look at the JCL. 

#### 2. View your JCL in the PDS directory 

If you want to view the JCL contents, follow the below step; 

Go to the JCL Library directory and view the `ACCTFILE` file using `cat` command in the terminal

```shell
cd /opt2/tmaxapp/OpenFrame/volume_DEFVOL/SYS1.JCLLIB/
cat ACCTFILE
```

You will be able to see the contents of the JCL with this.