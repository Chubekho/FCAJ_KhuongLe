---
title: "Worklog Week 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 objectives:

- Finish the remaining frontend features: file export, campaign management, usage tracking.
- Harden security and system observability (Secrets Manager, CloudWatch, WAF) before going live.
- Begin deploying the real AWS infrastructure for the workshop project: packaging artifacts and standing up the first infrastructure components.

### Tasks to complete this week:

| Day | Task | Start Date | Completion Date |
| --- | --- | --- | --- |
| Mon | - Built the file export area: 3 formats (PDF/DOCX/HTML), downloaded directly via a presigned URL. <br> - Completed the Campaign management page: creating new campaigns, attaching content to campaigns, archiving (soft delete). <br> - Completed the usage tracking page: a token/quota progress bar, broken down by AI model. | 29/06/2026 | 29/06/2026 |
| Tue | - Moved all sensitive secrets (JWT, database, AI API key) from config files into a centralized secret management service, with a flexible toggle between local and production environments. <br> - Switched the AI provider to a lower-cost option through a provider abstraction layer (easy to switch back if needed). <br> - Set up centralized log monitoring (separate log groups for API and Worker), configuring email alerts for abnormal errors. <br> - Set up a Web Application Firewall to protect the application from common attacks. | 30/06/2026 | 30/06/2026 |
| Wed | - Packaged the application into deployment-ready artifacts: bundling the source code for the background processing worker, building a multi-stage Docker image for the API tier. <br> - Hardened the application's security/production configuration (proxy, logging format suited to a real environment). <br> - Built the production frontend bundle, preparing an automated deployment script. | 01/07/2026 | 01/07/2026 |
| Thu | - **Began deploying the real AWS infrastructure:** building a dedicated virtual network (multiple availability zones), an auto-failover relational database (Multi-AZ), an image storage registry, and least-privilege IAM roles. <br> - Set up a load balancer and auto scaling group for the application tier, along with an in-memory cache service for the data tier. | 02/07/2026 | 02/07/2026 |

### Results achieved in Week 11:

- Completed all remaining frontend features:
  - Users can export content to real files (PDF/DOCX/HTML) and organize content by marketing campaign.
  - Gained clear visibility into monthly AI consumption — important for a usage-based SaaS billing model.
- Significantly hardened the system's security layer before going to production:
  - No secret remains directly in a config file — greatly reducing the risk of sensitive information leaking through source code.
  - An abstraction layer for the AI Provider is in place — switching AI providers takes just one config variable, with no business-logic code changes needed.
- Set up an observability layer and network-level defense:
  - Centralized logging per component, with proactive alerts instead of manual checking.
  - WAF blocks common attack types right at the system's entry point.
- Officially moved into the real infrastructure deployment phase:
  - Packaged standard artifacts (container image, serverless bundle) — exactly the skills practiced in Weeks 6-7.
  - Successfully stood up the foundational infrastructure framework (a multi-AZ private network, a redundant database, a load balancer, auto scaling) — directly applying the High Availability knowledge learned in Week 5.