## Software Management

# 📖Objectives
**In this lab, you will:**
- Update the Linux machine using the package manager
- Roll back or downgrade a previously updated package through the package manager
- Install the AWS Command Line Interface (AWS CLI)
  
# 📝Task 1: Use SSH to connect to an Amazon Linux EC2 instance
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

## 📖Task 2: Update your Linux machine
In this task, you use the yum package manager to update and upgrade the machine, including relevant security packages.
- To validate that you are in the companyA home folder, enter *pwd* and press Enter.
- If you are not in this folder, enter *cd companyA* and press Enter.
- If you are not in this folder, enter *cd companyA* and press Enter.
- To apply security-related updates, enter *sudo yum update --security* and press Enter.
- To update packages, enter *sudo yum -y upgrade* and press Enter.
<img width="1366" height="728" alt="lab-2 (1)" src="https://github.com/user-attachments/assets/11fa931a-25a7-470b-a0fc-b9326bb08d18" />

*Figure: Once the sudo yum -y upgrade command is ran, the packages are updated and the system will let you know that you are running the current updated version.*

Next step:
- To view the install of httpd and view the history of updates, enter *sudo yum install httpd -y* and press Enter.
<img width="1366" height="728" alt="lab-2 (2)" src="https://github.com/user-attachments/assets/cd9b3e21-9a14-4f29-a3f2-729ca23f6c49" />

 *Figure: This command installs httpd and will also show a list of all previous updates and current packages on the instance.*

# Task 3: Roll back a package
In this task, you downgrade a package that has been updated through the yum package manager by doing the following:
- Using the yum history to list what has been installed and updated
- Rolling back to the most recent updates in the history list
Next step:
- To validate that you are in the companyA home folder, enter *pwd* and press Enter.
- To view the history of updates, enter *sudo yum history list* and press Enter.
<img width="1366" height="184" alt="lab-2 (3)" src="https://github.com/user-attachments/assets/744a1f10-a967-4c16-b3b9-a4d102611419" />

  *Figure: Once the sudo yum history-list command is finished running, two users will appear (ec2-user and System) with the date, time, and actions that they did. It also shows how many files that were altered.*

Next step:
- To view the most recent set of updates, enter *sudo yum history info <#>* and replace <#> with the history list number from the previous step.
- Enter *sudo yum -y history undo <#>* and replace <#> with the history list number from the previous steps. Once you have adjusted this command with this number, press Enter.
<img width="1366" height="411" alt="lab-2 (4)" src="https://github.com/user-attachments/assets/e460e6dd-b442-49d7-b089-08d3d10a2df7" />

*Figure: Once the sudo yum -y history undo 2 command is ran, it now shows many packages as dep-install.*

# Task 4: Install the AWS CLI on Red Hat Linux
- To verify that Python is installed, enter the following command and press Enter: *python3 --version*
- To see if the pip package manager is already installed, enter the following command and press Enter: **pip3 --version**
- Run this command and press enter: curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
- unzip awscliv2.zip
<img width="1366" height="728" alt="lab-2 (5)" src="https://github.com/user-attachments/assets/6e45000c-bc78-4a6a-ba14-167a015e7bb8" />
 - Run the following command: *sudo ./aws/install*
 - aws help &
 <img width="1366" height="728" alt="lab-2 (6)" src="https://github.com/user-attachments/assets/ea527dfc-f013-4849-b010-e5632110c057" />

Enter q to exit.

# Task 5: Configure the AWS CLI to connect to your AWS account

-Run the *aws configure* and press ENTER

**At the prompts, enter the following information:**
1. For the AWS Access Key ID, leave blank and press Enter.
2. For the AWS Secret Access Key, leave blank and press Enter.
3. For the Default region name, enter us-west-2 and press Enter.
4. For the Default output format, enter json and press Enter
- enter the command *sudo nano ~/.aws/credentials*
- Paste the following on nano command

  [default]
  
aws_access_key_id=<your access key ID>

aws_secret_access_key=<your access key>

aws_session_token=<your session token>

<img width="1366" height="728" alt="lab-2 (7)" src="https://github.com/user-attachments/assets/903f1525-4142-4f7e-8044-9074f654507d" />

# Task 5: Configure the AWS CLI to connect to your AWS account
- In the manangment Console search *EC2* and choose EC2. In the Resources section, choose Instances (running). There is one instance called *Command Host.* Copy and paste the Instance ID for the Command Host into a text editor to use in the following step.
<img width="1366" height="728" alt="lab-2 (8)" src="https://github.com/user-attachments/assets/1d5af345-f0d5-4662-b981-ae7972adde72" />
- Run the following command: aws ec2 describe-instance-attribute --instance-id i-1234567890abcdefg --attribute instanceType

  
