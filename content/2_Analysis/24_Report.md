---
title: "Analyze other assets" # MODIFY THIS TITLE
chapter: true
weight: 24 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---


# Analyze CSD and JCL Assets

## 1. CSD Analysis
Click on **CSD Files** in the left pane Menu

Select the check box for the CSD source List

Click on **Analyze** in the Analyze CSD file window

![User Functions](/images/Discovery/csd1.png)

Click CSD File Name

Click on Analyze
![User Functions](/images/Discovery/analcsd.png)

In the Pop-up **Are you sure you want to analyze the CSD files?**

Click **Yes**

![User Functions](/images/Discovery/close2.png)

Once the analysis is complete, you will see a pop-up with message **CSD files analysis is complete**

Click **ok**

![User Functions](/images/Discovery/close3.png)

Close the **Analyze CSD Files** window
#####
![User Functions](/images/Discovery/close1.png)

--------------------

## 2. JCL Analysis

Similar to COBOL Analysis, Perform the JCL analysis

1. In the Top Left section, under **Repository**, Click on **Jcl**
2. Select the JCL source PDS - Check box for `AWS.M2.CARDDEMO.JCL`
3. Select All the JCL's (By checking the Check box in the top Menu)
3. In the top Menu, click on **Analyze File**
4. Complete the Analysis

#####
![User Functions](/images/Discovery/jcl.png)

5. Click Analyze and proceed with Analysis 

![User Functions](/images/Discovery/jcl2.png)

----------------

## 3. Understanding reports from OFMiner

Similarly, once you complete analyzing assets like COBOL, JCL etc., 
1. Go to **Overview** tab again and refresh to see final outcome. 
2. If there are no missing or Syntax error for assets, AWS CardDemo application is **ready to deploy on OpenFrame**.

![User Functions](/images/Discovery/readydeploy.png)