# Data Protection Using Encryption
## Lab Overview
In this lab, I learn how encryption works by creating a KMS key, using it on an EC2 instance to encrypt and decrypt text files, and seeing how encrypted data becomes unreadable until properly decrypted.
## Objectives
After completing this lab, you should be able to:
- Create an AWS KMS encryption key
- Install the AWS Encryption CLI
- Encrypt plaintext
- Decrypt ciphertext
## Task 1: Create an AWS KMS key
I search for KMS in the console, open Key Management Service, and choose Create a key.

For Key type, choose Symmetric, and then choose Next.

The configurations should look like the following image:
<img width="1071" height="526" alt="lab-2(1)" src="https://github.com/user-attachments/assets/4f5521c6-4f86-413a-8621-55f5a7fb6a7d" />

On the Add labels page, configure the following:
- Alias: MyKMSKey
- Description: Key used to encrypt and decrypt data files.
  <img width="1040" height="543" alt="lab-2 (2)" src="https://github.com/user-attachments/assets/fb085f79-7f82-4985-9430-d426520ff9e2" />
Choose Next.

On the Define key administrative permissions page, in the Key administrators section, search for and select the check box for voclabs and then choose Next.

On the Define key usage permissions page, in the This account section, search for and select the check box for voclabs and then choose Next.
<img width="1045" height="417" alt="lab-2 (3)" src="https://github.com/user-attachments/assets/b829e58d-50cf-447f-a888-d7d3eb2f47ee" />

Review the settings, and then choose Finish.
<img width="1052" height="496" alt="lab-2 (4)" src="https://github.com/user-attachments/assets/1e860ddb-c993-4015-ada4-ea45dec3247a" />

Choose the link for MyKMSKey, which you just created, and copy the ARN (Amazon Resource Name) value to a text editor.

You will use this copied ARN later in the lab.

## Task 2: Configure the File Server instance
I open EC2 from the console, select the File Server instance, and connect to it using the Session Manager tab.
<img width="1116" height="218" alt="lab-2 (5)" src="https://github.com/user-attachments/assets/1c7c98ab-ada7-406e-9d49-ff455fd9d96f" />

<img width="1327" height="476" alt="lab-2 (6)" src="https://github.com/user-attachments/assets/e7f40917-1331-43d7-a064-e252c8e1c4b1" />

To change to the home directory and create the AWS credentials file, run the following commands:
cd ~
aws configure

When prompted, configure the following:
- AWS Access Key ID: Enter 1, and then press Enter.
- AWS Secret Access Key: Enter 1, and then press Enter.
- Default region name: Copy and paste the Region provided from the Vocareum AWS Details page.
- Tip You may need to press Ctrl+Shift+V to paste into Session Manager.
- Default output format: Press Enter.

I open Vocareum’s AWS Details, show the AWS CLI section, copy the code block into a text editor, and return to the File Server browser tab.

To open the AWS credentials file, run the following command: vi ~/.aws/credentials

n the ~/.aws/credentials file, type dd multiple times to delete the contents of the file.

Paste in the code block that you copied from Vocareum.

The AWS credentials file should now look similar to the following:

Example of AWS credentials file contents.

The AWS credentials file includes the following: aws_access_key_id, aws_secret_access_key, and aws_session_token. The credentials used are from the AWS Details section.

To save and close the file, press Escape, type :wq and then press Enter.

To view the updated contents of the file, run the following command: cat ~/.aws/credentials

To install the AWS Encryption CLI and set your path, run the following commands:
________________________
- pip3 install aws-encryption-sdk-cli
- export PATH=$PATH:/home/ssm-user/.local/bin
________________________________

