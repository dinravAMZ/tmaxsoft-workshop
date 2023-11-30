---
title: "Import application source code"  
chapter: true
weight: 21  
---

<!-- MORE SUBMODULES CAN BE ADDED TO DIVIDE UP THE SETUP INTO SMALLER SECTIONS -->
<!-- COPY AND PASTE THIS SUBMODULE FILE, RENAME, AND CHANGE THE CONTENTS AS NECESSARY -->

# Import source

## Import application source code in OFMiner Repositories



#### 1. **Logging to the terminal** 

By now, you should be in the Linux Terminal of the EC2 instance as explained in the previous step in Introduction

[Getting into the Lab environment](/introduction/02-environment)

{{% notice note %}}
For this workshop, AWS CardDemo application source code is already downloaded under directory - `/opt2/tmaxapp/awsdemo/`
{{% /notice %}}

---------
#### 2. **Copy the contents of AWS Card Demo application source code to respective folders under OFMiner directory**

In order to accelerate the source code migration, a set-up script `1_ofminer.sh` is provided which automates source code copy for analysis.  
    
> From the pre-downloaded AWS card demo source code in directory  /opt2/tmaxapp/awsdemo/ 

> To the respective folders under OFMiner directory               /opt2/tmaxui/ofminer/repository 

#####
Execute the set-up script `1_ofminer.sh` located in the directory `/opt2/tmaxapp/awsdemo/setup`


```shell
sh /opt2/tmaxapp/awsdemo/setup/1_ofminer.sh
```

Paste the code in the Linux terminal and Hit Enter

![User Functions](/images/Discovery/exec.png)

---------

#### 3. **Component Mapping**

Components are mapped as shown below:

![Mapping](/images/Discovery/mapping.png)
