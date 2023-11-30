---
title: "Application CICS and Catalog demo" # MODIFY THIS TITLE
chapter: true
weight: 53 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---
# Experience Online App
--------

## Login to the Application

:white_check_mark: Log in to the application

**User ID**     – `USER0001`  :key:

**Initially configured Password** – `PASSWORD` :key:

**:white_check_mark: Hit Enter**

This would help you access the back office functions

![User Functions](/images/run/login2.png)

After logging, this would take you to the application Main Menu as shown below :point_down:

![User Functions](/images/run/menu.png)

For this Demo, let us Test **01. Account View** functionality

:white_check_mark:Enter `01` as the Option in the Menu

:white_check_mark: Hit Enter

![User Functions](/images/run/menu1.png)


You should be able to see the Account View as given below :point_down:

![User Functions](/images/run/view.png)

:white_check_mark: Now let us **get an Account Number** from the Dataset which we migrated earlier.

As part of the Dataset Load process, we had already migrated the ACCTFILE Dataset ***AWS.M2.CARDDEMO ACCTDATA.PS***

Open the ***Tmax OpenFrame Manager*** browser Window

:white_check_mark: Click on **Base**

:white_check_mark: Click on **Datasets**

:white_check_mark: Select the **Dataset** `AWS.M2.CARDDEMO ACCTDATA.PS`

:white_check_mark: Click on **View/Edit**


{{% notice tip %}} 
:star: In case if you get any Errors (due to time out), Click on ***ROOT*** at the top right corner of the ***Tmax OpenFrame Manager*** browser Window;
**Logout** and then **Login** again :star:
{{% /notice %}}

![User Functions](/images/run/file.png)

:white_check_mark: In the File View Window, select the CopyBook 

Key in the Copy Book Name as `CVACT01Y`

```sh
CVACT01Y
```

:white_check_mark: Click on `Select`
![User Functions](/images/run/copy.png)

You would see the File getting displayed with the COPY BOOK layout

:white_check_mark: Pick up one of the Account Numbers to enter into the CICS Like Screen

:white_check_mark: Here in this example, the first account number is being picked.

![User Functions](/images/run/fileview.png)

:white_check_mark: Enter the Account number from the file into the Menu Screen

:point_right: Paste the account number

![User Functions](/images/run/acct.png)

:white_check_mark: Hit Enter after entering the account number

:point_right: You should be able to view the Account Details getting populated.

![User Functions](/images/run/data.png)

:white_check_mark: Hit PF3 in the Keypad to go back to the Main Menu

![User Functions](/images/run/pf3.png)



**:star: :star: Now you can play around various options in the Main Menu**

:point_down: Refer to the AWS Card Demo Application for more details

:white_check_mark: You may play around with various options as detailed in the documentation

https://github.com/aws-samples/aws-mainframe-modernization-carddemo


