# CICD-Concepts-L1
Problem Statement 
This assignment asks me todifferentiate bwt Continuous integration CI, Continuous Delivery, and Continuous Deployment, explain the difference between manual and automated approval steps, and design a theoretical CI/CD pipeline for a simple Web Application.

# Part 1 - Understanding CI, CD, and C Development
Continuous Integration (CI) is the practice where every developer merges their code changes into a shared repository frequently, usually multiple times a day. Each merge automatically triggers a build and a set of automated tests. The goal is to catch bugs early, before they grow into bigger problems.
Continuous Delivery takes CI one step further. After the code passes all tests, it is automatically packaged and deployed to a staging environment. However, pushing it to production still requires a human to review and give manual approval. A team lead or QA engineer clicks a button to say "yes, this is safe to go live."
Continuous Deployment removes that human step entirely. Once the code passes all automated checks, it is automatically deployed straight to production without any manual intervention. This requires a very high level of trust in your automated tests.

# Part 2 — Manual vs Automated: Delivery vs Deployment
The single biggest difference between Continuous Delivery and Continuous Deployment is the production approval gate.
In Continuous Delivery, there is a manual checkpoint before production. A human being reviews the staging environment, checks logs, checks business requirements, and decides whether to release. This gives teams control, especially in regulated industries like banking or healthcare.
In Continuous Deployment, that checkpoint is replaced entirely by automated tests. If all tests pass, the code goes live automatically, sometimes within minutes of a developer pushing a commit. This is common in companies like Netflix or Amazon that deploy dozens of times per day.
The table below summarizes this:

<img width="846" height="477" alt="image" src="https://github.com/user-attachments/assets/a761119b-cb44-4c6f-822f-4486654d2447" />

Part 3 — Theoretical CI/CD Pipeline for a Web Application
Below is the pipeline I have designed for a simple Node.js web application:
Step 1 — Code Push
A developer pushes code to a GitHub repository. This event triggers the pipeline automatically via a webhook.
Tools: Git, GitHub
Step 2 — Build
The pipeline installs all dependencies and compiles the application. For a Node.js app, this means running npm install and creating a Docker image.
Tools: npm, Docker
Step 3 — Automated Testing
Unit tests and integration tests run automatically against the built code. If any test fails, the pipeline stops and the developer is notified.
Tools: Jest (for JavaScript), GitHub Actions as the runner
Step 4 — Code Quality Scan
The code is analysed for style issues, potential bugs, and security vulnerabilities before it proceeds further.
Tools: ESLint (style), SonarQube (quality and security)
Step 5 — Package and Store Artifact
The Docker image is tagged with the commit ID and pushed to a container registry so it can be deployed consistently.
Tools: Docker Hub or AWS ECR
Step 6 — Deploy to Staging
The Docker image is automatically pulled and deployed to a staging server. The team can test it manually in a real environment here.
Tools: GitHub Actions, Kubernetes (staging namespace)
Step 7 — Deploy to Production
In the Continuous Delivery model: a team lead reviews staging and clicks "Approve" in GitHub Environments.
In the Continuous Deployment model: if all previous steps pass, this step runs automatically.
Tools: Kubernetes (production namespace), AWS EKS or Heroku

<img width="770" height="633" alt="image" src="https://github.com/user-attachments/assets/7874b250-f813-4641-9463-645eecd54c40" />


Steps Followed

Studied the definitions of CI, Continuous Delivery, and Continuous Deployment
Created a comparison table showing which steps are manual vs automated in each model
Mapped out a 7-stage pipeline for a Node.js web application
Selected realistic tools for each stage
Documented everything in this README file


Output
The output of this assignment is:

A written comparison of CI vs CD Delivery vs CD Deployment
A theoretical pipeline flow with tools at each stage
A pipeline diagram showing all 7 stages
