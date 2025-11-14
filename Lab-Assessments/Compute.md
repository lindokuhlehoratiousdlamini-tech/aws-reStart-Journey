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
- <img width="1366" height="728" alt="1" src="https://github.com/user-attachments/assets/145747d1-a842-48e9-96c0-33cc47b5843b" />

- <img width="1366" height="728" alt="2" src="https://github.com/user-attachments/assets/d817ffdd-0667-4f06-8810-5685aadf507a" />

-<img width="1366" height="728" alt="3" src="https://github.com/user-attachments/assets/a2bdc6e2-069a-4d4e-a55d-ce2826d1c849" />
-<img width="1366" height="728" alt="4" src="https://github.com/user-attachments/assets/fe8ed434-52ca-45ce-9606-9731eef93d0f" />
-<img width="1366" height="728" alt="4a instance type" src="https://github.com/user-attachments/assets/7bae5d09-3e77-497d-b725-6289380e0757" />
-<img width="1366" height="728" alt="5" src="https://github.com/user-attachments/assets/bbd40e24-2b01-4492-b2eb-c3cfafc2919a" />
- <img width="1366" height="728" alt="6" src="https://github.com/user-attachments/assets/069ab7d6-fb86-4c6c-9c1e-6ef72886c096" />
- <img width="1366" height="728" alt="7" src="https://github.com/user-attachments/assets/dbe23a9f-da78-40cb-ba8e-c31381e436da" />
- ![8](https://github.com/user-attachments/assets/2e3a6b14-b93f-4ad4-84e5-a0139bfc44e9)







