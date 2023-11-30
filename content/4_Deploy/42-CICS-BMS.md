---
title: "CICS BMS Programs" # MODIFY THIS TITLE
chapter: true
weight: 42 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

##  Compile and Deploy CICS BMS programs
--------

#### Native Support to Maps


{{% notice info %}} 
:white_check_mark: :white_check_mark: **NO ACTION REQUIRED** This step is Informational only :heavy_exclamation_mark: 
{{% /notice %}}

OpenFrame provides native support for CICS/IMS-DC maps – BMS/MFS 

You need to compile using **OpenFrame map compiler utility** once source is copied to OpenFrame platform.

-------

#### Viewing the list of BMS programs

AWS CardDemo application BMS file are locate in `/opt2/tmaxapp/awsdemo/bms` 

:white_check_mark: Go to the directory by executing the `cd` command  

:white_check_mark: List the files with `ll` command

```sh
cd /opt2/tmaxapp/awsdemo/bms
ll
```

![PDS Gen](/images/Deploy-and-run/comp11.png)

--------

#### Compile the MAP Programs

For AWS CardDemo application **CICS Maps**, you have to run BMS compile script `all_map_comp.sh` present at directory – `/opt2/tmaxapp/awsdemo/compile`

:white_check_mark: Go to the directory by executing the `cd` command  

:white_check_mark: List the files `sh all_map_comp.sh` 


```bash
cd /opt2/tmaxapp/awsdemo/compile 
sh all_map_comp.sh
```

![PDS Gen](/images/Deploy-and-run/comp12.png)
####
![PDS Gen](/images/Deploy-and-run/comp13.png)

 


