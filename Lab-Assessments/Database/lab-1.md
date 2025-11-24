# Introduction to Amazon Aurora
## Overview
This lab introduces you to Amazon Aurora and provides you with a basic understanding of how to use Aurora. You will follow the steps to create an Aurora instance and then connect to it.

## Topics covered
**After completing this lab, you will be able to:**
- Create an Aurora instance
- Connect to a pre-created Amazon Elastic Compute Cloud (Amazon EC2) instance
- Configure the Amazon EC2 instance to connect to Aurora
- Query the Aurora instance
## Task 1: Create an Aurora instance
In the Manangment Console search for and choose *RDS*. In the left navigatio pane choose Database. *Create a new database*

Configure the following steps:
1. For Choose a database creation method, choose Standard create.
2. For Engine type, choose Aurora (MySQL Compatible).
3. For Engine version, choose the version specified as the default for major version 8.0.
4. For Templates, choose Dev/Test.

In the Settings section, configure the following options:
1. For DB cluster identifier, enter aurora.
2. For Master username, enter admin.
3. For Master password, enter admin123.
4. For Confirm password, enter admin123

In the Instance configuration section choose Burstable classes and choose db.t3.medium from the dropdown list.

In the Availability & durability section for Multi-AZ deployment, choose Don't create an Aurora Replica.

 In the Connectivity section, configure the following options and leave any not mentioned with their default value:
* For **Virtual private cloud (VPC)**, choose **LabVPC**.
* For **Subnet group**, choose **dbsubnetgroup**.
* For **Public access**, select **No**.
* For **VPC security group**, select **Choose existing**.
* For **Existing VPC security groups**, remove the **default** security group.
* From the **Existing VPC security groups** dropdown list, choose **DBSecurityGroup**.

In the Monitoring section, clear the check box for Enable Enhanced monitoring.

Expand  Additional configuration section. For Initial database name, enter world

In the Encryption section, clear the check box for Enable encryption. 

In the Maintenance section, clear the check box for Enable auto minor version upgrade.

Scroll to the bottom of the screen, and then choose Create database.

<img width="1366" height="728" alt="lab-1 (1)" src="https://github.com/user-attachments/assets/3fb12177-a469-4b31-8aa1-8d4adc44ed67" />

## Task 2: Connect to an Amazon EC2 Linux instance
Search for EC2, open Instances, select Command Host, choose Connect, pick Session Manager, and click Connect to open the terminal.

<img width="1366" height="728" alt="lab-1 (2)" src="https://github.com/user-attachments/assets/6b10b4dd-1ea7-449f-85de-0d68beff469f" />

# Task 3: Configure the Amazon EC2 Linux instance to connect to Aurora
-  To install the MariaDB client, run the following command: sudo yum install mariadb -y

<img width="1366" height="728" alt="lab-1 (3)" src="https://github.com/user-attachments/assets/3310f59c-41af-43b7-958a-381eeccc8b52" />

Open **RDS**, go to **Databases**, wait for **aurora-instance-1** to show *Available*, and then select **aurora**.

I learned that the **Aurora cluster endpoint** always connects me to the **primary DB instance**, which is the only one that can perform write operations, so it’s the endpoint I must use when setting up the cluster or when there’s only one DB instance.

<img width="1366" height="728" alt="lab-1 (4)" src="https://github.com/user-attachments/assets/de0823f0-0d78-4f12-9aef-c6e6b1c48034" />

The MySQL Command-Line Client is a SQL shell which enables interaction with database engines. 

<img width="1366" height="728" alt="lab-1 (5)" src="https://github.com/user-attachments/assets/fa387100-e144-4bce-b449-f1b00ae138c9" />

Return to the Session Manager browser tab that was used to connect to the Command Host. To connect to the Aurora instance, run the command you had copied in the previous step.

# Task 4: Create a table and insert and query records
- To list the available databases, run the following command. SHOW DATABASES;
- Run the following command: USE world;
- To insert new records into the country table that you just created, run the command
- run the command SELECT * FROM country WHERE GNP > 35000 and Population > 10000000;
<img width="1366" height="728" alt="lab-1 (6)" src="https://github.com/user-attachments/assets/1a045ee7-dc27-4158-a5c6-0ff39b032291" />

Congratulations you have succcesfully finished this lab!!🎉
