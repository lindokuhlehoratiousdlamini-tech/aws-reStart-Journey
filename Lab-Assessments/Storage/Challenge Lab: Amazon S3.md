# Challenge Lab: Amazon S3
## Lab overview
In this challenge lab, you create an Amazon Simple Storage Service (Amazon S3) bucket and perform some routine tasks, such as uploading objects and configuring permissions to make those objects publicly accessible through a browser.
## Objectives
By the end of this challenge, you should be able to do the following:
- Create an S3 bucket. 
- Upload an object into this bucket. 
- Access the object by using a web browser. 
- List the contents of the S3 bucket by using the AWS Command Line Interface (AWS CLI). 

## Task 1: Connecting to the CLI Host instance

On the AWS Management Console, in the Search bar, enter and choose EC2 to open the EC2 Management Console.
- In the navigation pane, choose Instances.
- From the list of instances, select the CLI Host instance.
- Choose Connect.
  
<img width="1087" height="236" alt="Screenshot (23)" src="https://github.com/user-attachments/assets/4d085ab8-d337-4a62-aead-d0cada04a902" />

<img width="1308" height="540" alt="Screenshot (24)" src="https://github.com/user-attachments/assets/1c9083f8-6f31-4631-8c41-ce676f4e64e3" />

On the EC2 Instance Connect tab, choose Connect.

## Task 2: Configuring the AWS CLI
To set up the AWS CLI profile with credentials, run the following command in the EC2 Instance Connect terminal:
________________________________________________
aws configure
_________________________________________________
<img width="1333" height="316" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/cb67d57a-eab1-4924-a80d-4ba81aa6056c" />

At the prompts, copy the following values that you pasted into your text editor, and paste them into the terminal window as directed.
<img width="1093" height="512" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/e0d6c0b0-091c-4e5a-a947-b69adf2283db" />

- AWS Access Key ID: Enter the value for AccessKey.
- AWS Secret Access Key: Enter the value for SecretKey.
- Default region name: Enter us-west-2.
- Default output format: Enter json.

## Task 3: Finishing the challenge
To finish the challenge, do the following:
- Create an S3 bucket. 
- Upload an object into this bucket.
- Try to access the object by using a web browser. 
- Make the object (not the bucket) publicly accessible.
- Access the object by using a web browser. 
- List the contents of the S3 bucket by using the AWS CLI.

       Let`s Deploy to S3
 - In the Manangment Console search S3 and chooose S3
 - Select create a backect
 -  Configure your buckect name to be **websiteeasymade* and leave the settings at default
    <img width="1354" height="546" alt="website easy made" src="https://github.com/user-attachments/assets/d8bfd126-7f5a-49bd-8b5c-12cbac3fcf38" />
    We will need to change some settings later, but we will see at a later point

  - On your right below click Create a bucket
 <img width="1353" height="463" alt="Screenshot 2025-11-27 145140" src="https://github.com/user-attachments/assets/3b418227-7aa0-4954-85de-22275942178b" />

Okay great!
- Once you have your website bucket created you will need to upload all of your files and folders 
<img width="1366" height="547" alt="Screenshot 2025-11-27 145601" src="https://github.com/user-attachments/assets/b38d38ce-8ed8-46cc-b89c-f0822b742b54" />
<img width="1326" height="557" alt="Screenshot 2025-11-27 145710" src="https://github.com/user-attachments/assets/376ef7c3-f3d0-4219-b6df-1f5b00a17db5" />
- Once you have succesfully uploaded your files and folders, go back to your bucket and click on it.
- You will click your index.html
- Then scroll down and copy & paste the Object URL to a new tab.
<img width="1366" height="679" alt="Screenshot 2025-11-27 150017" src="https://github.com/user-attachments/assets/af502c1c-0406-447a-8f27-7d67cda16cb7" />
- Access has been denied. What you need to do is to enable the Static Website Hosting.
- To do that go back to your bucket and go to the properies tab and scroll to the bottom
- You will seee something called Stating website hosting, click on edit and enable the static website hosting.
- give the name of your index document to
  _______________________________________
  index.html
  ________________________________________
  <img width="1342" height="545" alt="Screenshot 2025-11-27 150214" src="https://github.com/user-attachments/assets/aee64b87-fc25-4191-87cb-2fa3344d128b" />
Click on save changes.
<img width="1366" height="220" alt="Screenshot 2025-11-27 150247" src="https://github.com/user-attachments/assets/2968f952-3cd8-49a1-b9f3-494140a364f0" />
- Great! Go back and refresh.
<img width="1366" height="679" alt="Screenshot 2025-11-27 150017" src="https://github.com/user-attachments/assets/69118eef-846e-43ae-a068-270985e3d7fc" />
- As you can see access is still denied!
- We are trying to acess this website from the internert so what we need to do is to make the bucket publicly accessable
- So, to do that go to the Permission tab
- click on block public Access
- Edit
- Then uncheck Block all public access
  <img width="1342" height="557" alt="Screenshot 2025-11-27 150422" src="https://github.com/user-attachments/assets/1fa6ec90-73c4-4e0a-8a0d-14f99253162b" />
<img width="1366" height="560" alt="Screenshot 2025-11-27 150453" src="https://github.com/user-attachments/assets/d7591687-6cca-4ed5-bd91-f3406d4da9c5" />
<img width="1356" height="210" alt="Screenshot 2025-11-27 150516" src="https://github.com/user-attachments/assets/b86f500e-b83e-4140-a77a-a52c038f8430" />
- Great!
- Now lets go see if we are having a publicly accessable website
- Go and Reload the webpage.
<img width="1366" height="679" alt="Screenshot 2025-11-27 150017" src="https://github.com/user-attachments/assets/fd014b37-af03-4d24-9386-263262b78bc8" />
- We still have a Acess denied error
- What we must do is to make all our objects realted to our website publicly accessable
- Therefore, we have to select them all 
<img width="1351" height="534" alt="Screenshot 2025-11-27 150716" src="https://github.com/user-attachments/assets/4b8c1fde-953e-4740-b556-f7b47913a593" />
- Click on Actions, when you scroll down you should be able to see the **Make public using ACL* not greyed out.
- So, for that action to be enabled you must go to Permissions and scroll down to Object ownership
- Click on Edit
- Enable access control list
- scroll down to the check box *I acknowledge that ACLs will be restored.* and check it
  <img width="1342" height="538" alt="Screenshot 2025-11-27 150741" src="https://github.com/user-attachments/assets/61e6ade7-f0b7-403d-a309-aed1ca13e67d" />
<img width="1347" height="562" alt="Screenshot 2025-11-27 150816" src="https://github.com/user-attachments/assets/d68583af-6dd9-492c-9833-9217cfaf36ea" />

 Scroll down to save changes 
<img width="1366" height="162" alt="Screenshot 2025-11-27 150835" src="https://github.com/user-attachments/assets/f3f678ac-58d2-4f56-af18-1824a2bb2b1e" />

- Go back to Objects tab and select all Objects
  <img width="1348" height="544" alt="Screenshot 2025-11-27 150903" src="https://github.com/user-attachments/assets/6c8aecfb-d3e2-4968-b0b1-13022e3c6924" />

- Click on Actions
- Choose make public using ACLs 
<img width="1354" height="547" alt="iyo eza kqala" src="https://github.com/user-attachments/assets/a424e2f6-b718-4566-a6bc-024a0f1b1d12" />
click on Make puclic 
<img width="1348" height="547" alt="Screenshot 2025-11-27 151024 khona eza kuqala" src="https://github.com/user-attachments/assets/9f9327f7-c55e-4556-ac07-3a0a6fac5ac0" />
- Now go back and refresh
  <img width="1366" height="684" alt="end product" src="https://github.com/user-attachments/assets/49899e38-5fde-4425-9474-02678a920646" />

And there it is! You have sucessfully hosted your static website on AWS S3








