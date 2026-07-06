---
title: "Worklog Week 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 objectives:
* Learn the Security & Reliability service group: permission limiting, application protection, data encryption, system backup.
* Get familiar with Infrastructure as Code (IaC) via AWS CloudFormation — instead of manual Console operations.

### Tasks to complete this week:
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Learn IAM Permission Boundary: the maximum permission ceiling a User/Role can have, regardless of what policies are attached. <br> - **Practice:** Create a Permission Boundary, attach it to an IAM User, and verify the user cannot self-escalate permissions beyond the boundary. | 08/06/2026 | 08/06/2026 | [Limiting User Permissions with IAM Permission Boundary](https://000030.awsstudygroup.com) |
| Tue | - Learn AWS WAF: protecting web applications from common vulnerabilities (SQL Injection, XSS), rate limiting. <br> - **Practice:** Attach a WAF WebACL to an Application Load Balancer, create a rule to block SQL Injection and limit request rates. | 09/06/2026 | 09/06/2026 | [Protecting Applications and APIs with AWS WAF](https://000026.awsstudygroup.com) |
| Wed | - Learn AWS KMS: encryption key management, envelope encryption. <br> - **Practice:** Create a Customer Managed Key, encrypt an object in S3 using a custom key instead of the AWS default key. | 10/06/2026 | 10/06/2026 | [Managing Encryption Keys with AWS KMS](https://000033.awsstudygroup.com) |
| Thu | - Learn AWS Backup: automated backup plans, retention policy. <br> - **Practice:** Create a Backup Plan to automatically back up RDS daily, and perform a test restore from a backup. | 11/06/2026 | 11/06/2026 | [Implementing a System Backup Plan with AWS Backup](https://000013.awsstudygroup.com) |
| Fri | - Learn AWS CloudFormation: Infrastructure as Code, YAML/JSON templates, the Stack concept. <br> - **Practice:** Write a template to create a VPC + EC2 using CloudFormation, comparing it with manual Console operations. | 12/06/2026 | 12/06/2026 | [Getting Started with Infrastructure as Code using AWS CloudFormation](https://000037.awsstudygroup.com) |

### Results achieved in Week 8:
* Understood and applied the least-privilege principle at a deeper layer than ordinary IAM Policies:
  * Permission Boundary caps the maximum permission "ceiling," preventing escalation even if someone accidentally attaches an overly broad policy.
* Deployed an application protection layer at the network level with AWS WAF:
  * Understood the mechanism of managed rules (blocking common exploits) combined with custom rules (rate limiting tailored to specific needs).
* Mastered the concept of data encryption with KMS:
  * Distinguished between AWS-managed keys and Customer-managed keys — and when independent control over a key's lifecycle is needed.
* Built an automated backup strategy instead of relying on manual backups:
  * Understood retention policy and the importance of periodically testing restores (an untested backup is not a trustworthy one).
* Got familiar with the Infrastructure as Code mindset:
  * Infrastructure defined as files that can be version-controlled, reviewed, and reused — a stark contrast to error-prone, hard-to-reproduce manual operations.
  * This is an important foundational mindset for managing the infrastructure of the workshop project in the coming weeks, even if the specific IaC tooling differs (scripts/CLI instead of CloudFormation).