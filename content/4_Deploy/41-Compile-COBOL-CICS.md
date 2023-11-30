---
title: "COBOL-CICS Programs" # MODIFY THIS TITLE
chapter: true
weight: 41 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

## Compile & Deploy COBOL-CICS programs

### :one: Native Compiler Support

{{% notice info %}} 
:white_check_mark: :white_check_mark: OpenFrame has its own compilers for all major languages.
**NO ACTION REQUIRED in this step**:heavy_exclamation_mark: 
{{% /notice %}}

:point_right: OpenFrame provides native support for Mainframe languages like COBOL, Assembler, PLI, Easytrieve etc. 

:point_right: **No need to make any change to source code**, just move source code to OpenFrame platform and recompile using OpenFrame compilers.

------

#### :two: Compile the Application

OpenFrame provide a compile utility **`cobcomp.sh`** to compile cobol application using **ofcobol** compiler.

>    For this workshop a Compile script **`cob_compile.sh`** is provided

>    The script is customized to compile and deploy all programs at required LOADLIB. 
> | Type                    | Library / Region           |
  | -------------           |:-------------| 
  |Batch programs	        | AWS.M2.CARDDEMO.LOADLIB|
  |Online programs	        | **OSCOIVP1**|

This script is present under directory `/opt2/tmaxapp/awsdemo/compile` at OpenFrame EC2 instance. 

**Follow the below instructions :point_down:**


:white_check_mark: Go to the directory by executing the `cd` command  

```sh
cd /opt2/tmaxapp/awsdemo/compile
```

{{% notice tip %}} 
You can type **cob_compile.sh** or **cobcomp.sh** at command line and hit enter and you will get help menu. 
You can compile **individual program or whole COBOL directory** at once.
{{% /notice %}}


:white_check_mark: Run the script without any path directory to have a glimpse of the functions


```sh
sh cob_compile.sh
```

![comp1 Gen](/images/Deploy-and-run/comp1.png)

**Compile and deploy the whole AWS CardDemo application source code** present in `/opt2/tmaxapp/awsdemo/cbl`

:white_check_mark: Run the script  

```sh
sh cob_compile.sh -md /opt2/tmaxapp/awsdemo/cbl
```

**:warning:** **This would take a few minutes** to compile all source code (1 to 2 mins). 

**:warning:** Wait for it to complete.

![PDS Gen](/images/Deploy-and-run/comp2.png)

---------

### :three: Validate the logs for any errors

> You can use the linux command `cat` to view the log files. 

> Ex: `cat log file name`

**Go to Compile Log directory and verify if any error or all compiled successfully.**

:point_right: In this case ALL programs compiled successfully and deployed. 

:point_right: If any error you will see a batch_error report and look at batch_log file for details.

:white_check_mark: Go to the directory by executing the `cd` command  

:white_check_mark: List the files with `ll` command


```sh
cd /opt2/tmaxapp/awsdemo/compile/Log
ll
```


![PDS Gen](/images/Deploy-and-run/comp3.png)

:white_check_mark: Use the `cat` command to view the logs 



