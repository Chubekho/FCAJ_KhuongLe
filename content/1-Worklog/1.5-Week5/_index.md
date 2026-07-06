---
title: "Worklog Week 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 objectives:
* Complete the remaining foundational services in the "Explore AWS Services" group: static storage with S3, managed database with RDS, system monitoring with CloudWatch, and automatic scaling with EC2 Auto Scaling.
* Practice Hybrid Cloud connectivity (simulating on-premise ↔ cloud) via VPC Endpoint and DNS Resolver.

### Tasks to complete this week:
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Learn Amazon S3: object storage, storage classes, versioning. <br> - **Practice:** Create a bucket, enable Static Website Hosting, configure a public-read Bucket Policy, deploy a static HTML page, and access it via the S3 endpoint. | 18/05/2026 | 18/05/2026 | [Hosting a Static Website with Amazon S3](https://000057.awsstudygroup.com/) |
| Tue | - Learn Amazon RDS: managed relational database, compared with self-managing a DB on EC2 (backup, patching, Multi-AZ). <br> - **Practice:** Launch an RDS PostgreSQL instance in a Private Subnet, configuring a Security Group so only EC2 within the VPC can access it. | 19/05/2026 | 19/05/2026 | [Creating a Database on Amazon Relational Database Service (Amazon RDS)](https://000005.awsstudygroup.com/) |
| Wed | - Learn Amazon CloudWatch: Metrics, Logs, Alarms, Dashboard. <br> - **Practice:** Create a CloudWatch Alarm to monitor EC2 CPUUtilization, connecting an SNS Topic to receive email alerts when the threshold is exceeded. | 20/05/2026 | 20/05/2026 | [Building a Monitoring Dashboard with Amazon CloudWatch](https://000008.awsstudygroup.com/) |
| Thu | - Learn EC2 Auto Scaling: Launch Template, Auto Scaling Group (ASG), Target Tracking Policy. <br> - **Practice:** Create a Launch Template from an existing AMI, create an ASG that scales based on average CPU %, and verify scale-out/scale-in behavior. | 21/05/2026 | 21/05/2026 | [Automatically Scaling an Application with Amazon EC2 Auto Scaling](https://000006.awsstudygroup.com/) |
| Fri | - Practice the **"Securing Hybrid Access to S3 with VPC Endpoint"** lab: build 2 VPCs (Cloud & On-Prem), create a Gateway Endpoint and an Interface Endpoint to S3, simulate a Site-to-Site VPN connection, and verify DNS resolution from the on-premise side. | 22/05/2026 | 22/05/2026 | [Setting up Hybrid DNS with Route 53 Resolver](https://000010.awsstudygroup.com/) |

### Results achieved in Week 5:
* Successfully deployed a static website on S3:
  * Understood how Bucket Policy permissions differ from IAM User/Role permissions.
* Successfully launched and connected to RDS PostgreSQL from EC2 within the same VPC:
  * Understood why the database should sit in a Private Subnet rather than a Public Subnet, to reduce the attack surface.
* Set up a basic monitoring flow: CloudWatch Alarm → SNS → Email:
  * Understood the role of observability in production operations, rather than relying on manual checks.
* Understood and practiced the Auto Scaling mechanism:
  * The system automatically adds/removes instances based on real load, avoiding wasted resources during low traffic and overload during peak traffic.
* Completed the VPC Endpoint/Hybrid DNS lab:
  * Distinguished a Gateway Endpoint (routed via a route table, used for S3/DynamoDB) from an Interface Endpoint (using an ENI + PrivateLink, used for most other AWS services).
  * Understood how an on-premise data center can privately access S3 without going through the public internet.
* Began forming a clearer picture of how these components would be used in a real production system (S3 for file storage, RDS for data, Auto Scaling + CloudWatch for the application tier) — laying the groundwork for designing the infrastructure of the workshop project in the coming weeks.