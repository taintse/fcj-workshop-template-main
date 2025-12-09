---
title: "Blog 3 - From Virtual Machines to Kubernetes to Serverless: How Dacadoo Saved 78% on Cloud Costs"
date: 2025-03-26T00:00:00Z
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# From Virtual Machines to Kubernetes to Serverless: How Dacadoo Saved 78% on Cloud Costs and Automated Operations

**Authors:** Andreas Gehrig, Kevin Nash, Philippe Wanner  
**Published:** March 26, 2025  
**Categories:** Amazon API Gateway, Amazon DynamoDB, Amazon Route 53, Amazon Simple Storage Service (S3), Architecture, AWS Cloud Financial Management, AWS Lambda, AWS WAF, Migration, Serverless, Thought Leadership

---

## Introduction

**Dacadoo** is a global technology company headquartered in **Switzerland**, specializing in solutions for:
- **Digital health interaction**
- **Health risk quantification**

Their products include a **SaaS platform** based on:
- **Behavioral science**
- **Artificial Intelligence (AI)**
- **Gamification**

To help end users **improve their health outcomes**.

### The Modernization Journey

The company initiated an **API modernization journey** to:
- Quantify health and lifestyle data
- Provide risk assessment tools
- Calculate probability of **mortality and morbidity** based on **scientific research data**

To transform VM-based API services into a **global health score and risk calculation solution with disaster recovery**, dacadoo chose **Amazon Web Services (AWS)**.

### Results Achieved

The outcome:
- ✅ **78% cost reduction**
- ✅ **Infrastructure maintenance time under 1 hour/year**
- ✅ **Deploy multiple AWS infrastructures** without expanding the SRE team
- ✅ **High automation levels** and **agile mindset**

---

## Context: Three Evolutionary Stages

The solution architecture evolved through **three stages**:

### **Stage 1: Incubation with Virtual Machines**
- Single virtual machine on-premises with disaster recovery (DR) in Switzerland

### **Stage 2: Global and Scalable**
- Multiple Kubernetes clusters globally

### **Stage 3: Operational Excellence**
- Fully serverless with geographic redundancy on AWS

---

## Stage 1: Incubation with Virtual Machines

### Initial Architecture

After years of **scientific research and development**, the service launched, running on:
- **A single on-premises virtual machine**
- Using **hypervisor technology** to provide **disaster recovery (DR) capabilities**

The application served:
- **API requests**
- **NoSQL databases**

**All running on the same server.**

### Challenges

| Issue | Details |
|-------|---------|
| **High availability** | No HA, manual recovery required |
| **Software deployment** | Manual via SSH |
| **OS maintenance** | Manual process |
| **Automation level** | Very low |
| **Data backup** | VM snapshots only |
| **Monitoring** | Manual, no automation |
| **Testing** | Developer workstation only |

### Key Limitations

- API available only in **Switzerland**
- Maintenance performed **manually**
- Software deployment handled **manually**
- No **global scalability**
- **Personnel management issues**

---

## Stage 2: Global and Scalable with Kubernetes

### Strategic Decision

Dacadoo made a **strategic investment decision** in:
- **Kubernetes** to manage **containerized workloads**
- **Global management** at scale

### Global Deployment

Due to **geographically distributed customers** and **low-latency requirements**:

**Three Kubernetes clusters deployed:**
- Each in **a different continent**
- NoSQL databases **stored near workloads**
- Reduced **service latency** and **migration effort**

### Operations Optimization

**NoSQL Databases:**
- Integrated as **SaaS service**
- **Minimized operational maintenance**

**Monitoring:**
- Centralized with **Datadog**

**Infrastructure Provisioning:**
- Exclusively with **Terraform**
- Includes: Kubernetes clusters, NoSQL databases, GitLab & Datadog integration

**CI/CD:**
- Using **GitLab CI/CD**
- Deploy to **multiple environments and clusters**
- Planetary-scale super system

### Comparison: VM vs Kubernetes

| Criteria | Virtual Machine | Kubernetes |
|----------|-----------------|-----------|
| **Scalability** | Low | High |
| **Availability** | Best effort | 99.95% |
| **Infrastructure cost** | Low | High |
| **Maintenance effort** | High | Medium |

### Challenges

**High Costs:**
- Three regional Kubernetes clusters
- Three environments
- Total: **27 cluster nodes**

**Additional Costs:**
- Managing **NoSQL SaaS database instances** for each cluster

**Complexity:**
- **Multi-cluster multi-environment CI/CD** processes
- **Significant operational effort** to maintain infrastructure
- Need for **continuous updates** to Kubernetes components

---

## Stage 3: Operational Excellence with Serverless

### Why Move to Serverless?

The **Kubernetes-based architecture met requirements**, but:
- Some **API backlog features needed better** alignment
- Architecture needed **alignment with latest technology**
- Need to **optimize best practices**

This was the **right time** to:
- Take a **holistic view** of infrastructure and software architecture
- **Refactor** the solution with AWS's **latest technology**

### Solution Requirements

Requirements for the **refactoring**:

✅ **Maintain API functionality**

✅ **Restrict data processing** to selected regions (comply with local data protection laws)

✅ **Avoid weekly patching cycles** - use only managed serverless services

✅ **Reduce costs** - choose services with **pay-as-you-go pricing**

✅ **Delegate authentication** to dedicated service

✅ **Use established web framework** with broad ecosystem

### Application Refactoring

**API service comprises:**
1. **Developer Portal** (Developer Portal)
2. **Health score and risk calculation API**

**Database only needs:**
- API keys
- Algorithm parameters
- Quotas
- Usage statistics

### Distributed Database

**Health Data:**
- **Processed by region** by **compute layer**
- **NOT stored** (only temporary processing)
- Opens opportunity for **distributed database**

**Amazon DynamoDB Global Tables:**
- **Perfect choice** for this solution
- **Writes:** Distributed to all connected regions
- **Reads:** Performed **locally**
- **Low latency** - meets Dacadoo's SLAs

### Architecture Components

**Developer Portal:**
- Web user interface
- API documentation
- API key management
- **AWS Lambda** - auto-scaling, pay-per-request

**Health and Risk API:**
- Algorithms implemented in **C** (short simulations)
- Requires **compute-intensive calculations**
- REST API wrapped in **Python FastAPI**
- **AWS Lambda** - excellent choice

---

## Serverless Architecture in Detail

### Request Flow

**HTTP Requests:**
1. Routed via **Amazon API Gateway**
2. Protected by **AWS WAF** (against malicious requests)
3. Forwarded to **AWS Lambda functions**

**Static Resources:**
- Served from **Amazon S3**
- Via **API Gateway**
- CloudFront not required (reduces complexity)

### Global DNS Routing

**Amazon Route 53 - Latency-based Routing:**
- **Redirects DNS queries** to the **lowest-latency endpoint**
- Provides **regional HA** for API users
- **Doesn't require** specific data processing location
- Users can call **region-specific endpoints** (if regulatory compliance needed)

### Authentication and Authorization

**API Authorization:**
- Based on **HTTP headers**
- Implemented in the **application**
- Data stored in **Amazon DynamoDB**

---

## Infrastructure as Code with Pulumi

### Tool Selection

The SRE team **proficient in Python**, selected **Pulumi**:

**Advantages:**
- ✅ **Programming language control flow** - language programming
- ✅ **Powerful configuration capabilities**
- ✅ **Multi-cloud support**

### CI/CD Pipeline

**GitLab CI:**
1. **Compile** algorithm library
2. **Test** FastAPI applications
3. **Package** everything

**Deployment:**
- Just an **AWS Lambda update**
- **Simple and reliable** workflow

### Skill Enhancement

**Transformation:**
- From **configuration-based approach**
- To **infrastructure code base design**
- Using **Python object-oriented programming**

**Results:**
- SRE develop **software engineering skills**
- Investment in **team modernization**
- **GitOps culture** focused on productivity

---

## Comprehensive Comparison

| Criteria | Virtual Machine | Kubernetes | Serverless |
|----------|-----------------|-----------|-----------|
| **Scalability** | Low | High | **Very High** |
| **Availability** | Best effort | 99.95% | **99.999%*** |
| **Infrastructure cost** | Low | High | **Low** |
| **Maintenance effort** | High | Medium | **Very Low** |

*With global redundancy elevating availability to **99.999%** while keeping costs **low**.

---

## Final Results

### Cost & Performance

✅ **78% cost reduction**

✅ **Maintenance time under 1 hour/year**

✅ **99.999% global availability**

✅ **Complete automation**

### Strategic Benefits

✅ Deploy **multiple AWS infrastructures** without **expanding SRE team**

✅ **Simplify** infrastructure management complexity

✅ **Enhance** flexibility and automation

✅ **Maintain** lean SRE team

✅ **Keep infrastructure** costs **competitive**

---

## Conclusion

Migration from **virtual machines** → **Kubernetes** → **AWS Lambda** demonstrates:

**Evolution of cloud engineering** toward:
- 📈 **Efficiency**
- 📈 **Enhanced scalability**

**Each step in the journey:**
- ⬇️ Minimizes **infrastructure management complexity**
- ⬆️ Enhances **flexibility and automation**

**Results for Dacadoo:**
- ✨ **Powerful platform** growth
- ✨ **Enhanced skills** for engineers
- ✨ **Maintained** lean SRE team
- ✨ **Competitive** cost structure

---

## Get Started

**Start** with **your own AWS serverless solution**!

---

## About the Authors

### Andreas Gehrig

**Position:** Senior Cloud Architect at Dacadoo, Zurich, Switzerland

**Background:** Software engineering

**Expertise:** Leveraging AWS technology to design and build cloud-native solutions for applications and analytics

### Kevin Nash

**Position:** Senior Solutions Architect at Amazon Web Services (AWS), Switzerland

**Background:** Distributed systems

**Expertise:** Building solutions for customers, supporting customer cloud migration

### Philippe Wanner

**Position:** Senior Expert Solutions Architect at AWS

**Expertise:** Promoting optimization methods for migration and modernization

**Current Focus:** Multi-disciplinary areas encompassing:
- Distributed systems
- Serverless architecture
- Business transformation