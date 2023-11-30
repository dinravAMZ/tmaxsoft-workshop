---
title: "Service Instances Provisioning"
weight: 45
chapter: true
draft: false
pre: "<b>D. </b>"
---

# Service Instances Provisioning

## Learning Objectives
In this Lab we will configure and launch service instances required in IBM Cloud pak for Data. This lab required below services to be configured additionally:
- Data Virtualization
- Cognos Analytics

## Prerequisites
- IBM Cloud Pak for Data
- Data Virtualization
- Cognos Analytics

## Lab Steps:

> ### Step 1: Login to IBM Cloud Pak for Data

> 1. Login to IBM Cloud Pak for Data with valid credentials

To perform this lab you need IBM Cloud Pak for Data's credential which include both username and password. If you do not have the credentials then refer previous lab exercise to get the credentials.

![](/images/00_getting_started/login.png)

> 2. Check if IBM Data Virtualization service is installed and provisioned

Follow the below steps to make sure IBM Data Virtualization service service is installed and provisioned in the provided IBM Cloud Pak for Data instance.

**Steps:**

1. Go to hamburger navigation menu and click on services and then click on services catalog to see all available services for this instance

![](/images/00_getting_started/dv_install_check.png)

2. Now in the search box type **Data Virtualization** to search Data Virtualization (DV) service and click on it.
![](/images/00_getting_started/service_catalog_dv.png)

3. Inside DV service you should be able to see that the service is enabled as shown in above picture. If it is not, ask the lab instructor and get data virtualisation service enabled.
![](/images/00_getting_started/dv_service_status.png)

4. Now click on **Instances** to verify if **Data Virtualization** service is already running.
![](/images/00_getting_started/dv_health.png)

**If in step 3 & 4 you could see Data Virtualization service is up and running then you DON'T have to follow below steps and you can skip to STEP-11.**

5. Follow only step 3 and 4 are failed. Go to hamburger navigation menu and click **Services** then **Instances**

![](/images/00_getting_started/lab0-1.png)

6. In the **Instances** page click **New Instance +** to configure and launch new service instance.
![](/images/00_getting_started/lab0-2.png)

7. Select **Data Virtualization** from list of services option
![](/images/00_getting_started/lab0-3.png)

8. Click **New Instance +** in the Data Virtualization page
![](/images/00_getting_started/lab0-4.png)

9. Click **Next**, **Continue**, and then **Next** in **Configure service** option.
![](/images/00_getting_started/lab0-5.png)
![](/images/00_getting_started/lab0-6.png)
![](/images/00_getting_started/lab0-7.png)

10. In the **Node storage** select **ocs-storage-cluster-ceph-rbd** storage class for both **Node** and **Caching** storage. and click **Next** and then **Configure** DV service.
![](/images/00_getting_started/lab0-8.png)
![](/images/00_getting_started/lab0-9.png)

Data Virtualization configuration may take upto 10-15 minutes, so you can start other lab exercise.

11. Click hamburger navigation menu and click on Services -> Instances to view all available instances.
![](/images/00_getting_started/service_instance.png)

12. Click on instance with type **db2oltp** and status running.
![](/images/00_getting_started/cognos_instance_1.png)

13. Note down the details such as hostname (ip address might varies in different installation), database name, port etc.
![](/images/00_getting_started/cognos_instance_2.png)

14. Click hamburger navigation menu and click **Data** -> **Platform connection**
![](/images/00_getting_started/cognos_instance_3.png)

15. Click **New connection +** and choose DB2 as connection type
![](/images/00_getting_started/cognos_instance_4.png)
![](/images/00_getting_started/cognos_instance_5.png)

16. Fill the connection details which you found from step 13.
![](/images/00_getting_started/cognos_instance_6.png)
![](/images/00_getting_started/cognos_instance_7.png)

17. Again click hamburger navigation menu and click on **Services** -> **Services catalog** to see all available services for this instance
![](/images/00_getting_started/dv_install_check.png)

18. Select and click on **Cognos Analytics** service
![](/images/00_getting_started/cognos_instance_10.png)

19. Click **New instance +**
![](/images/00_getting_started/cognos_instance_11.png)

20. Select **Shared Volume Storage** as shown in images and click Next
![](/images/00_getting_started/cognos_instance_12.png)

21. Select **Content Manager Database** and **Audit Database** which we created during **Platform connection**
![](/images/00_getting_started/cognos_instance_13.png)

22. Click **Next**
![](/images/00_getting_started/cognos_instance_14.png)

23. Click **Create**. Now you can perform other Labs/Steps until **Cognos Analytics** instance is ready
![](/images/00_getting_started/cognos_instance_15.png)
![](/images/00_getting_started/cognos_instance_16.png)
