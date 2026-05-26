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



