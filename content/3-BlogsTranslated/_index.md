---
title: "Translated Blogs"
date: 2024-10-15T00:00:00Z
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Translated AWS blogs are summarized and compiled below:

### [Blog 1](3.1-Blog1/)

**Author:** Sébastien Stormacq  
**Published:** March 26, 2025  
**Categories:** Announcements, AWS Amplify, AWS WAF, Featured, Front-End Web & Mobile, Launch, News, Security, Identity, & Compliance

**Summary:** 
This article introduces the AWS WAF (Web Application Firewall) integration feature with AWS Amplify Hosting, allowing you to directly attach a web application firewall to your Amplify application with just one click in the Amplify console or using Infrastructure as Code (IaC).

Previously, to deploy a robust security system for Amplify Hosted applications, you needed to use Amazon CloudFront with AWS WAF, requiring additional complex configuration steps. Now, this new feature simplifies the process.

**Key Features:**
- Protection against common vulnerabilities (SQL injection, XSS)
- Restrict access by country (Geo-blocking)
- Restrict access by IP address
- DDoS protection using request rate limiting
- Restrict access to the amplifyapp.com domain

**Four Types of Protection:**
1. Amplify-Recommended Protection – protects against common vulnerabilities
2. Restrict access to amplifyapp.com – blocks default domain access
3. IP Protection – allow/block by IP range
4. Geographic Protection – restrict access by country

**Pricing:**
- Follows standard AWS WAF pricing model
- Additional $15/month when attaching web application firewall
- Calculated hourly

**Availability:**
- Available in all AWS regions where Amplify Hosting operates
- Web ACL can be attached to multiple Amplify applications, but must be in same region

This article provides practical examples of testing AWS WAF by simulating attacks (sending requests with empty User-Agent), monitoring via AWS WAF console, and analyzing logs to fine-tune security rules.

### [Blog 2 - From Cloud Beginner to Award-Winning Game Developer: A Journey with AWS Cloud Institute](3.2-Blog2/)

**Author:** Carlie Marvel  
**Published:** April 1, 2025  
**Categories:** Amazon Bedrock, Amazon CloudFront, Amazon DynamoDB, Amazon Q Developer, Amazon Route 53, Amazon Simple Storage Service (S3), AWS Lambda, AWS Training and Certification

**Summary:**
The story of JC Boissy's journey from an IT project management expert with no real cloud experience to becoming an award-winning game developer thanks to AWS Cloud Institute. The CloudJack-21 game combines blackjack mechanics with AWS service education, using AI tools like Amazon Q Developer to optimize the development process.

**Highlights:**
- AWS Cloud Institute provides 12 courses, 150+ hands-on labs
- Journey from concepts to advanced serverless architecture
- Uses AWS Lambda, DynamoDB, S3, CloudFront, Route 53
- Leverages AI tools: Amazon Q Developer and PartyRock
- 24/7 learning community support via Slack
- Certifications earned: Cloud Practitioner, AI Practitioner, Solutions Architect Associate

### [Blog 3 - From Virtual Machines to Kubernetes to Serverless: How Dacadoo Saved 78% on Cloud Costs](3.3-Blog3/)

**Authors:** Andreas Gehrig, Kevin Nash, Philippe Wanner  
**Published:** March 26, 2025  
**Categories:** Amazon API Gateway, Amazon DynamoDB, Amazon Route 53, Amazon Simple Storage Service (S3), Architecture, AWS Cloud Financial Management, AWS Lambda, AWS WAF, Migration, Serverless, Thought Leadership

**Summary:**
Dacadoo's modernization journey from a single VM architecture to global Kubernetes clusters, and finally to a fully serverless architecture. Through these three stages, Dacadoo reduced infrastructure costs by 78%, reduced maintenance time to under 1 hour/year, and achieved 99.999% availability with geographic redundancy.

**Highlights:**
- **Stage 1 - Virtual Machines:** Best-effort availability, manual maintenance, low cost
- **Stage 2 - Kubernetes:** Three global clusters, 99.95% availability, high cost, medium maintenance
- **Stage 3 - Serverless:** AWS Lambda, 99.999% availability, 78% lower cost, high automation
- Uses DynamoDB Global Tables, API Gateway, Route 53 latency-based routing
- Infrastructure as Code with Pulumi (Python-based)
- Automated CI/CD with GitLab

