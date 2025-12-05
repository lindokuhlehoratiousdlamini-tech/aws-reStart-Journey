
## 📦 AWS Storage Notes

Storage refers to the technology and services used to save digital information — such as files, images, videos, logs, backups, or databases — in a secure and accessible way.

# 🧠 What I Learned (Common Lessons From AWS Labs)
**Understanding differences between S3, EBS, and EFS**

S3 = object storage (scalable, inexpensive, web-scale)

EBS = block storage for EC2 instances

EFS = shared file system for Linux-based workloads

**How to create, attach, and work with EBS volumes**

Create a volume

Attach to an EC2 instance

Format and mount the volume

Resize and take snapshots

**How to upload and manage data in S3**

Create buckets

Upload/download objects

Manage permissions

Configure versioning and lifecycle rules

**How storage aligns with workload requirements**

Use EFS for shared access

Use EBS for operating systems and databases

Use S3 for backups, logs, and static content

# 📝 Why AWS Storage Matters

Storage is one of the core pillars of cloud computing. It determines:

How data is stored

How fast it can be accessed

How secure and durable it is

How much it costs

Knowing the correct storage service helps make systems more reliable, scalable, and efficient.

# Key AWS Storage Services Summary

| **Service**        | **Type**             | **Best For**                         |
|--------------------|----------------------|--------------------------------------|
| Amazon S3          | Object Storage       | Backups, static websites, logs       |
| Amazon EBS         | Block Storage        | EC2 root volumes, databases           |
| Amazon EFS         | File Storage         | Shared file storage                   |
| S3 Glacier         | Archival Storage     | Long-term cold storage                |
| Storage Gateway    | Hybrid Storage       | On-premises + cloud backups           |
| RDS / Aurora       | Database Storage     | Relational data                       |
| DynamoDB           | NoSQL Storage        | Key-value and document workloads      |

# ✅ My Takeaways
- I now understand the difference between object, block, and file storage.
- S3 is great for flexible, everyday storage and website hosting.
- EBS is like a hard drive for EC2 – perfect for apps that need fast access to data.
- EFS is useful when multiple EC2s need to share files.
- AWS has storage options for every need — from fast-access to deep archiving.
- Learning how to use them made me feel more confident in building cloud solutions.
