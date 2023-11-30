---
title: "Run initial set-up jobs in AWS Card Demo Application" # MODIFY THIS TITLE
chapter: true
weight: 34 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Run initial setup jobs to prepare AWS CardDemo application data

AWS CardDemo application requires running a set of JCLs part of Initial setup after creating PDS, dataset migrations and moving assets to respective PDS, you did just now. 

The list of JCL's to execute are listed below:
| JCL Name          | Purpose           |
| -------------     |:-------------| 
|DUSRSECJ	        | Set-up user security vsam file|
|ACCTFILE	        | Load Account database using sample data|
|CARDFILE	        | Load Card database with credit card sample data|
|CUSTFILE	        | Create customer database|
|XREFFILE	        | Load Customer Card account cross reference to VSAM|
|TRANFILE	        | Copy initial Transaction file to VSAM|
|DISCGRP	        | Copy initial Disclosure Group file to VSAM|
|TCATBALF	        | Copy initial TCATBALF file to VSAM|
|TRANCATG	        | Copy initial transaction category file to VSAM|
|TRANTYPE	        | Copy initial transaction type file|
|DEFGDGB	        | Define GDG Base|



In this chapter, you will learn how to execute JCL using the web interface OFManager and by using the command line.

#### Login to OFManager 

:white_check_mark: Open OFManager console 

:point_right: Refer to [OpenFrame Console URLs](/introduction/03-OpenFrame-URL) section for fetching the OFManager URL

:point_right: Copy the URL Corresponding to **OFManager** in the output section

:point_right: Go to a Web browser (Google Chrome preferred) and Paste the URL 

**Default Login Credentials are given below** :point_down:

**User ID**     – `ROOT` 

**Password** – `SYS1` 


{{% notice info %}} 
This is the **RACF** equivalent ID which was migrated to OpenFrame **TACF**. Users can also login with their own TACF credentials
{{% /notice %}}

![User Functions](/images/build-and-migrate/04-run-initial-jobs/ofmanager.png)

:white_check_mark: Go to Batch menu option

![User Functions](/images/build-and-migrate/04-run-initial-jobs/batmenu.png)


:white_check_mark: Go to JCLs on left side menu

![User Functions](/images/build-and-migrate/04-run-initial-jobs/jcl.png)


:white_check_mark: You can either **select the JCL in the list (List View)** or type the **JCL name in the search box** and hit Enter or the Search button

Search for our first JCL to be executed :point_down:

`DUSRSECJ`


![User Functions](/images/build-and-migrate/04-run-initial-jobs/jclsearch.png)


Search results would be displayed as :point_down:

![User Functions](/images/build-and-migrate/04-run-initial-jobs/jclresult.png)


:white_check_mark: Click on JCL and hit Submit button. 

![User Functions](/images/build-and-migrate/04-run-initial-jobs/submit.png)


A job number would be displayed at bottom right corner once submitted. 

:white_check_mark: You can click on that to go directly to running job and see status or note down job number and see in Jobs menu in top left corner. 

![User Functions](/images/build-and-migrate/04-run-initial-jobs/jobrun.png)


:white_check_mark: If you missed the green pop up, you can still find your JCL execution under the Jobs menu on the left pan. The most recent JCL will be on the top of the list

![User Functions](/images/build-and-migrate/04-run-initial-jobs/postrun.png)


:white_check_mark: You can check job status if successfully done or error and view JCL messages similar to mainframe JCL to view output results. 

![User Functions](/images/build-and-migrate/04-run-initial-jobs/resultview.png)

**Until now, we have looked at the process for submitting JCL DUSRSECJ.** 


Submit ALL jobs mentioned below **in the same order** as shown above and ALL should be completed successfully to proceed further. 


{{% notice tip %}} 
Submitting Jobs can be done wither Individually OR in Batch mode
{{% /notice %}}

Submitting the Jobs could be done in **Two different ways**

:one: Iteratively submits each job listed below in the same order.

:two: Via a shell script for submitting all the jobs


{{% notice warning %}} 
**Follow one of the Options ONLY**
{{% /notice %}}


**Option :one:** 

Follow the instructions listed in Step 4 and 5 iteratively for each job in the same order. :arrows_counterclockwise: :arrows_counterclockwise:

---

**List of Jobs to be executed** 

1. `ACCTFILE`
2. `CARDFILE`
3. `CUSTFILE`	 
4. `XREFFILE`	 
5. `TRANFILE`	 
6. `DISCGRP`	 
7. `TCATBALF`	 
8. `TRANCATG`	 
9. `TRANTYPE`	 
10. `DEFGDGB`	 

**If you are following Option1, Skip option 2**

**Option :two:** 

Via a shell script for submitting all the jobs

**:warning:** **:warning:** **Execute this only if you have skipped Option1**

:white_check_mark: Execute the command 


```shell
sh /opt2/tmaxapp/awsdemo/setup/7_intialjclrun.sh
```

![User Functions](/images/build-and-migrate/04-run-initial-jobs/jclinit.png)

For both the Options, you can check the execution from OFMananager under JOBS menu:

![User Functions](/images/build-and-migrate/04-run-initial-jobs/ofmgrjes.png)