
### 1. What is EC2?
- Elastic Compute Cloud = scalable virtual servers in the cloud.
- Launch instances (VMs), choose OS, config, storage, networking, security.

### 2. Key Components
- Instance types: Combo of CPU, RAM, storage, networking. Families include:
    - General purpose (t2, t3, m5, m6g...)
    - Compute optimized (c5, c6g...)
    - Memory optimized (r5, r6g, x1...)
    - Storage optimized (i3, d2...)
- AMI (Amazon Machine Image): Template for OS + apps. Choose from AWS, market, or custom.
- Security Groups: Virtual firewalls controlling inbound/outbound traffic.
- Key pairs: SSH access. Download .pem file (Linux/Mac) or .ppk (Windows).

### 3. Storage Options
- Instance Store: Ephemeral, high IOPS, attached to instance physically.
- EBS (Elastic Block Store): Persistent block storage volumes.
    - Types: gp2, gp3, io1, io2, st1, sc1.
- Snapshots: Backups stored in S3.

### 4. Pricing Models
1. On-Demand: Pay per hour/second used. No commitment.
2. Reserved Instances: 1–3 year commitment. Up to 75% off.
3. Spot Instances: Bid for unused capacity. Up to 90% off, but can be terminated with 2-min notice.
4. Savings Plans: Flexible pricing based on usage commitment.

### 5. Auto Scaling & Load Balancing
- Auto Scaling: Maintain performance by scaling instances across AZs.
- ELB (Elastic Load Balancer): Distributes traffic. Types: ALB, NLB, CLB.

### 6. Networking
- VPC: Isolated network. Subnets (public/private), route tables, internet/NAT gateways.
- Elastic IP: Static public IP.

### 7. Monitoring & Security
- CloudWatch: Metrics, alarms, logs.
- IAM Roles: Grant permissions to instances securely.

### 8. Quick Commands (CLI)
- Launch instance: aws ec2 run-instances --image-id ami-xxxx --count 1 --instance-type t2.micro
- List instances: aws ec2 describe-instances
- Terminate: aws ec2 terminate-instances --instance-ids i-xxxxxx

### 9. Best Practices
- Use IAM roles for least privilege access.
- Tag resources for cost tracking.
- Regularly back up EBS volumes.
- Harden security groups (allow minimal ports).


### AWS Responsibility
- Hypervisor, physical hosts, global infrastructure (regions, AZs, edge locations)
- Host OS, virtualization layer patching and maintenance
- Network & power infrastructure, cooling, physical security

### Customer Responsibility
- OS & application configs, patching, updates
- Security groups, NACLs, firewalls, IAM policies
- Data encryption (in transit + at rest), backups
- Instance-level monitoring with CloudWatch, logs, compliance

### Other Things to Keep Handy
- Key pairs — you manage private keys securely; lose ‘em, you lose access.
- Elastic IPs — stick a static public IP to your instance; remember it’s limited per region.
- AMI management — keep AMIs updated and secured; use AWS Marketplace or custom baked images.
- Cost control — leverage CloudWatch + Budgets; stop or terminate idle instances.

