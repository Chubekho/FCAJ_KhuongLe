---
title: " Worklog Week 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 objectives:
* Complete the process of earning Credit from the AWS Free Tier program.
* Set up cost alerts and apply the highest account security standards (IAM User, MFA).
* Expand IAM knowledge: from granting permissions to people (User) to granting permissions directly to AWS resources (Role) — an important security foundation to be applied in practice next week.

### Tasks to complete this week:
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Tue | - **Practice Task 3 (Credit):** Launch a static S3 Bucket. <br> - **Practice Task 4 (Credit):** Create a basic RDS Database. <br> - **Practice Task 5 (Credit):** Create a simple Lambda function. | 05/05/2026 | 05/05/2026 | [AWS Free Tier Guide](https://000001.awsstudygroup.com/vi/) |
| Thu | - Practice managing AWS spending with the AWS Budgets service. <br> - Manage access permissions with AWS IAM (creating a Group and an Admin User). <br> - Set up security for the IAM User (Password Policy, MFA). | 07/05/2026 | 07/05/2026 | [AWS Budgets](https://000007.awsstudygroup.com/vi/) <br> [AWS IAM](https://000002.awsstudygroup.com/vi/) |
| Sat | - Learn about the risk of storing hardcoded Access Keys/Secret Keys on a server or in source code. <br> - Learn the IAM Role concept: granting permissions directly to an AWS resource instead of assigning static credentials. <br> - **Practice:** Create an IAM Role that allows access to S3, and learn the temporary-credentials mechanism behind an Instance Profile. | 09/05/2026 | 09/05/2026 | [AWS IAM](https://000002.awsstudygroup.com/vi/) |

### Results achieved in Week 3:
* Fully completed all 5 "Money-Making" Tasks, officially collecting the entire $200 Credit for use in advanced labs:
  * S3: understood the concept of object storage, buckets, and basic object upload/management.
  * RDS: launched a database instance and verified a basic connection.
  * Lambda: wrote and deployed a simple function, understanding the serverless model (no server management required).
* Set up cost alerts with AWS Budgets:
  * Configured alert thresholds based on a percentage of the planned budget.
  * Connected email notifications to trigger when the threshold is exceeded, avoiding unexpected charges.
* Successfully set up a secure AWS account with an IAM Admin User (retiring use of the Root account):
  * Created an IAM Group to assign permissions by role, instead of granting permissions individually to each User.
  * Applied a Password Policy requiring a password change on first login.
  * Enabled MFA (Virtual MFA Device) for the Admin account.
* Understood why storing hardcoded Access Keys/Secret Keys is a major security risk:
  * Real-world risks: keys leaked through Git commits, application logs, or public config files.
  * Solution: use an IAM Role to grant temporary credentials that rotate automatically, removing the need to store static credentials on a resource — knowledge to be applied in practice when deploying EC2 in Week 4.