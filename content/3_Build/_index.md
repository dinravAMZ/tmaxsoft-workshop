---
title: "3. Build and Migrate" # MODIFY THIS TITLE IF APPLICABLE
chapter: true
weight: 30
---

# Build and Migrate :

Until now, you have analyzed the AWS CardDemo mainframe application workload. 

In this chapter, you will
-	Generate the AWS CardDemo application dataset
-	Migrate the AWS CardDemo Application data (PS/GDG/VSAM) with the OpenFrame tool-kit
-	Update OpenFrame CICS environment with AWS CardDemo CICS system definitions (CSD file)  
-	Initialize the AWS CardDemo Application 

The OpenFrame platform enables below key features:
-	The ability to RePlatform mainframe applications with **minimal to nil change** to AWS.
-	The transition of data - DB, Datasets (PS, PDS, GDG, VSAM) to AWS RDS and storage.
-	Support for online CICS applications.
-	A batch environment to support the move of current jobs, job control, JCL, and batch utilities.

Below steps are executed in this chapter:

#### 1. [Create the AWS CardDemo application PDS Library]({{< ref "31-Create-AWS-CDA-PDS-library.md" >}})
#### 2. [Copy AWS CardDemo Application PDS contents]({{< ref "32-copy-PDS-contents.md" >}})
#### 3. [Migrate Business Application data - PS/VSAM/GDG]({{< ref "33-migrate-data.md" >}})
#### 4. [Run AWS CardDemo Application initial setup jobs]({{< ref "34-run-initial-jobs.md" >}})
#### 5. [Openframe OCS CICS region setup]({{< ref "35-cics-setup.md" >}})

