---
title: "Analyze Source Code" # MODIFY THIS TITLE
chapter: true
weight: 23 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

## Analyze the AWS Card demo source code with OFMiner


#### 1. COBOL Analysis
Click **COBOL** assets under Repository menu

:white_check_mark: Check the COBOL Source check box

![User Functions](/images/Discovery/RepoMenu.png)

You can analyze the estate with one of the below options

> :a: Select checkbox at top to analyze all COBOL programs ***OR***

> :b: Can do specific COBOL programs by selecting corresponding checkbox. 
#####
:white_check_mark: For the lab, select **ALL** checkbox. 

:white_check_mark: Hit **Analyze File** button as highlighted.

![User Functions](/images/Discovery/Analyze.png)

:white_check_mark: From the next pop-up you can select copybook paths or leave as default and hit **Analyze**. 

:point_right: The asset verification process will start and you would be able to see the results.

![User Functions](/images/Discovery/AnalResult.png)

:white_check_mark: In the pop-up window, click **Yes** for the Question to Analyze the COBOL.

![User Functions](/images/Discovery/confirm.png)

:white_check_mark: During Analysis, it would like below.

![User Functions](/images/Discovery/anal.png)

:white_check_mark: Once analysis is done, click on **ok**.

![User Functions](/images/Discovery/complete.png)

:white_check_mark: Close the analyze COBOL popup

![User Functions](/images/Discovery/close.png)

Once analysis is done, you will see results as below.
#### Status 
- Green   – Analysis done and no issues found. **Fully compatible to OpenFrame.**
- Missing – **Missing element(s)**, for ex – Copybook, DCLGEN etc.
- Error   - Syntax or compatibility issue. **Needs some fix**

![User Functions](/images/Discovery/PostAnal.png)


