# Compute Lab: EC2 Launch
## Objectives
This lab is about launching, resizing, managing and monitoring an Amazon EC2 instance on AWS

## Tasks
- Launching EC2 instance - I created a new EC2 instance named Web Server. I chose Amazon Linux 2 AMI and t3.micro instance type.
- Monitor your instance - I checked CPU usage and system status in the EC2 Mointoring tab to make sure the instance was running correctly.
- Update security group and access the web server - I added an inbound rule for HTTP (port 80) from anywhere so I could acceess the web server
- Resize instance and EBS volume - I stopped the instance, changed the type to t3.small and I increased the volume from 8 GB to 10 GB
- Test termination protection - I turned on the termination protection, tried to delete the instance and confirmed AWS blocked the action until i disabled it.
## Challenges
- I did not face any challenges during this lab, everything was straight forward.
## Takeaways
- Make sure your security group has the correct inbound rules
- Enable the termiantion protection to avoid accidentally deleting instances
## Screenshots
