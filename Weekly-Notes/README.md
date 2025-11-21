# AWS re/Start Programme Weekly Notes 🚀

Welcome to my weekly notes for the AWS re/Start programme! Here I'll document my learning journey, reflections, and hands-on experiences. Let's get cloud-ready! ☁️✨

# 🌱 Week 1 — Introduction & Foundations

In the first week of the AWS re/Start programme, I focused on building the essential foundations needed to understand computers, operating systems, and the cloud. This was my starting point, and even though the concepts were basic, they were important for everything I will learn later in the programme.

I began by meeting my instructors and fellow learners, and I learned how the programme is structured and what the long-term goals are. This helped me understand the journey ahead and what skills I’m expected to develop by the end. I also set up my learning environment, which included preparing my computer, creating accounts, and joining collaboration platforms like Slack/Teams so I can communicate and work with others throughout the course.

A major focus of Week 1 was:
- **digital and computer fundamentals**. I learned how operating systems work, what file systems are, and how computers organise data internally. Understanding these basics helped me see what’s happening “behind the scenes” on a computer and why certain actions matter. This foundational knowledge is especially important in cloud computing, where server management and system behaviour are part of everyday tasks.

One of the biggest skills I developed this week was using the:
- **Linux command line**. I practiced essential terminal commands such as navigating directories, listing files, creating folders, and understanding how the Linux file system is structured. At first, typing commands felt unfamiliar, but I quickly learned how powerful and efficient the terminal is. Because cloud servers often do not have a graphical interface, becoming comfortable with the command line is a crucial step toward working confidently in AWS later on.

Overall, Week 1 gave me a strong start. I built confidence with computers, learned how to use the terminal, and prepared my environment for the hands-on cloud training that comes later. Even though these were introductory skills, they form the foundation for everything else I will do in the cloud — from managing servers to automating tasks and deploying applications. This week set the groundwork for my entire cloud learning journey.

# ☁️ Week 2 — Cloud Concepts & AWS Introduction 

In Week 2 of the AWS re/Start programme, I moved from basic computer fundamentals into understanding what **cloud computing** actually is and why it matters in the modern world. This week helped me build a clear picture of how the cloud works, how AWS fits into it, and why businesses rely on these technologies.

I began by learning the core idea behind cloud computing: instead of companies buying and maintaining their own physical computers and servers, they can rent computing power, storage, and services over the internet. This simple concept is the foundation of the entire cloud industry. I explored key cloud models — public, private, and hybrid — and learned how each one is used depending on a company’s needs. This helped me understand that the cloud is flexible and can support both small startups and large enterprises with different requirements.

I also learned about the **AWS global infrastructure**, which includes:
- Regions
- Availability Zones
- data centers located all around the world.

AWS divides its global network in a way that helps customers build applications that are fast, secure, and reliable. A “Region” is a specific geographic location, and inside each Region are multiple “Availability Zones,” which are separate data centers designed for high availability. Understanding this structure helped me see how AWS provides resilience: if something fails in one location, the system can continue working from another.

Another important part of Week 2 was learning why companies move to the cloud. I explored the benefits of cloud computing, such as reduced costs, faster deployment, easier scaling, and improved reliability. Instead of waiting days or weeks to set up physical hardware, the cloud allows resources to be created in minutes. This efficiency is a major reason cloud skills are in high demand.

By the end of the week, I could clearly explain what the cloud is, how AWS is built, and why organisations trust cloud services to run their applications. Week 2 gave me the conceptual foundation I need for the more hands-on AWS work that comes later in the programme. It helped me shift my mindset from thinking of computers as physical machines to seeing them as flexible, on-demand, internet-based resources — which is the core of modern cloud computing.
 
## Week 3: AWS Core Services 🛠️

In Week 3 of the AWS re/Start programme, I moved from learning cloud concepts into working directly with AWS services. This was my first real hands-on experience in the cloud, and it helped me understand how companies actually run applications using AWS. I focused mainly on **EC2**, which provides virtual servers, and **S3**, which stores data in the cloud. These two services form the foundation of most cloud environments, so getting comfortable with them was an important part of my progress.

I started by learning about:
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

## Week 4: Storage Services 🗄️

- *Here is **Week 4** written in **long, fluent paragraphs**, suitable for GitHub, using “I”, with no bullets — just a smooth, detailed explanation.

---

# 💾 Week 4 — Storage Services: S3, EBS, and EFS (My Learning Summary)

In Week 4 of the AWS re/Start programme, I deepened my understanding of cloud storage by exploring how different AWS storage services work and why companies choose one type over another. This week helped me realise that “storage” in the cloud isn’t just about saving files — it’s about choosing the right type of storage for the right task, depending on performance, durability, accessibility, and cost. I began by expanding my knowledge of Amazon S3. Previously, I learned the basics of storing objects, but this week I went further into advanced features like versioning and lifecycle rules. Versioning allowed me to keep multiple versions of the same file, which is incredibly useful for protecting data from accidental deletion or overwriting. Lifecycle rules taught me how organisations control costs by automatically moving older files into cheaper storage classes. It showed me how smart, automated policies can balance cost efficiency with data protection. These features helped me understand that S3 is not just a storage space — it’s a powerful system designed to manage data throughout its entire lifecycle.

I then explored Amazon EBS, which provides block-level storage for EC2 instances. This type of storage behaves more like a traditional hard drive connected to a computer. I learned how EBS volumes attach to servers, how they store operating systems or application data, and how snapshots can be created to back up an entire volume at any moment. Creating snapshots was an important skill because it demonstrated how companies protect their critical data and ensure that servers can be restored quickly after failures or maintenance. Working with EBS also helped me understand real-world scenarios, such as increasing volume sizes, replacing volumes, and maintaining data even when servers stop or fail.

Finally, I learned about Amazon EFS, which provides shared storage that multiple servers can access at the same time. This concept was new to me because unlike EBS, which connects to a single server, EFS behaves like a shared folder that can be used by many EC2 instances simultaneously. This is extremely useful for applications that need to share files or maintain consistent data across multiple servers, such as web applications or content management systems. Exploring EFS helped me understand how cloud systems scale and how multiple servers can work together efficiently when they share the same data.

By the end of the week, I realised that cloud storage is far more flexible than traditional storage. Each service — S3, EBS, and EFS — solves a different problem, and understanding these differences gave me a clearer picture of how cloud architectures are built. Week 4 strengthened my skills in data management, backups, cost optimisation, and multi-server storage design. It also prepared me for future weeks where storage, compute, networking, and security come together to form complete cloud solutions.

---

Do you want **Week 5** next in the same long-paragraph style?
�

## Week 5: Database & Analytics Services 🗃️📊

- **Databases**
  - Introduction to relational (RDS) & non-relational (DynamoDB) databases 🧱
  - Performed CRUD operations with AWS databases ✍️
  - Learned backup, restore, and security basics for databases 🔐
- **Analytics**
  - Explored AWS analytics tools (Athena, QuickSight, Redshift) 📈
  - Practiced querying datasets and generating reports 🧐

## Week 6: Networking & Content Delivery 🌐🚚

- **Networking**
  - Learned about VPCs, subnets, route tables, and security groups 🌉
  - Configured internet gateways and NAT gateways 🌏
  - Hands-on with IP addressing and network ACLs 🗺️
- **Content Delivery**
  - Explored CloudFront for content distribution 🚀
  - Concepts of latency, edge locations, and caching ⚡

## Week 7: AWS Security Services & Best Practices 🛡️🔒

- **Security Fundamentals**
  - Learned IAM (Identity & Access Management) users, groups, and policies 🧑💼
  - Explored Multi-Factor Authentication (MFA) 🔑
  - Worked with AWS security services (KMS, GuardDuty, CloudTrail, Inspector) 👮
  - Reviewed AWS shared responsibility model and best practices 📚
