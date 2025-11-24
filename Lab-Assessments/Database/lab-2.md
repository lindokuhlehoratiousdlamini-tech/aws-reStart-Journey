# Introduction to Amazon DynamoDB
## Lab overview
Amazon DynamoDB is a fast and flexible NoSQL database service for all applications that need consistent, single-digit millisecond latency at any scale. It is a fully managed database and supports both document and key-value data models. Its flexible data model and reliable performance make it a great fit for mobile, web, gaming, ad-tech, Internet of Things (IoT), and many other applications.

In this lab, you will create a table in DynamoDB to store information about a music library. You will query the music library and then delete the DynamoDB table.

## Topics covered
In this lab, you will:
- Create an Amazon DynamoDB table
- Enter data into an Amazon DynamoDB table
- Query an Amazon DynamoDB table
- Delete an Amazon DynamoDB table
## Task 1: Create a new table
Open **DynamoDB**, choose **Create table**, enter **Music** with **Artist** as the partition key and **Song** as the sort key, keep defaults, create the table, and wait for it to become **Active**.

<img width="1362" height="375" alt="lab-2 (1)" src="https://github.com/user-attachments/assets/0136dc37-4a9f-4183-a218-80735d473767" />

# Task 2: Add data
<img width="1366" height="728" alt="lab-2 (2)" src="https://github.com/user-attachments/assets/b894d9c1-bbd8-4f8f-bc76-6e6ef2202437" />

You added items to the **Music** DynamoDB table by entering the required attributes (*Artist* and *Song*) and then adding extra fields like *Album*, *Year*, *Genre*, and *LengthSeconds*. Each item used a different set of attributes, showing that DynamoDB lets you store flexible, varied data without defining a fixed schema. You also learned that data can be loaded faster using tools like the AWS CLI or programmatic methods.

# Task 3: Modify an existing item

<img width="734" height="348" alt="lab-2 (3)" src="https://github.com/user-attachments/assets/140771f0-df23-46aa-9122-819f4832ed12" />

I opened the **Music** table in DynamoDB, selected the **Psy** item, changed the **Year** from 2011 to 2012, and saved the update.
and made the rest of necessary additions
# Task 4: Query the table
I queried the table for **Psy – Gangnam Style** to quickly retrieve the item, then used a **Scan** with a filter on **Year = 1971** to find the matching song, learning that queries are far more efficient than scans.

# Task 5: Delete the table

I opened the **Music** table’s settings, chose **Delete table**, typed *delete* to confirm, and removed the table.

 Congratulations you have sucessfully finished your lab!!🎉
