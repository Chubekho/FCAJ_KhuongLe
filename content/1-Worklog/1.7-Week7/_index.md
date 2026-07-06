---
title: "Worklog Week 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 objectives:
* Learn Serverless architecture: Lambda interacting directly with S3 and DynamoDB, with no need for a continuously running server.
* Build a REST API with API Gateway to expose Lambda externally.
* Practice asynchronous (async) processing with SQS and SNS — a producer/consumer decoupling model.
* Get familiar with observability for Serverless systems: CloudWatch and X-Ray, along with automating deployment via CodePipeline.

### Tasks to complete this week:
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Learn Serverless architecture: Lambda, triggered by S3 Events, reading/writing data to DynamoDB. <br> - **Practice:** Write a Lambda function that automatically processes new files uploaded to S3, writing the results to DynamoDB. | 01/06/2026 | 01/06/2026 | [Serverless - Lambda Interacting with S3 and DynamoDB](https://000078.awsstudygroup.com/) |
| Tue | - Learn Amazon API Gateway: REST API, Lambda Proxy Integration, request/response mapping. <br> - **Practice:** Build a REST API to expose a Lambda function externally, testing it with Postman and a simple frontend. | 02/06/2026 | 02/06/2026 | [Serverless - Building a Frontend that Calls API Gateway](https://000079.awsstudygroup.com/) |
| Wed | - Learn asynchronous processing with Amazon SQS (queue) and SNS (pub/sub, fan-out). <br> - **Practice:** Simulate an order-processing flow — the API pushes a message to SQS, a Lambda worker consumes and processes it, and SNS sends result notifications to subscribers. | 03/06/2026 | 03/06/2026 | [Serverless - Processing Orders with SQS and SNS](https://000083.awsstudygroup.com/) |
| Thu | - Learn observability for Serverless systems: CloudWatch Logs/Metrics and AWS X-Ray (distributed tracing). <br> - **Practice:** Enable X-Ray for Lambda, tracking the latency of each step across the API Gateway → Lambda → DynamoDB chain. | 04/06/2026 | 04/06/2026 | [Serverless - Monitoring a Serverless Application with CloudWatch and X-Ray](https://000085.awsstudygroup.com/) |
| Fri | - Learn CI/CD specific to Serverless applications (different from the container deployment approach in Week 6) — using AWS SAM/CloudFormation to package and deploy Lambda. <br> - **Practice:** Build a CodePipeline that automatically redeploys the Lambda function on every new commit. | 05/06/2026 | 05/06/2026 | [Serverless - CI/CD with AWS CodePipeline](https://000084.awsstudygroup.com/) |

### Results achieved in Week 7:
* Understood and became proficient in the "event-driven" Serverless model:
  * Lambda is automatically triggered by S3 Events, with no need for polling or a continuously running server.
  * Read/wrote data to DynamoDB (NoSQL) from within a Lambda function.
* Successfully built a REST API with API Gateway:
  * Understood the Lambda Proxy Integration mechanism — API Gateway forwards the request/response directly for Lambda to handle.
* Mastered the asynchronous processing model with SQS and SNS:
  * SQS: a message queue that decouples where a request is created from where it's processed — if the consumer is slow or fails, the request stays safely in the queue rather than being lost.
  * SNS: a pub/sub mechanism where one message can "fan out" to multiple subscribers at once (email, another Lambda, another SQS queue, etc.).
  * This is exactly the async job processing model (the API returns immediately, with the real work happening in the background) — the core architecture to be applied directly to the asynchronous processing component of the workshop project.
* Set up observability for the Serverless system:
  * CloudWatch Logs for debugging Lambda runtime errors.
  * X-Ray to trace the full path of a request across multiple services (API Gateway → Lambda → DynamoDB), pinpointing exactly which step is slow.
* Built a dedicated CI/CD pipeline for Serverless:
  * Understood the difference from the container CI/CD in Week 6: Serverless deploys via SAM/CloudFormation (packaging code + infrastructure config), with no Docker image build required.