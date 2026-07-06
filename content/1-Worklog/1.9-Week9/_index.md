---
title: "Worklog Week 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 objectives:
* Begin implementing the workshop project — **AI Content Generator Platform**: a SaaS platform that generates marketing content with AI based on a Brand Persona (each business's own brand voice).
* Complete the entire backend core: authentication, brand persona, asynchronous content generation via SQS, multi-format export, usage/quota.

### Tasks to complete this week:
| Day | Task | Start Date | Completion Date |
| --- | --- | --- | --- |
| Mon | - Scaffold the monorepo (backend/frontend/infrastructure), Docker Compose (PostgreSQL+Redis+LocalStack). <br> - Design an 11-table multi-tenant Prisma schema, configuration layer (database/redis/aws/logger). <br> - Build the full Auth flow (register/login/refresh/logout/me + JWT rotation), Brand Persona CRUD + Redis cache, Content CRUD + async operations pushed to SQS. <br> - Write worker.ts (SQS consumer → AI provider → save ContentVersion + UsageLog). | 15/06/2026 | 15/06/2026 |
| Tue | - Complete Campaign CRUD (multi-tenant filtering, soft delete). <br> - Test the full end-to-end flow: register → create a persona → create content → generate → poll the job. <br> - Fixed several bugs: normalizing persona data types, incorrect parameters when enqueueing to SQS, AI provider client configuration. | 16/06/2026 | 16/06/2026 |
| Wed | - Built the Export Service: generating PDF/DOCX/HTML files from content, uploading to S3, and returning a presigned URL. <br> - Added a Mock mode for the AI Provider so development doesn't depend on real AI costs. <br> - Fixed an S3 Client configuration bug when used with the local simulated environment. | 17/06/2026 | 17/06/2026 |
| Thu | - Built the usage-tracking feature (monthly, per AI model). <br> - Implemented Quota Enforcement: blocking content generation once the limit is exceeded, with shared logic between the API and the Worker. <br> - Built the Org Settings management page: viewing/updating quotas, role-based permissions (OWNER/ADMIN). | 18/06/2026 | 18/06/2026 |

### Results achieved in Week 9:
* Completed the entire backend core of the workshop project within the first 5 days:
  * A proper multi-tenant architecture: every table has an `organizationId`, and every query filters by organization — preventing data leakage between different customers.
  * A complete asynchronous processing flow: the API receives a request → pushes a job to SQS → responds immediately → the Worker processes the AI job in the background → updates the result — correctly applying the Serverless/Queue architecture learned in Week 7.
  * A Quota mechanism shared between the API and the Worker — avoiding duplicated logic and ensuring consistent enforcement in both places.
* Successfully built a multi-format Export feature (PDF/DOCX/HTML) with a secure file-download mechanism via presigned URLs, without exposing the storage bucket directly to the public.
* Set up a Mock mode for the AI Provider — allowing development and testing to run in parallel without incurring continuous real AI costs.
* Proficiently applied several skills learned in previous weeks in practice: multi-tenant filtering (a least-privilege mindset), the async job pattern (SQS/Worker), and managing relational data with Prisma/PostgreSQL.