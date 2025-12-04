## Working with AWS Lambda
# Lab overview

In this lab, you set up a serverless system using AWS Lambda. The Lambda function creates a daily sales report by doing the following:
1. Gets database login details from AWS Systems Manager Parameter Store.
2. Connects to a MySQL database that is running on an EC2 LAMP server.
3. Pulls sales data from the database.
4. Generates a report based on the data.
5. Emails the report automatically every day.

The architecture diagram shows how all these steps happen in order, from storing configuration parameters → running the Lambda function → connecting to the database → sending the email.
<img width="773" height="415" alt="lab-2 (1)" src="https://github.com/user-attachments/assets/ca4e1506-a8ff-477b-aff9-367addb65967" />

Explaining the diagram:

| **Step** | **What Happens**                                                                                                  | **Simple Explanation**                                                           |
| -------- | ----------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **1**    | A CloudWatch Events rule triggers the salesAnalysisReport Lambda function every day at 8 PM (Monday–Saturday).  | CloudWatch automatically starts the main Lambda function at the scheduled time.  |
| **2**    | The salesAnalysisReport Lambda function calls another Lambda function named salesAnalysisReportDataExtractor. | The main function asks a second function to fetch the data it needs.             |
| **3**    | The salesAnalysisReportDataExtractor function runs an analytical query on the cafe_db database.               | The second function connects to the database and runs a query to get sales data. |
| **4**    | The query results are sent back to the salesAnalysisReport function.                                            | The database results are returned to the main function.                          |
| **5**    | The salesAnalysisReport function formats the report and sends it to the salesAnalysisReportTopic SNS topic.   | The main function creates a readable report and sends it to SNS.                 |
| **6**    | The salesAnalysisReportTopic SNS topic delivers the report by email to the administrator.                       | SNS emails the final report to the admin.                                        |
# Objectives
After completing this lab, I will be able to do the following:
- Recognize necessary AWS Identity and Access Management (IAM) policy permissions to facilitate a Lambda function to other Amazon Web Services (AWS) resources.
- Create a Lambda layer to satisfy an external library dependency.
- Create Lambda functions that extract data from database, and send reports to user.
- Deploy and test a Lambda function that is initiated based on a schedule and that invokes another function.
- Use CloudWatch logs to troubleshoot any issues running a Lambda function.

 # Challanges 
This was so far my most biggest and head throbbing lab i had to do out of all my labd. My issue was the testing and save. I got an "Execution result: failed" erro which was far by right according to the lab. But i had to fix it in which that is when everything became so sour for me and everything became soo messy. I made a lot of Inbound rules through the required lab for 3306 but still nothing happened when i tested it over and over again. i simply went to the Configuration tab and choose VPC to check the Inbound rules of the EC2 security group to see if port 3306 is allowed. If not, I add a rule to allow it. After fixing the security group, I return to the salesAnalysisReportDataExtractor Lambda function, go to the Test tab, and 
run the test again. If everything is correct, I see a green message: “Execution result: succeeded (logs)”, which means the function ran successfully.

# Task 1: Observing the IAM role settings
     Task 1.1: Observing the salesAnalysisReport IAM role settings
I go to IAM in the AWS Console and open the role called salesAnalysisReportRole.

When I check the Trust relationships, I see that Lambda is trusted.
This means Lambda is allowed to use this role.

In the Permissions tab, I see four policies attached:
- **AmazonSNSFullAccess** – allows me to use SNS completely.
- **AmazonSSMReadOnlyAccess** – allows me to read values from Parameter Store.
- **AWSLambdaBasicRunRole** – allows my Lambda function to write logs to CloudWatch.
- **AWSLambdaRole** – allows one Lambda function to call another.

Later in the lab, I will use this role for the salesAnalysisReport Lambda function.

    Task 1.2: Observing the salesAnalysisReportDERole IAM role settings

I go back to the Roles page in IAM and search for sales again.

From the results, I open the salesAnalysisReportDERole role.

In the Trust relationships tab, I see that lambda.amazonaws.com is trusted, which means Lambda can use this role.

In the Permissions tab, I see two policies:
- **AWSLambdaBasicRunRole** – lets my Lambda function write logs to CloudWatch.
- **AWSLambdaVPCAccessRunRole** – allows my function to create and manage network interfaces so it can connect to a VPC.

This role will be used by the salesAnalysisReportDataExtractor Lambda function that I create next.
# Task 2: Creating a Lambda layer and a data extractor Lambda function
First things first to start this lab you need to dowload the following ZIP folders 
________________________________________________________________
pymysql-v3.zip

salesAnalysisReportDataExtractor-v3.zip
_________________________________________________________________

      Task 2.1: Creating a Lambda Layer

I go to AWS Lambda in the console and open the Layers section.

I choose Create layer and fill in the details:
- I name the layer pymysqlLibrary.
- I add the description PyMySQL library modules.
- I upload the pymysql-v3.zip file.
- I select Python 3.9 as the compatible runtime.
  
  <img width="1336" height="498" alt="lab-2 (3)" src="https://github.com/user-attachments/assets/54c56634-9d05-459a-bfd0-4b3654595934" />

- Then I choose Create to finish making the layer.

           Task 2.2: Creating a data extractor Lambda function
  
I go to the Functions page in AWS Lambda and choose Create function.
- I select Author from scratch.
- I name the function salesAnalysisReportDataExtractor.
- I choose Python 3.9 as the runtime.
- In Change default execution role, I select Use an existing role.
- I pick the salesAnalysisReportDERole as the existing role.
<img width="1350" height="513" alt="lab-2 (5)" src="https://github.com/user-attachments/assets/c824dbdf-325e-4f84-b214-94cb91eb6e5f" />

Then I choose Create function.

                Task 2.3: Adding the Lambda layer to the function

In my Lambda function page, I go to the Function overview section and choose Layers.
- At the bottom, I select Add a layer.
- On the Add layer page:
- I choose Custom layers.
- I select pymysqlLibrary.
- I choose Version 1.
  
<img width="1366" height="499" alt="lab-2 (8)" src="https://github.com/user-attachments/assets/d9228758-1162-4706-8b6c-9f53f68eb8fe" />

Then I choose Add to attach the layer to my function.

              Task 2.4: Importing the code for the data extractor Lambda function

I open my salesAnalysisReportDataExtractor Lambda function.
- In Runtime settings, I choose Edit and change the handler to salesAnalysisReportDataExtractor.lambda_handler, then I save it.
- In the Code source section, I choose Upload from, select .zip file, and upload the salesAnalysisReportDataExtractor-v3.zip file I downloaded earlier.
<img width="1326" height="291" alt="lab-2 (12)" src="https://github.com/user-attachments/assets/0bf49991-6cd8-4874-a95b-7665bd888e0f" />
<img width="820" height="378" alt="lab-2 (13)" src="https://github.com/user-attachments/assets/03357b3a-baf9-41d0-a3dc-dff13d675c74" />

  Finally, I choose Save.             

          Task 2.5: Configuring network settings for the function

I go to the Configuration tab of my Lambda function and choose VPC.

Then I select Edit and set the following:
- For VPC, I pick the one named Cafe VPC.

For Subnets, I choose Cafe Public Subnet 1.
(I ignore the warning about needing two subnets.)

For Security groups, I choose CafeSecurityGroup and see its inbound and outbound rules appear.

<img width="1350" height="516" alt="lab-2 (14)" src="https://github.com/user-attachments/assets/327f1ea5-d31d-4da2-b24a-6713dceec258" />

After that, I choose Save.

# Task 3: Testing the data extractor Lambda function
    Task 3.1: Launching a test of the Lambda function

 I open AWS Systems Manager in a new browser tab and go to Parameter Store.

I open each parameter and copy its Value into a text editor:

`/cafe/dbUrl`

`/cafe/dbName`

`/cafe/dbUser`

`/cafe/dbPassword`

Then I return to my salesAnalysisReportDataExtractor Lambda function in the Lambda console and go to the Test tab.

- I select Create new event.

- I name the event SARDETestEvent.

- I choose the hello-world template.

- I replace the JSON in the Event JSON pane with the new JSON object I need for testing.
- I ran the following code for testing
  
` {
  "dbUrl": "<value of /cafe/dbUrl parameter>",
  "dbName": "<value of /cafe/dbName parameter>",
  "dbUser": "<value of /cafe/dbUser parameter>",
  "dbPassword": "<value of /cafe/dbPassword parameter>"
}`

Then i will save and test. After some time the page showed a "Execution result: failed" error i did not give in to much worry to it , i simply went to the Configuration tab and choose VPC to check the Inbound rules of the EC2 security group to see if port 3306 is allowed. If not, I add a rule to allow it. After fixing the security group, I return to the salesAnalysisReportDataExtractor Lambda function, go to the Test tab, and run the test again. If everything is correct, I see a green message: “Execution result: succeeded (logs)”, which means the function ran successfully.
