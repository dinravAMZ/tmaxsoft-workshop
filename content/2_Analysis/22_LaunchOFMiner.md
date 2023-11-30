---
title: "App. Analysis with OFMiner" # MODIFY THIS TITLE
chapter: true
weight: 22 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

## Launch OFMiner for analysis

#### 1. **Fetching the OFMiner URL**

Refer to [OpenFrame Console URLs](/introduction/03-OpenFrame-URL) section for fetching the OFManager URL
:white_check_mark: Copy the URL Corresponding to **OFMiner** in the output section

:white_check_mark: Go to a Web browser (Google Chrome preferred) and Paste the URL
:point_right: Your URL would look like: `http://xxx.xxx.xxx.xxx:8086/ofminer/` 
> In this case xxx.xxx.xxx.xxx is the AWS EC2 instance's **public IP**

**Alternatively, you may use the earlier fetched AWS EC2 instance public IP and login to OFMiner**

Refer to [Getting into the Lab environment](/introduction/02-environment) section for fetching the public IP


:white_check_mark: Go to a Web browser (Google Chrome preferred) and use address - `http://xxx.xxx.xxx.xxx:8086/ofminer/` 

> Replace `xxx.xxx.xxx.xxx` with the AWS EC2 instance **public IP** of the instance

-----------------

#### 2. **Login to the OFMiner Terminal**
:white_check_mark: Use Default credentials to login as given below 

**User      :**     `ROOT`  :key:

**Password  :**   `SYS1` :key:

![User Functions](/images/Discovery/OFMiner.png)

----------

#### 3. **After Logging in, it should display the preloaded content as shown below.**

![User Functions](/images/Discovery/OFMinerLogin.png)

----------

#### 4. **Perform JCL Sync**

:white_check_mark: Go to Repository (Top Left menu options) 

:point_right: Select asset class JCL

:point_right: Select asset folder you want to analyze 

:point_right: Click on Sync. 

![User Functions](/images/Discovery/Repo.png)

:white_check_mark: Sync will synchronize OFMiner repository folder uploads done in first step to OFMiner browser application. 

![User Functions](/images/Discovery/Sync.png)

:white_check_mark: Post Sync operation, it should look like

![User Functions](/images/Discovery/PostSync.png)

----------

#### 5. **Sync COBOL assets**
:white_check_mark: Go to Repository (Top Left menu options) 

:point_right: Select asset class COBOL

:point_right: Select asset folder you want to analyze 

:point_right: Click on Sync. 

![User Functions](/images/Discovery/cobol.png)

:white_check_mark: Sync will synchronize OFMiner repository folder uploads done in first step to OFMiner browser application. 

![User Functions](/images/Discovery/cblsync.png)

:white_check_mark: Post Sync operation, it should look like

![User Functions](/images/Discovery/cblpost.png)

----------

#### 6. **Assets Summary view**
:white_check_mark: Once all assets are synchronized, go to Overview at top left corner and you will see summary of assets synced but not analyzed yet.
![User Functions](/images/Discovery/AssetSummary.png)