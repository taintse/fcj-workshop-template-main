---
title: "Blog 1 - Web Application Firewall Support for Websites Hosted on AWS Amplify"
date: 2024-10-15T00:00:00Z
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Web Application Firewall Support for Websites Hosted on AWS Amplify

**Author:** Sébastien Stormacq  
**Published:** March 26, 2025  
**Categories:** Announcements, AWS Amplify, AWS WAF, Featured, Front-End Web & Mobile, Launch, News, Security, Identity, & Compliance

---

## Introduction

Today, we announce the integration of **AWS WAF (Web Application Firewall)** with **AWS Amplify Hosting**. Web application owners are always working to protect their applications from various threats.

---

## The Previous Problem

Previously, if you wanted to deploy a robust security system for Amplify Hosted applications, you needed to:
- Create an architecture using **Amazon CloudFront** with **AWS WAF** protection
- Perform additional complex configuration steps
- Require high technical expertise
- Increase management costs significantly

---

## The New Solution: AWS WAF Integration with Amplify

Now, you can **directly attach a web application firewall** to your AWS Amplify application through:
- A **one-click integration** in the **Amplify console**, or
- Using **Infrastructure as Code (IaC)**

This integration allows you to:
- Access **all AWS WAF features**
- Use **pre-managed rules**
- Create **custom rules** based on your specific application needs
- Protect against **common web vulnerabilities**:
  - SQL injection
  - Cross-site scripting (XSS)

---

## Powerful Security Strategies

### 1. DDoS Protection
You can leverage **AWS WAF's rate-based rules** to:
- Limit request rates from IP addresses
- Protect against distributed denial-of-service (DDoS) attacks

### 2. Geo-blocking
- Restrict access to your application from specific countries
- Particularly useful if your service targets specific geographic regions

---

## Four Protection Types Provided by Amplify

### 1. Amplify-Recommended Firewall Protection
- Protects against the **most common vulnerabilities** found in web applications
- **Blocks IP addresses** from potential threats based on Amazon's internal threat intelligence
- Protects against **malicious actors** discovering application vulnerabilities

### 2. Restrict Access to amplifyapp.com
- Restricts access to the **default amplifyapp.com domain** created by Amplify
- Useful when you **add a custom domain**
- Prevents **bots and search engines** from harvesting domain information

### 3. IP Address Protection
- Restrict web traffic by **allowing or blocking** requests from **specified IP ranges**

### 4. Geographic Protection
- Restrict access based on **specific countries**

---

## How to Set Up

Setting up AWS WAF protection for your Amplify application is **very simple**:

1. From the **Amplify console**, navigate to **app settings**
2. Select the **Firewall** tab
3. Choose the **pre-defined rules** you want to apply

### Creating a Web Access Control List (ACL)

Protections enabled through the **Amplify console** will create a **basic Web Access Control List (ACL)** in your AWS account.

**For more detailed rule sets:** Use the **rule builder** in the **AWS WAF console**.

### Time to Activate

After **a few minutes**, the rules will be **associated with your application**, and **AWS WAF will start blocking suspicious requests**.

---

## Testing AWS WAF in Action

### How to Simulate an Attack

You can **simulate an attack** and **monitor it** using AWS WAF's **test request** functionality.

**Example:** Send a request with an **empty User-Agent header value** → This will **trigger the blocking rule** in AWS WAF.

### Step 1: Send a Valid Request

First, send a **valid request** to your application.

**Result:** The server returns an **HTTP 200 (OK)** response

### Step 2: Send an Invalid Request

Then, send a request **without any value associated with the HTTP User-Agent header**.

**Result:** The server returns an **HTTP 403 (Forbidden)** response

---

## Monitoring and Optimization

AWS WAF provides **visibility into request patterns**, helping you:
- **Fine-tune security settings** over time
- **Analyze traffic trends**
- **Improve security rules** as needed

You can access **logs** through:
- **Amplify Hosting console**, or
- **AWS WAF console**

---

## Availability

- **Available in all AWS regions** where Amplify Hosting operates
- This integration **is part of AWS WAF's global resources** (similar to Amazon CloudFront)
- **Note:** Web ACLs can be attached to **multiple Amplify Hosting applications**, but they must be in the **same region**

---

## Pricing Model

Pricing for this integration follows the **standard AWS WAF pricing model**:

### AWS WAF Costs:
You pay for the AWS WAF resources you use based on:
- Number of **ACLs**
- Number of **rules**
- Number of **web requests**

### Additional Cost from AWS Amplify:
- **$15/month** when you attach a web application firewall to your application
- This cost is **calculated hourly**

---

## Key Benefits

This new feature brings **enterprise-grade security features** to all Amplify Hosting customers, from:
- **Individual developers**
- To **large enterprises**

**Now you can:**
- **Build** web applications
- **Host** web applications  
- **Protect** web applications

**All in the same service**, reducing:
- **Architecture complexity**
- **Security management overhead**

---

## Conclusion

AWS WAF integration with **Amplify Hosting** is an important step forward in **simplifying web application security**. With the ability to set up powerful protections with just one click, developers can focus on building their applications without worrying about security complexity.

---

## References and Learn More

- **AWS WAF integration for Amplify** documentation
- Try it directly in the **Amplify console**
- **AWS WAF** documentation

---

## About the Author: Sébastien Stormacq

Seb has been writing code since first touching a Commodore 64 in the mid-eighties. He inspires developers to harness the power of AWS Cloud, using a secret combination of:
- Passion
- Enthusiasm
- Customer advocacy
- Curiosity
- Creativity

**His interests:** Software architecture, development tools, and mobile computing.

**Pro tip:** If you want to sell him something, make sure it has an **API**.

**Follow @sebsto on:** Bluesky, X, Mastodon and beyond.

