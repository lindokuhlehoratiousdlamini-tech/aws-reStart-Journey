## Design a 3D Architecture on AWS 

# 🚀 Project Summary  

I am part of a startup team building a next-generation 3D e-commerce web application that will transform how customers shop online. Our platform allows users to interact with 3D models of products such as furniture, gadgets, and fashion items before making a purchase. With millions of users expected globally, my responsibility as a Cloud Practitioner is to design a cloud architecture on AWS that ensures the platform is fast, highly available, secure, and cost-efficient.  

To achieve this, I designed the architecture with the following AWS services:  

- **Amazon S3** for storing 3D assets, ensuring durability and scalability.  
- **Amazon CloudFront** for global content delivery, reducing latency and improving performance.  
- **EC2 and AWS Lambda** for backend compute, balancing flexibility with serverless efficiency.  
- **Amazon RDS and DynamoDB** for managing product and customer data, combining relational and NoSQL capabilities.  
- **Elastic Load Balancer (ELB)** to distribute traffic evenly across servers for fault tolerance.  
- **Amazon Route 53** for domain management and DNS routing.  
- **CloudWatch and Trusted Advisor** for monitoring, optimization, and cost control.  
 ....and many other more 

This architecture meets the critical requirements:  
- **High Availability** through load balancing, failover, and distributed infrastructure.  
- **Scalability** with auto-scaling groups and serverless functions to handle unpredictable traffic spikes.  
- **Performance** by leveraging CloudFront and optimized storage for fast 3D rendering.  
- **Security** by following AWS best practices, including IAM, encryption, and monitoring.  
- **Cost Optimization** through managed services, auto-scaling, and proactive monitoring.  

# Project Walkthrough 

***1. Design the Architecture***

- We used a diagramming tool Lucidchart so we can show you how our serivices interact with each other.
- We incorporate AWS services such as: 
▪ Amazon S3 for 3D asset storage 
▪ CloudFront for content delivery 
▪ EC2 / AWS Lambda for backend compute 
▪ RDS / DynamoDB for product and customer data 
▪ Elastic Load Balancer (ELB) for traffic distribution 
▪ Route 53 for domain managemen
and many other more

***2. Explain Your Choices*** 
o We wrote a brief document explaining: 
▪ Why you chose each AWS service. 
▪ How your architecture meets each of the 5 requirements. 
▪ Any design trade-offs or challenges.

# 3D Architecture Model 

![Archictecture](https://github.com/user-attachments/assets/af02eb7a-eb7e-4cc7-8fb9-45fa8275cd13)

The diagram shows an AWS cloud architecture that handles requests from mobile and web clients through several integrated services.

Here's a breakdown of the flow:

1. Client requests – Mobile and web clients connect to the internet. The web client uses Route 53 (DNS) to route traffic to CloudFront (CDN) or directly to the Web Application Firewall (WAF).

2. Edge security & delivery – CloudFront serves content and forwards requests through the WAF for protection. The WAF filters traffic before it hits the application.

3. Application hosting – The filtered traffic goes to Amplify Hosting, which serves the frontend. The backend API is exposed via Amazon API Gateway linked to App Runner (containerized app) protected by Shield (DDoS protection).

4. Data caching & processing – API requests hit ElastiCache for fast data retrieval. Lambda functions handle small tasks, interacting with S3 (storage), DynamoDB (catalog), and a PostgreSQL database (orders/users). Amazon SQS queues messages between Lambda and services, with KMS managing encryption.

5. Data & secrets management – Secrets Manager secures database credentials. PostgreSQL and DynamoDB store application data.

6. Monitoring & cost – CloudWatch monitors the environment, while Cost Explorer tracks spending.
# 🌟Takeaways  

- I learned that **user experience must come first**—fast, smooth 3D interactions are critical for customer satisfaction.  
- I realized the importance of **high availability**, and how redundancy, load balancing, and failover mechanisms keep the platform reliable 24/7.  
- I saw how **scalability is essential**; auto-scaling and serverless compute allow the system to handle unpredictable traffic spikes without over-provisioning.  
- I understood that **security has to be built in from the start**, by following AWS best practices like IAM, encryption, and monitoring.  
- I discovered that **cost efficiency is achievable** by using managed services, monitoring tools, and avoiding unnecessary resources.  
- I appreciated how each AWS service plays a **specific role** in meeting business and technical requirements, from S3 for storage to CloudFront for global delivery.  
- I recognized that **design trade-offs are inevitable**—balancing performance with cost, or flexibility with simplicity, is part of cloud architecture design.  
# Team Members & Roles 
Lindokuhle.D - Reasearch & Documentation 

Chriswell.M - Reasearch & Documentation 

Onnalerona.J.M - Reasearch & Documentation 

Brite.S - Designing the Architecture 

Nayana.M - Designing the Architecture 
