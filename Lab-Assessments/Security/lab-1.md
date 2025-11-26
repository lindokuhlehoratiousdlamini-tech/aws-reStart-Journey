# Monitor an EC2 Instance
## Lab overview
Logging records system events so you can see detailed activity, while monitoring analyzes that data to track performance and detect issues. In this lab, I create a CloudWatch alarm that triggers when an EC2 instance’s CPU goes above a set level, and I set up an SNS subscription to email me when the alarm activates. I then run a stress test on the instance to push its CPU usage to 100%.
## Challanges
The only challange I encounted was creating a tag for a Restore volume. The tag was succesfully created but it couldn`t be dispalyed and the next step wanted me to implicate an Action to attach a volume. I created 3 tags and still couln`t show even though i reloaded. I went to Instances to check if are they running, when i came back i saw the Restore volume and was able to properly configure the required step.
## Objectives
After completing this lab, you should be able to:
  
  - Create an Amazon SNS notification
  - Configure a CloudWatch alarm
  - Stress test an EC2 instance
  - Confirm that an Amazon SNS email was sent
  - Create a CloudWatch dashboard
 ## Task 1: Configure Amazon SNS
 I search for SNS in the console, open Simple Notification Service, go to Topics, and choose Create topic.

On the Create topic page in the Details section, configure the following options:
- Type: Choose Standard.
- Name: Enter MyCwAlarm 
- Choose Create topic.
- 
 The configurations should look like the following image:

<img width="889" height="543" alt="lab-1 (1)" src="https://github.com/user-attachments/assets/4d1055b4-0c80-4354-acb5-0ed4598f6a3a" />
