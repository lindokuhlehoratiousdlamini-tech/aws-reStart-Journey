# 🌐 AWS Networking Notes

Networking is how computers and systems communicate with each other. But in AWS is how resources talk to each other inside the cloud AND outside (internet).

AWS gives tools to:
- Isolate networks
- Control traffic
- Secure communication
- Connect to the internet

Key AWS Networking Services Summary

| **Service**            | **Type**            | **Best For**                                      |
|------------------------|----------------------|---------------------------------------------------|
| Amazon VPC             | Virtual Network      | Creating isolated networks in AWS                 |
| Subnets                | Network Segments     | Splitting VPC into public/private sections        |
| Internet Gateway (IGW) | Internet Access      | Allowing public subnets to communicate online     |
| NAT Gateway            | Private Connectivity | Letting private subnets access the internet safely |
| Route Tables           | Routing Control      | Managing traffic paths inside the VPC             |
| Security Groups        | Instance Firewall    | Controlling inbound/outbound traffic to instances |
| NACLs                  | Subnet Firewall      | Additional subnet-level traffic control           |
| VPC Peering            | VPC Connection       | Connecting two VPCs privately                     |
| AWS Transit Gateway    | Hub Networking       | Managing multiple VPCs and on-prem networks       |
| AWS Direct Connect     | Dedicated Connection | High-speed private link to on-premises networks   |
| Elastic Load Balancer  | Traffic Distribution | Distributing traffic across multiple EC2 servers  |
| Route 53               | DNS Service          | Domain names, routing policies, health checks     |

# 🧠 What I Learned From AWS Networking Labs

✔ How to create and configure a VPC
Choose CIDR block

Add subnets

Attach an Internet Gateway

Modify route tables

 Difference between public and private subnets
Public = reachable from the internet

Private = isolated from the internet

 How resources communicate
Routing rules

Security Groups (instance level)

NACLs (subnet level)

How to secure a network
Restrict inbound access

Use NAT for secure outbound traffic

Control traffic using firewall rules

 How AWS DNS (Route 53) works
Domain registration

Health checks

Routing policies (weighted, latency, failover)

# 📝 My Takeaways from AWS Networking Labs
- I learned how AWS uses VPCs to create isolated virtual networks where I can launch and secure my cloud resources.
- I now understand the difference between public and private subnets, and when to place resources in each one.
- I gained hands-on practice attaching an Internet Gateway to allow public traffic and using a NAT Gateway to give private resources safe outbound internet access.
- I learned how route tables work and how routing determines where traffic flows inside a VPC.
- I became more comfortable working with Security Groups and NACLs, and I understand how they control inbound and outbound traffic at different levels.
- I can now explain the difference between stateful firewalls (Security Groups) and stateless firewalls (NACLs).
- I learned how AWS networking services like VPC Peering, Transit Gateway, and Direct Connect are used to connect different networks together.

