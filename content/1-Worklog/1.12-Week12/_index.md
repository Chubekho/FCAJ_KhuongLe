---
title: "Worklog Week 12"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "

---

### Week 12 objectives:
* Finish deploying the real AWS infrastructure, build automated CI/CD, and finalize all documentation.

### Tasks to complete this week:
| Day | Task | Start Date | Completion Date |
| --- | --- | --- | --- |
| Mon | - Fixed issues that only appeared once the system went live: missing IAM permissions, an incorrectly configured encrypted connection to the database. <br> - Finished deploying the background processing worker as a serverless function, connecting it to the production message queue. <br> - Handled a replacement for the primary CDN (since the account wasn't verified): switching to static hosting + an alternate CDN, configuring a subdomain, attaching a Web Application Firewall, and setting up full monitoring alerts. <br> - Rotated all sensitive secrets that had been previously exposed (auth keys, database info, AI API key). <br> - Ran the seed data against production through a secure session-manager tunnel. | 06/07/2026 | 06/07/2026 |
| Tue | - Built an automated CI/CD pipeline with GitHub Actions: authenticating to AWS via OIDC (no long-lived access keys), automated code checks (lint + type-check), building/pushing the image, updating the background worker, building/pushing the frontend, then checking system health. Verified in practice: push code → the entire pipeline runs green → production updates automatically. <br> - Completed end-to-end business flow testing on the real environment (register → persona → create content → export → usage), confirming the WAF correctly blocks attacks. <br> - Drew the system's overall architecture diagram. <br> - Reviewed and finalized the README (architecture, deployment guide, fixing sections no longer matching reality after the CDN/auth changes), consolidating documentation to prepare for the end-of-course demo. | 07/07/2026 | 07/07/2026 |

### Results achieved in Week 12:
* Finished the entire production infrastructure for the workshop project:
  * Resolved "production-only" issues once and for all (IAM permissions, encrypted database connections) — an important lesson: a local/LocalStack environment doesn't fully replicate real AWS behavior.
  * Had a reasonable fallback plan when the primary CDN service was blocked — not letting an unexpected limitation stall progress.
* Fully resolved the security issue: every secret that had been exposed was rotated, with none of the old values still usable.
* Successfully built a complete, hands-off CI/CD pipeline: from pushing code to production being updated is fully automatic, with secure authentication requiring no long-lived access keys.
* Completed end-to-end business flow testing on the real environment — confirming the system works exactly as designed, from start to finish.
* Finalized the technical documentation (README, architecture diagram) under a tight time crunch — wrapping up the 4-week journey of building the workshop project.