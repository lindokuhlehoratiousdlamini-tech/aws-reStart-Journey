
## 📦 AWS Storage Services Notes

# 1. Amazon S3 (Simple Storage Service)
- Object storage service used to store and retrieve any amount of data.
- Stores data in "buckets".
- Commonly used for backups, hosting static websites, and data archiving.
- Supports versioning and encryption.

Example use case: Hosting a static website or storing user-uploaded files.

# 2. Amazon EBS (Elastic Block Store)
- Block-level storage for EC2 instances.
- Data persists independently from the instance.
- Good for use cases like databases and file systems.

Example use case: Attaching to a Linux server to store application files.

# 3. Amazon EFS (Elastic File System)
- Scalable file storage for use with EC2.
- Automatically grows and shrinks as files are added/removed.
- Shared across multiple EC2 instances.

Example use case: Shared network storage between multiple app servers.

# 4. Amazon Glacier / S3 Glacier
- Long-term, low-cost storage for archiving data.
- Retrieval takes time (minutes to hours), but very cost-efficient.

Example use case: Backing up company data you rarely access.

✅ My Takeaways
- I now understand the difference between object, block, and file storage.
- S3 is great for flexible, everyday storage and website hosting.
- EBS is like a hard drive for EC2 – perfect for apps that need fast access to data.
- EFS is useful when multiple EC2s need to share files.
- AWS has storage options for every need — from fast-access to deep archiving.
- Learning how to use them made me feel more confident in building cloud solutions.
