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

