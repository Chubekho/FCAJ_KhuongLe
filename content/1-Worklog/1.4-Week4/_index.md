---
title: "Worklog Week 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 objectives:
* Master IP addressing concepts and hands-on deploy an enterprise-standard virtual network infrastructure on Amazon VPC.
* Deploy an application server (EC2) into the newly built VPC, applying the IAM Role learned in Week 3 to securely grant S3 access.
* Get familiar with the AWS Cloud9 cloud development environment, preparing the tooling for upcoming practice weeks.

### Tasks to complete this week:
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Tue | - Learn the theory behind Classless Inter-Domain Routing (CIDR) and Subnet Masks. <br> - Analyze Variable Length Subnet Mask (VLSM) subnetting techniques. | 12/05/2026 | 12/05/2026 | [Introduction to Amazon VPC](https://000003.awsstudygroup.com/1-introduce/) |
| Thu | - Practice: Create a new Amazon VPC (not using the Default VPC). <br> - Set up Public and Private Subnets based on VLSM calculations. <br> - Configure the Internet Gateway (IGW) and Route Tables to enable outbound internet traffic. | 14/05/2026 | 14/05/2026 | [Environment Preparation](https://000003.awsstudygroup.com/3-prerequisite/)|
| Fri | - **Practice:** Launch an EC2 instance in the Public Subnet of the newly created VPC. <br> - Connect via SSH using a Keypair (.pem), handling certificate file permissions (chmod 400). | 15/05/2026 | 15/05/2026 | [Deploying an Amazon EC2 Instance](https://000003.awsstudygroup.com/4-createec2server/) |
| Sat | - **Practice:** Attach the IAM Role created in Week 3 to the EC2 instance (Instance Profile), verifying that EC2 can access S3 without declaring an Access Key/Secret Key. <br> - Learn about and set up the Cloud9 IDE development environment. | 16/05/2026 | 16/05/2026 | [Granting Applications Access to AWS Services via IAM Role](https://000048.awsstudygroup.com/) |

### Results achieved in Week 4:
* Gained a deep understanding of IP planning:
  * Clearly distinguished Network ID and Host ID through CIDR ranges.
  * Calculated VLSM to divide subnets of varying sizes, avoiding wasted IP ranges.
* Designed and deployed a complete standalone Amazon VPC:
  * A Public Subnet (routed to the Internet via the IGW) and a Private Subnet (isolated, with no direct outbound route).
  * A separate Route Table for each subnet type, understanding the routing mechanism that separates public and private zones.
* Successfully launched and ran an EC2 server inside the newly established VPC:
  * Connected via SSH using a Keypair, resolving the common permission error when using a .pem file (chmod 400).
* Successfully applied an IAM Role (Instance Profiling) to a real EC2 instance:
  * Attached the Role directly to EC2, confirming normal S3 access with no Access/Secret Key stored on the machine.
  * Verified the security theory learned in Week 3 through concrete practice — no longer just theory.
* Successfully set up the AWS Cloud9 development environment:
  * Wrote and ran commands directly in the browser, with no need for a local setup — ready for the coding practice in the coming weeks.