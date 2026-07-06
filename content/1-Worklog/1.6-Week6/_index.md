---
title: "Worklog Week 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 objectives:
* Get familiar with containerization — packaging applications with Docker to ensure consistent behavior across environments (local, staging, production).
* Learn container orchestration with Amazon ECS/Fargate — running containers at scale without managing servers directly (serverless containers).
* Build an automated CI/CD pipeline with AWS CodePipeline — the foundation for automating deployment in the final workshop project.

### Tasks to complete this week:
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Learn Docker: images, containers, Dockerfile, layer caching. <br> - **Practice:** Write a Dockerfile for a simple application, build the image, and run a test container locally. | 25/05/2026 | 25/05/2026 | [Deploying an Application with Docker](https://000015.awsstudygroup.com/vi/) |
| Tue | - Learn Amazon ECS: Cluster, Task Definition, Service, and the Fargate launch type (serverless, no underlying EC2 management required). <br> - **Practice:** Push an image to Amazon ECR, deploy a container to ECS running on Fargate. | 26/05/2026 | 26/05/2026 | [Deploying an Application to Amazon ECS](https://000016.awsstudygroup.com/vi/) |
| Wed | - Practice an extended lab: split a monolithic application into smaller services, containerize them, and deploy each part to Fargate. | 27/05/2026 | 27/05/2026 | [Monolith to Microservices with Docker and AWS Fargate](https://000067.awsstudygroup.com/vi/) |
| Thu | - Learn AWS CodePipeline: Source stage, Build stage (CodeBuild), Deploy stage. <br> - **Practice:** Build a pipeline that automatically builds a Docker image and deploys it to ECS on every new commit to GitHub. | 28/05/2026 | 28/05/2026 | [Deploying an Application with AWS CodePipeline](https://000017.awsstudygroup.com/vi/) |
| Fri | - Practice a complete container CI/CD lab: build → push the image to ECR → automatically update the ECS Service, with no manual steps at any stage. | 29/05/2026 | 29/05/2026 | [CI/CD with CodePipeline](https://000152.awsstudygroup.com/vi/) |

### Results achieved in Week 6:
* Understood and became proficient in containerization with Docker:
  * Wrote optimized Dockerfiles (multi-stage builds, reducing image size).
  * Clearly distinguished an Image (a static packaged artifact) from a Container (a running instance of that image).
* Successfully deployed a containerized application to Amazon ECS running on Fargate:
  * Understood why Fargate is well suited to avoid having to patch/scale underlying EC2 instances for containers.
  * Grasped the flow: build the image → push to ECR (a private registry) → ECS pulls the image to run it.
* Practiced splitting an application from a monolithic architecture into smaller services:
  * Understood the benefits: scaling each service independently, easier maintenance, and a reduced blast radius when failures occur.
* Successfully built an automated CI/CD pipeline with CodePipeline:
  * The flow: Source (GitHub) → Build (CodeBuild, building the Docker image) → Deploy (updating the ECS Service).
  * Clearly understood the core value: every code push automatically produces a new version running in production, with no manual SSH into a server required to deploy.
* Grasped the foundation of container-based CI/CD — this is the exact model to be applied directly when building the GitHub Actions pipeline for the workshop project in the coming weeks (even though the CI tooling differs, the pipeline mindset is the same).