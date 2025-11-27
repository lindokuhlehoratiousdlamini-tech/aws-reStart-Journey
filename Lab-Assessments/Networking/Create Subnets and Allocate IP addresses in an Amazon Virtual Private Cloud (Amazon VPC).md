# Create Subnets and Allocate IP addresses in an Amazon Virtual Private Cloud (Amazon VPC)
## Objectives

In this lab, you will:
- Summarize the customer scenario
- Create a Amazon Virtual Private Cloud (Amazon VPC) and understand how to create subnets and allocate IP addresses
- Familiarize yourself with the Amazon Web Services (AWS) Management Console
- Develop a solution to the customer's issue in this lab
- Summarize and describe your findings (group activity)
## Scenario
Your role is a cloud support engineer at AWS. During your shift, a customer from a startup company requests assistance regarding a networking issue within their AWS infrastructure. The following is the email and an attachment regarding their architecture: 

## Customer diagram

<img width="824" height="530" alt="lab-1 (1)" src="https://github.com/user-attachments/assets/00d6abe1-ee3b-4430-987c-bc225811dc8d" />

 *Figure: In the customer's VPC architecture, the customer needs approximately 15,000 IP addresses for their Seattle office headquarters and 50 IP addresses for their operations department, which will be in the public subnet.*

 ## Task 1: Investigate the customer's needs
 
A VPC is like having your own private data center in the cloud. It is separated from other networks, and I can use it to quickly launch my AWS resources. The resources inside a VPC talk to each other using private IP addresses. If an instance needs to connect to the internet, it must have a public IP address, and the VPC must have an internet gateway and a route table so the traffic can reach outside. A CIDR block is the range of private IP addresses that the VPC uses, and a subnet is a smaller part of that range. To choose a CIDR range, I can use an online subnet calculator, and to see the recommended private IP address ranges, I can check the RFC1918 guide

- I go to the AWS console, search for the VPC service, open it, and then use the “Launch VPC Wizard” to start creating my first VPC through a simple step-by-step setup.
- In the VPC wizard, I follow the guided steps to create my VPC and choose a CIDR block between /16 and /28 while configuring the required options:
1. For IPv6 CIDR block, leave No IPv6 CIDR Block selected. You will not be using IPv6 in this lab.
2. For the VPC name, enter First VPC
3. For Public subnet's IPv4 CIDR, this option prefills. Input the correct VPC CIDR that you are using; however, keep in mind that the public subnet's CIDR must be smaller then the VPC CIDR block, and it must be able to include at least 50 IP addresses.
4. For Availability Zone, choose No Preference.
5. For Subnet name, leave this option set to Public subnet.
6. Leave the remaining options set to their default settings.

<img width="1366" height="637" alt="lab-1 (2)" src="https://github.com/user-attachments/assets/c7b69861-24af-41df-834a-3557eab522ba" />
   
7. At the lower-right, choose Create VPC.

<img width="1366" height="643" alt="lab-1 (3)" src="https://github.com/user-attachments/assets/be137138-db65-45b4-968c-207e0ae17cd5" />

*You`ve successfully created a VPC*

## Create a VPC with a public subnet
<img width="1366" height="639" alt="lab-1 (4)" src="https://github.com/user-attachments/assets/81769dfc-7afa-4120-92eb-36654d7b135a" />

At the lower-right, Choose Create subnet

<img width="1366" height="651" alt="lab-1 (5)" src="https://github.com/user-attachments/assets/db2f78bc-918e-4ac3-9dbc-322c5042c040" />

Congratulations you`ve succesfully completed your lab!!🎉
