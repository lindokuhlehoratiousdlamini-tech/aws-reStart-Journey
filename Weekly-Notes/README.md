# AWS re/Start Programme Weekly Notes 🚀

Welcome to my weekly notes for the AWS re/Start programme! Here I'll document my learning journey, reflections, and hands-on experiences. Let's get cloud-ready! ☁️✨

# 🌱 Week 1 — Introduction & Foundations

In the first week of the AWS re/Start programme, I focused on building the essential foundations needed to understand computers, operating systems, and the cloud. This was my starting point, and even though the concepts were basic, they were important for everything I will learn later in the programme.

I began by meeting my instructors and fellow learners, and I learned how the programme is structured and what the long-term goals are. This helped me understand the journey ahead and what skills I’m expected to develop by the end. I also set up my learning environment, which included preparing my computer, creating accounts, and joining collaboration platforms like Slack/Teams so I can communicate and work with others throughout the course.

## A major focus of Week 1 was:
- **Digital and computer fundamentals**. I learned how operating systems work, what file systems are, and how computers organise data internally. Understanding these basics helped me see what’s happening “behind the scenes” on a computer and why certain actions matter. This foundational knowledge is especially important in cloud computing, where server management and system behaviour are part of everyday tasks.

One of the biggest skills I developed this week was using the **Linux command line**. I practiced essential terminal commands such as navigating directories, listing files, creating folders, and understanding how the Linux file system is structured. At first, typing commands felt unfamiliar, but I quickly learned how powerful and efficient the terminal is. Because cloud servers often do not have a graphical interface, becoming comfortable with the command line is a crucial step toward working confidently in AWS later on.

Overall, Week 1 gave me a strong start. I built confidence with computers, learned how to use the terminal, and prepared my environment for the hands-on cloud training that comes later. Even though these were introductory skills, they form the foundation for everything else I will do in the cloud — from managing servers to automating tasks and deploying applications. This week set the groundwork for my entire cloud learning journey.

# ☁️ Week 2 — Cloud Concepts & AWS Introduction 

In Week 2 of the AWS re/Start programme, I moved from basic computer fundamentals into understanding what **cloud computing** actually is and why it matters in the modern world. This week helped me build a clear picture of how the cloud works, how AWS fits into it, and why businesses rely on these technologies.

## Learnt about the following:
I began by learning the core idea behind cloud computing: instead of companies buying and maintaining their own physical computers and servers, they can rent computing power, storage, and services over the internet. This simple concept is the foundation of the entire cloud industry. I explored key cloud models — public, private, and hybrid — and learned how each one is used depending on a company’s needs. This helped me understand that the cloud is flexible and can support both small startups and large enterprises with different requirements.

I also learned about the **AWS global infrastructure**, which includes:
- Regions
- Availability Zones
- data centers located all around the world.

AWS divides its global network in a way that helps customers build applications that are fast, secure, and reliable. A “Region” is a specific geographic location, and inside each Region are multiple “Availability Zones,” which are separate data centers designed for high availability. Understanding this structure helped me see how AWS provides resilience: if something fails in one location, the system can continue working from another.

Another important part of Week 2 was learning why companies move to the cloud. I explored the benefits of cloud computing, such as reduced costs, faster deployment, easier scaling, and improved reliability. Instead of waiting days or weeks to set up physical hardware, the cloud allows resources to be created in minutes. This efficiency is a major reason cloud skills are in high demand.

By the end of the week, I could clearly explain what the cloud is, how AWS is built, and why organisations trust cloud services to run their applications. Week 2 gave me the conceptual foundation I need for the more hands-on AWS work that comes later in the programme. It helped me shift my mindset from thinking of computers as physical machines to seeing them as flexible, on-demand, internet-based resources — which is the core of modern cloud computing.
 
# Week 3: AWS Core Services 🛠️

In Week 3 of the AWS re/Start programme, I moved from learning cloud concepts into working directly with AWS services. This was my first real hands-on experience in the cloud, and it helped me understand how companies actually run applications using AWS. I focused mainly on **EC2**, which provides virtual servers, and **S3**, which stores data in the cloud. These two services form the foundation of most cloud environments, so getting comfortable with them was an important part of my progress.

## Learnt about the following:
- **Amazon EC2**, which allows you to create and run virtual machines without needing physical hardware. Instead of buying a server, I could launch one in minutes. During the labs, I created my own EC2 instance, selected an operating system, and connected to it using SSH, which let me access the server through the terminal. This was my first time logging into a cloud-based machine, and it showed me how real-world engineers set up applications, manage configurations, and troubleshoot systems remotely.
- I also learned the key components that keep cloud servers secure and functional. I explored **instance types**, which determine the computing power of the server; **security groups**, which act like virtual firewalls; and **key pairs**, which allow secure remote access. Understanding these features helped me see how AWS protects systems while still giving users full control.
- I then moved on to **Amazon S3**, one of AWS’s most popular storage services. S3 is used to store files, backups, logs, media, and almost any type of digital content. I created S3 buckets, uploaded objects, managed permissions, and explored how S3 keeps data available and safe. What stood out to me most was how S3 automatically scales and doesn’t require any hardware setup — it just works. This made me realise why companies trust S3 for reliable and long-term storage.

By using both EC2 and S3, I learned how compute and storage interact. EC2 runs applications, while S3 stores the data they rely on. This combination is at the heart of cloud technology, and understanding it gave me a solid foundation for the more advanced topics that will come later, such as networking, automation, and security.

## ✔️ **Key Skills Learned This Week**

* Launched and managed Amazon EC2 instances
* Connected to servers using SSH
* Worked with instance types, key pairs, and security groups
* Created and managed S3 buckets
* Uploaded, downloaded, and organised objects in S3
* Learned how compute (EC2) and storage (S3) work together
* Gained hands-on experience with real AWS cloud resources

# 💾 Week 4 — Storage Services: S3, EBS, and EFS 

In Week 4 of the AWS re/Start programme, I deepened my understanding of cloud storage by exploring how different AWS storage services work and why companies choose one type over another. This week helped me realise that “storage” in the cloud isn’t just about saving files — it’s about choosing the right type of storage for the right task, depending on performance, durability, accessibility, and cost. I began by expanding my knowledge of Amazon S3.

## Learnt about the following:
- The basics of storing objects, but this week I went further into advanced features like versioning and lifecycle rules. Versioning allowed me to keep multiple versions of the same file, which is incredibly useful for protecting data from accidental deletion or overwriting. Lifecycle rules taught me how organisations control costs by automatically moving older files into cheaper storage classes. It showed me how smart, automated policies can balance cost efficiency with data protection. These features helped me understand that S3 is not just a storage space — it’s a powerful system designed to manage data throughout its entire lifecycle.
- I then explored Amazon EBS, which provides block-level storage for EC2 instances. This type of storage behaves more like a traditional hard drive connected to a computer. I learned how EBS volumes attach to servers, how they store operating systems or application data, and how snapshots can be created to back up an entire volume at any moment. Creating snapshots was an important skill because it demonstrated how companies protect their critical data and ensure that servers can be restored quickly after failures or maintenance. Working with EBS also helped me understand real-world scenarios, such as increasing volume sizes, replacing volumes, and maintaining data even when servers stop or fail.
- Amazon EFS, which provides shared storage that multiple servers can access at the same time. This concept was new to me because unlike EBS, which connects to a single server, EFS behaves like a shared folder that can be used by many EC2 instances simultaneously. This is extremely useful for applications that need to share files or maintain consistent data across multiple servers, such as web applications or content management systems. Exploring EFS helped me understand how cloud systems scale and how multiple servers can work together efficiently when they share the same data.

By the end of the week, I realised that cloud storage is far more flexible than traditional storage. Each service — S3, EBS, and EFS — solves a different problem, and understanding these differences gave me a clearer picture of how cloud architectures are built. Week 4 strengthened my skills in data management, backups, cost optimisation, and multi-server storage design. It also prepared me for future weeks where storage, compute, networking, and security come together to form complete cloud solutions.

# Week 5: Database & Analytics Services 🗃️📊

In Week 5 of the AWS re/Start programme, I shifted my focus from computing and storage to understanding how data is stored, retrieved, and analysed in the cloud. This week introduced me to databases and analytics services, and it helped me appreciate how important data is in every modern application.

## Learnt about the following:
- The difference between relational and non-relational databases. Relational databases, like those supported by Amazon RDS, organise information in tables, similar to a large spreadsheet where different pieces of data are connected through relationships. This design is ideal for applications that require structured information, such as financial systems, inventory tracking, or user account management. I practiced performing basic CRUD operations—creating, reading, updating, and deleting data—which showed me how applications interact with databases behind the scenes. Even though these actions were simple, they helped me see how real systems store and modify information every time a user performs an action.
- Learned about Amazon DynamoDB, which is AWS’s non-relational (NoSQL) database service. DynamoDB stores information in a more flexible way compared to relational databases, making it perfect for applications that need to handle large amounts of data quickly and at scale. I explored how DynamoDB tables work, how items are stored, and how data can be accessed efficiently. Using DynamoDB helped me understand why many modern, high-performance applications—such as gaming platforms and e-commerce websites—rely on fast, scalable NoSQL databases to handle millions of requests.
- Learning about AWS analytics tools such as Amazon Athena, Amazon QuickSight, and Amazon Redshift. These services showed me how businesses turn raw data into meaningful insights. I practiced uploading a dataset into Amazon S3 and then used Athena to run SQL queries directly on that data without needing to set up a traditional database. This was my first experience with serverless analytics, and it made me realise how powerful AWS can be for large-scale data processing. Exploring QuickSight gave me an understanding of how visual dashboards are created to help teams make informed decisions, while learning about Redshift introduced me to the idea of data warehouses—systems designed specifically for large-scale analytics.

By the end of the week, I gained a deeper understanding of how essential data is in cloud environments. Data isn’t just stored; it’s collected, processed, analysed, and used to guide decisions. This week helped me see how different AWS services work together—from storing information in RDS or DynamoDB to analysing it with Athena or QuickSight. It also made me more confident in handling data-driven tasks and prepared me for more advanced work in automation, networking, and application design. Week 5 showed me that behind every app, website, or system I use daily, there is a well-structured layer of data operations keeping everything running smoothly.


## Week 6: Networking & Content Delivery 🌐🚚

This week, I learned about how content like websites, videos, apps, and files are delivered to users over the internet quickly, securely, and reliably. The topic was Content Delivery and Networking, and at first, I didn’t fully understand why it mattered so much. But as the week went on, I began to realize just how important it is for any company or website that wants to serve users all around the world without delays or interruptions. In simple terms, the goal is to make sure that when someone clicks a website or opens an app, it loads fast—no matter where they are.

## Learnt about the following:
- **Amazon CloudFront**, which is a content delivery network (CDN). What that means is that it has servers all over the world, and instead of your content always coming from one central place, CloudFront delivers it from the closest location to the user. For example, if a website is based in South Africa, but someone in the U.S. wants to view it, CloudFront will serve the content from a nearby U.S. location instead of sending the request all the way to South Africa. This helps websites load faster and reduces internet traffic issues. It also helps protect websites against attacks and high traffic that could cause slowdowns.
- **Amazon Route 53** which is a scalable Domain Name System (DNS) web service. I learned that DNS works like a phone book for the internet. When someone types in a website like “www.example.com,” Route 53 helps find the right server that hosts that website. Without DNS, people would need to type in complicated IP addresses instead of simple website names. Route 53 also helps make sure that if one server goes down, the traffic is rerouted to another healthy one. This helps improve uptime and keeps services available at all times.

These services ensure that users across the globe can access websites, videos, or applications quickly, securely, and reliably. Even without a technical background, it’s easy to see the value: AWS helps businesses improve performance, reduce loading times, and stay available 24/7 — no matter where their customers are. This week gave us a solid foundation for understanding how modern websites and applications reach users efficiently through the cloud.

## Week 7: AWS Security Services & Best Practices 🛡️🔒
In Week 7 of the AWS re/Start programme, was all about learning how to protect information and manage things better in the cloud. At first, I was nervous because terms like "encryption" and "monitoring" sounded so technical, but as the days went on, things started making more sense.

## Learnt about the following:
- One of the first tools we explored was **AWS KMS**, which stands for Key Management Service. I learned that it helps to lock and unlock important information using something like a secret password (called a key). Just like I wouldn’t leave my house without locking the door, companies use KMS to lock up data, and only people with the right “key” can open it. It made me realize how important encryption is, especially when working with sensitive information like customer details.
This week was all about **networks**—the invisible systems that allow devices like computers, phones, and servers to communicate with each other. Before this, I didn’t realise how much goes on behind the scenes whenever we open a website or use an app. I learned that every device needs an **IP address**, which works like a home address so information can reach the right place. There are two types: **IPv4**, which is older and widely used, and **IPv6**, which is newer and gives more addresses for the growing number of devices.
- Then we moved on to **AWS CloudTrail**, which was like the CCTV of everything that happens in AWS. I now understand that every time someone makes a change—like deleting a file or creating a new server—it gets recorded. This helps companies track who did what, and when. I thought that was really smart because it keeps everyone accountable. Along with that, we used AWS Config, which is like having a daily report that shows if something in your environment has changed. For example, if a storage bucket was set to private and someone made it public, AWS Config would pick that up. I now appreciate how this helps organizations stay secure and make sure no one makes risky changes by accident.
- We also worked with **Amazon CloudWatch**, which helps you monitor how things are running in AWS—like whether a server is working too hard or if something has crashed. I didn’t know it was possible to be alerted automatically if something went wrong, but now I understand how helpful that is, especially when managing multiple applications. AWS Systems Manager was another cool tool. It lets you manage your computers (or instances, in cloud language) without having to log into each one. I thought that was powerful because you could update, fix, or control them all from one place.

Overall, Week 7 helped me see that cloud security isn’t just for experts—it’s about using the right tools and following smart practices. Even with no IT background, I started understanding how businesses keep their information safe and manage their cloud setups properly. I now feel more confident in learning and applying these tools, knowing they’re there to make cloud work more secure, organized, and easier to manage.

**Key Points:**

* Networks connect devices so they can communicate
* Every device has an IP address (IPv4 and IPv6)
* Subnets divide networks into smaller sections
* Public vs private IPs
* AWS VPC: my private cloud network
* Route Tables and Security Groups control traffic and security

