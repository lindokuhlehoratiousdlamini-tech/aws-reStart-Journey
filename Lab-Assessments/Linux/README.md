# Introduction to an Amazon Linux Amazon Machine Image (AMI)
This lab is designed to reinforce your knowledge of the basic command line interface functionality and provide a solid foundation from which you can continue to learn about new commands and capabilities within the Linux shell.
## Senario
In this lab, you use Secure Shell (SSH) to access an Amazon Linux Amazon Machine Image (AMI) within Vocareum labs. Next, you use the man command to access the man pages.
 
## Objectives
After completing this lab, you will be able to:
- Use SSH to access an Amazon Linux AMI within Vocareum labs
- Understand the purpose of the man command
- Demonstrate the search feature of the man pages
- Examine man page headers
# Task 1: Use SSH to connect to an Amazon Linux EC2 instance
In this task, you will connect to a Amazon Linux EC2 instance. You will use an SSH utility to perform all of these operations.
# 🔑 Accessing the AWS Console
- Click Start Lab → wait for Lab status: ready.
- Click AWS to open the console (auto-login).
- Arrange your screen so the lab instructions and console are side by side.

# 📝 Connect to the EC2 Instance (SSH)
**Windows Users**
- Download labsuser.ppk from the Details panel.
- Note the Public IP.
- Use PuTTY → configure SSH following AWS instructions.
**Connect as:**
ec2-user@<public-ip>

**macOS / Linux Users**
Download labsuser.pem.

**In terminal:**

**Open a terminal window, and change directory cd to the directory where the labsuser.pem file was downloaded. For example, if the labuser.pem file was saved to your Downloads directory, run this command:**

cd ~/Downloads

**Change the permissions on the key to be read-only, by running this command:**

chmod 400 labsuser.pem

**Run the below command (replace <public-ip> with the PublicIP address you copied earlier).
Alternatively, return to the EC2 Console and select Instances. Check the box next to the instance you want to connect to and in the Description tab copy the IPv4 Public IP value.:**

ssh -i labsuser.pem ec2-user@<public-ip>

**Type yes on first connection.**
# 📝 Task 2: Explore the man Pages
In this exercise, you use a bash terminal to view the Linux standard help system. This system is generally referred to as the manual pages (or man pages).

In the SSH terminal, run:
man man
<img width="1366" height="728" alt="man man 1" src="https://github.com/user-attachments/assets/a49dda41-154c-420f-93b5-1e9aa24e4f0e" />
*Figure: The man page displays important information about a command.* 

**The following are a few important man page headers:**
- NAME
- SYNOPSIS
- DESCRIPTION
- OVERVIEW
- EXAMPLES
- FILES
- OPTIONS
- SEE ALSO
<img width="1366" height="728" alt="Screenshot 2025-11-24 110653" src="https://github.com/user-attachments/assets/f88283de-b01a-42cc-a640-9c0527c81e84" />
*Figure: The DESCRIPTION header provides an overview of a command.*
Congratulations you have succesfully completed your lab!!

