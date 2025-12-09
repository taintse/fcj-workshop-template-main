---
title: "Event 5"
date: 2024-10-15T00:00:00Z
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

# Learning Report: "AWS Cloud Mastery Series #3 - Security on AWS"

---

## Event Basic Information

**Event Name:** AWS Cloud Mastery Series #3 - Security on AWS (Well-Architected Security Pillar)

**Date:** Saturday, November 29, 2025

**Time:** 08:30 - 12:00

**Location:** AWS Vietnam Office, Bitexco Financial Tower, District 1, Ho Chi Minh City

**Organized by:** AWS Community, Kha Van

**Number of Attendees:** 355 students & professionals

**My Role:** Event Participant, Active Learner

---

## Event Purpose

The **AWS Cloud Mastery Series #3** was organized to:

- 🎯 Introduce the **5 Pillars of AWS Well-Architected Security Framework**
- 🔐 Practice **modern Identity & Access Management** patterns
- 👁️ Understand **Detection & Continuous Monitoring** strategies
- 🛡️ Protect infrastructure and workloads effectively
- 🔒 Protect data with encryption & secrets management
- 🚨 Prepare **Incident Response playbooks** & automation

---

## Detailed Program

### 08:30 – 08:50 | Opening & Security Foundation

#### AWS Well-Architected Security Pillar

**Concept:**
- AWS Well-Architected Framework: 6 pillars (Operational Excellence, Security, Reliability, Performance, Cost Optimization, Sustainability)
- **Security Pillar** is the foundation for all others

#### 3 Core Principles

1. **Least Privilege** 🔑
   - Grant only necessary permissions
   - Avoid overprovisioning access
   - Audit & remove unused permissions regularly

2. **Zero Trust** 🚫
   - Assume system is compromised
   - Verify every request explicitly
   - Don't trust by default

3. **Defense in Depth** 🛡️
   - Multiple security layers
   - If one layer fails, others protect
   - Reduce single point of failure risk

#### Shared Responsibility Model

**AWS Responsibility:**
- Physical security of data centers
- Network infrastructure
- Hypervisor & underlying services
- Base infrastructure security

**Customer Responsibility:**
- IAM & access control configuration
- Encryption key management
- Application security
- OS & patch management
- Data classification & protection

**Key Insight:** Security is a **shared responsibility**, not AWS's sole responsibility

#### Top Threats in Vietnamese Cloud Environment

**Common Threats:**
- Compromised credentials (weak passwords, credential reuse)
- Misconfigured S3 buckets (public data exposure)
- Unpatched systems & vulnerabilities
- Insider threats & unauthorized access
- DDoS attacks on cloud infrastructure
- Ransomware & malware

**Why Vietnam-Specific?**
- Rapid cloud adoption across industries
- Talent shortage in cloud security
- Legacy system migration challenges
- Emerging regulatory requirements (PDPA, etc.)

---

### 08:50 – 09:30 | Pillar 1: Identity & Access Management

#### Modern IAM Architecture

**Core Components:**

1. **IAM Users vs Roles:**
   - **Users:** For people (developers, admins, contractors)
   - **Roles:** For services, cross-account access, temporary credentials
   - **Best Practice:** Use roles wherever possible, minimize user access keys

2. **Avoid Long-term Credentials:**
   - ❌ Never use AWS access keys for applications
   - ✅ Use IAM roles for EC2, Lambda, containers, on-prem servers
   - ✅ Use temporary security credentials with expiration

3. **IAM Policies:**
   - Identity-based policies (attached to users/roles)
   - Resource-based policies (attached to resources)
   - Permission boundaries (set maximum permissions ceiling)
   - SCPs (Service Control Policies) for org-level enforcement

#### IAM Identity Center

**Modern SSO Solution:**
- Replace traditional IAM users with AWS IAM Identity Center
- Single sign-on across AWS accounts & applications
- Support for SAML, OAuth, Okta, Azure AD
- Permission Sets (simplified policy management)

**Use Case:**
- Enterprise with 100s of employees
- Need access across multiple AWS accounts
- Centralized identity & access management

#### SCP & Permission Boundaries for Multi-account

**SCPs (Service Control Policies):**
- Applied at organization level
- Deny specific actions across all accounts
- Example: Prevent EC2 termination in production

**Permission Boundaries:**
- Set maximum permissions for user/role
- Prevent privilege escalation
- Example: Limit user to specific AWS regions

#### MFA, Credential Rotation, Access Analyzer

**Multi-Factor Authentication:**
- Hardware tokens, authenticator apps, SMS
- Mandatory for production access
- Prevent account takeover even if password compromised

**Credential Rotation:**
- Automated access key rotation (90 days)
- Reduce blast radius if key is compromised
- Detection & response faster

**Access Analyzer:**
- Find unintended access to resources
- Cross-account access analysis
- Identify public resources (S3, AMI, etc.)

#### Mini Demo: Validate IAM Policy + Simulate Access

**Demo Flow:**
1. Create IAM policy (S3 read-only to specific bucket)
2. Use IAM Policy Simulator to test
3. Show which actions allowed/denied
4. Simulate different scenarios & conditions

**Key Insight:** Always validate policies before applying - prevent production outages

---

### 09:30 – 09:55 | Pillar 2: Detection & Continuous Monitoring

#### CloudTrail (Organization Level)

**Purpose:**
- Log all AWS API calls & actions
- Who did what, when, and from where
- Compliance evidence & forensics
- Audit trail for all accounts

**Organization Trail:**
- Single trail for entire organization
- Aggregate logs from all accounts
- Centralized analysis & compliance

#### GuardDuty

**Threat Detection Service:**
- Machine learning-based intelligent threat detection
- Analyzes CloudTrail, VPC Flow Logs, DNS logs
- Find malware, compromised credentials, unusual behavior
- 30-day free trial then pay per GB analyzed

**Detection Categories:**
- Reconnaissance (port scanning, vulnerability scanning)
- Instance compromise (malware, unauthorized connections)
- Cryptocurrency mining exploitation
- IAM compromises & credential abuse

#### Security Hub

**Centralized Security Dashboard:**
- Aggregate findings from GuardDuty, IAM Access Analyzer, Config, Inspector
- Single pane of glass for entire security posture
- Compliance frameworks (CIS Benchmarks, PCI-DSS, NIST)

#### Logging at Every Layer

**VPC Flow Logs:**
- Network traffic logs (IP flow information)
- Find unusual traffic patterns
- Forensic analysis & incident investigation

**ALB/S3 Logs:**
- Application load balancer access logs (every request)
- S3 object-level logging (who accessed what when)
- Track access patterns & anomalies

#### Alerting & Automation with EventBridge

**Pattern:**
```
CloudTrail logs → EventBridge rule → Lambda/SNS → Auto-response/Alert
```

**Example:**
- EC2 instance launched → Check if AMI is approved
- If not approved → Terminate instance automatically
- Send alert to security & ops teams

#### Detection-as-Code

**Concept:**
- Infrastructure-as-code for security rules & detections
- Version control detection logic (git-based)
- Apply same rules consistently across environments
- Easy to audit & update

---

### 09:55 – 10:10 | Coffee Break

---

### 10:10 – 10:40 | Pillar 3: Infrastructure Protection

#### VPC Segmentation

**Best Practices:**
- Separate prod/non-prod VPCs
- Private subnets for databases (no internet exposure)
- Public subnets for load balancers & NAT gateways
- Subnets across multiple availability zones

**Network ACLs vs Security Groups:**
- **Security Groups (stateful):**
  - Allow outbound, implicit deny others
  - Efficient for instance-level control
  - Faster evaluation
  
- **Network ACLs (stateless):**
  - Explicit allow/deny rules
  - Subnet-level control
  - More granular but slower

**Private vs Public Placement:**
- **Public:** Bastion hosts (jump boxes), NAT gateways, ALB
- **Private:** Databases, application servers (no direct internet access)

#### WAF + Shield + Network Firewall

**AWS WAF (Web Application Firewall):**
- Protect web applications against common attacks
- SQL injection, XSS, DDoS, bot traffic
- Rate limiting, IP reputation filtering
- Managed rules from AWS

**AWS Shield:**
- Free tier: DDoS protection against common attacks
- Shield Advanced: 24/7 DDoS Response Team, larger attack protection
- Automatic mitigation

**Network Firewall:**
- Stateful firewall at VPC level
- Deep packet inspection & IPS capabilities
- Centralized threat protection
- Network segmentation enforcement

#### Workload Protection: EC2, ECS/EKS Security Basics

**EC2 Security:**
- Use AMI from AWS or trusted sources only
- Enable detailed CloudWatch monitoring
- AWS Systems Manager for OS patching
- Encrypted EBS volumes
- Security group & network ACL restrictions

**ECS/EKS Security:**
- Container image scanning before deployment
- Network policies (Kubernetes) for east-west traffic
- RBAC for access control
- Pod security policies & admission controllers
- Image signing & verification

---

### 10:40 – 11:10 | Pillar 4: Data Protection

#### KMS (Key Management Service)

**Key Concepts:**
- Customer Master Key (CMK) managed by KMS
- Private key never exposed (lives in hardware security module)
- Key policies control who can use keys
- Automatic rotation every 90 days optional

**Key Policies:**
- Who can administer key (key admins)
- Who can use key (for encryption/decryption)
- Cross-account access patterns
- Service-specific permissions

**Grants:**
- Temporary permissions for specific operations
- Useful for time-limited access
- More flexible than key policies

#### Encryption at-Rest & In-Transit

**At-Rest (stored data):**
- S3: Default encryption with KMS
- EBS: Enabled by default (create encrypted volume)
- RDS: Enable encryption at creation
- DynamoDB: Enable point-in-time recovery & encryption

**In-Transit (data moving):**
- TLS/SSL for all connections
- HTTPS for web traffic (never HTTP)
- VPN for site-to-site connectivity
- Never send plaintext over networks

#### Secrets Manager & Parameter Store

**Secrets Manager:**
- Store sensitive data (passwords, API keys, DB credentials)
- Automatic rotation (database credentials every 30 days)
- Encryption with KMS
- Complete audit trail of access

**Parameter Store:**
- Lighter-weight than Secrets Manager
- Store configuration values & application parameters
- Free tier available
- Version control built-in

**Rotation Patterns:**
- Database credentials: Automated rotation
- API keys: Manual rotation or key versioning
- Certificates: Auto-renewal before expiration

#### Data Classification & Access Guardrails

**Classification:**
- Identify sensitive data (PII, financial, health records)
- Apply different security controls based on classification
- Example: PII data only accessible from corporate VPC

**Guardrails:**
- Prevent downloading sensitive data to personal devices
- Restrict copy-paste in databases
- Audit all access to classified data
- Data loss prevention (DLP) policies

---

### 11:10 – 11:40 | Pillar 5: Incident Response

#### Incident Response Lifecycle (AWS Model)

**Phases:**

1. **Detection & Analysis:**
   - Identify incident (alert, log, report)
   - Understand scope & impact (how many systems)
   - Activate incident response team

2. **Containment:**
   - Stop attack from spreading to other systems
   - Isolate affected resources
   - Preserve evidence for forensics

3. **Eradication:**
   - Remove threat from systems
   - Patch vulnerabilities
   - Update configurations & credentials

4. **Recovery:**
   - Restore systems to normal operation
   - Verify integrity & functionality
   - Monitor for signs of recurrence

5. **Post-Incident:**
   - Document lessons learned (postmortem)
   - Update incident playbooks
   - Improve controls & detection

#### IR Playbooks for Common Scenarios

**Playbook 1: Compromised IAM Key**
```
Detection → Disable IAM user immediately
         → Audit recent CloudTrail actions
         → Check for unauthorized resources created
         → Identify data accessed
         → Rotate all credentials
         → Enable MFA
         → Update security policies & permissions
         → Monitor for continued abuse
```

**Playbook 2: S3 Public Exposure**
```
Detection → Check CloudTrail for who made change
         → Identify affected data & sensitivity level
         → Restrict access immediately
         → Scan logs for data exfiltration
         → Notify affected customers if PII exposed
         → Root cause analysis
         → Process improvement & automation
```

**Playbook 3: EC2 Malware Detection**
```
Detection → Isolate EC2 from network (security group)
         → Create snapshot for forensics analysis
         → Analyze logs (CloudTrail, VPC Flow Logs)
         → Terminate compromised instance
         → Patch other similar instances
         → Update antivirus/EDR rules
         → Review access logs
```

#### Snapshot, Isolation, Evidence Collection

**Quick Response Steps:**
1. **Snapshot** infected system (preserve evidence)
2. **Isolate** from network (stop propagation)
3. **Collect evidence** (logs, memory dumps, configs)
4. **Analyze offline** (forensics analysis)
5. **Respond** after understanding impact

#### Auto-response with Lambda/Step Functions

**Pattern:**
```
GuardDuty finding → EventBridge rule → Lambda/Step Functions
                 → Automated response (isolate, snapshot, notify)
                 → Create ticket in ticketing system
                 → Escalate to on-call engineer
```

**Example Auto-responses:**
- Disable IAM user on excessive failed logins
- Isolate EC2 instance on malware detection
- Restrict security group on port scanning detection
- Snapshot & isolate on suspicious behavior

**Benefits:**
- Faster response time (seconds vs hours)
- Consistent playbook execution (no human error)
- Reduced manual work
- 24/7 automated response capability

---

### 11:40 – 12:00 | Wrap-Up & Q&A

#### 5 Pillars Summary

1. **IAM:** Modern identity, least privilege, MFA mandatory
2. **Detection:** Continuous monitoring, alerting, automation essential
3. **Infrastructure:** Network segmentation, WAF, firewalls
4. **Data:** Encryption at-rest & in-transit, secrets management
5. **Incident Response:** Playbooks, automation, continuous improvement

#### Common Pitfalls & Vietnamese Business Context

**Common Mistakes:**
- ❌ Long-term access keys for applications & services
- ❌ S3 buckets accidentally made public (misconfiguration)
- ❌ No encryption enabled on sensitive data
- ❌ No backup/disaster recovery plan
- ❌ No incident response plan before crisis

**Vietnamese Context:**
- Growing regulatory requirements (PDPA compliance)
- Legacy systems migration security challenges
- Talent shortage in cloud security specialists
- Need for managed security services & outsourcing

#### Security Learning Roadmap

**AWS Certifications:**
1. **AWS Security Specialty:** Deep technical security knowledge
2. **Solutions Architect Professional:** Security architecture & design
3. **Advanced Security on AWS:** Expert-level knowledge

**Continuous Learning:**
- AWS Security workshops & hands-on labs
- Security conferences (AWS re:Invent, BSides, OWASP)
- Capture-the-flag (CTF) challenges
- Join security communities & forums
- Stay updated on threat intelligence

---

## Key Knowledge Acquired

### 1. **Security is Not a Feature, It's a Mindset** 🧠

- **Least Privilege:** Only grant what's absolutely needed
- **Zero Trust:** Never trust, always verify every request
- **Defense in Depth:** Multiple layers of protection
- **These principles** applicable across all cloud services

### 2. **IAM is Foundation of Cloud Security** 🔐

- Modern IAM ≠ legacy on-premises access control
- Roles > Users for most use cases
- MFA mandatory for sensitive access
- Regular audits & unused permission removal essential

### 3. **Detection & Monitoring are Continuous** 👁️

- CloudTrail provides comprehensive audit trail
- GuardDuty finds threats automatically (ML-based)
- Security Hub aggregates all security signals
- Automation responds faster than humans ever could

### 4. **Data Protection is Non-negotiable** 🔒

- Encryption at-rest & in-transit non-optional
- Key management critical & complex
- Secrets rotation automated & monitored
- Access to sensitive data audited completely

### 5. **Incident Response Needs Preparation** 🚨

- Playbooks written before incidents occur
- Automation speeds response dramatically
- Evidence preservation critical for RCA
- Postmortems & continuous improvement culture

### 6. **Security Requires Organizational Support** 🤝

- Not just infosec team responsibility alone
- Developers, ops, leadership all involved
- Budget allocation & resources necessary
- Training & security awareness essential

---

## Value Gained

### Skills & Knowledge

- ✅ **IAM Architecture:** Modern identity management patterns
- ✅ **Detection Strategy:** Continuous monitoring & intelligent alerting
- ✅ **Network Security:** VPC design, WAF, firewalls
- ✅ **Data Protection:** Encryption strategies & KMS key management
- ✅ **Incident Response:** Playbooks, automation, forensics
- ✅ **Compliance:** Well-Architected framework & PDPA awareness

### Practical Confidence

- ✅ **Can Design:** Secure AWS infrastructure from scratch
- ✅ **Can Implement:** IAM policies correctly
- ✅ **Can Monitor:** Detect threats continuously
- ✅ **Can Respond:** To incidents systematically & automatically
- ✅ **Can Audit:** AWS environment for misconfigurations

### Mindset Shift

- ✅ **Understand Shared Responsibility:** Security depends on both AWS & customer
- ✅ **Appreciate Defense in Depth:** No single magic solution exists
- ✅ **Value Automation:** Faster, more consistent, 24/7
- ✅ **Embrace Continuous Improvement:** Learning from incidents
- ✅ **Think like Attacker:** Anticipate threats & countermeasures

---

## Tools & Technologies Learned

| Tool | Application | Notes |
|------|-------------|-------|
| **IAM** | Identity & access control | Users, roles, policies, boundaries |
| **IAM Identity Center** | Enterprise SSO | Replace traditional IAM users |
| **CloudTrail** | API audit logging | Organization-level centralized |
| **GuardDuty** | Threat detection | ML-based anomaly detection |
| **Security Hub** | Security dashboard | Centralized findings aggregation |
| **VPC Flow Logs** | Network monitoring | IP traffic analysis & forensics |
| **WAF** | Web application firewall | Attack prevention & rate limiting |
| **Shield** | DDoS protection | Free + Advanced tiers |
| **Network Firewall** | VPC-level firewall | Stateful inspection & IPS |
| **KMS** | Key management | Encryption keys & rotation |
| **Secrets Manager** | Secret storage | Rotation & audit trail |
| **Parameter Store** | Configuration store | Lightweight secrets management |
| **EventBridge** | Event routing | Automation trigger |
| **Lambda** | Serverless compute | Auto-response functions |

---

## Conclusion

**AWS Cloud Mastery Series #3** was an invaluable workshop on security:

✨ **Strengths:**
- 5 Pillars framework is comprehensive & practical
- Balance between theory & real-world examples
- Incident scenarios are relatable & actionable
- Modern IAM & Zero Trust concepts explained well
- 355 engaged, security-focused participants

💫 **Key Takeaways:**
- **Security is Shared Responsibility:** AWS provides tools, customer implements
- **Least Privilege always:** Never grant unnecessary permissions
- **Detect & respond quickly:** Automation is critical
- **Data protection requires layers:** Encryption + access control
- **Incident response requires preparation:** Playbooks before crisis

🎯 **Practical Outcomes:**
- Can design secure AWS infrastructure
- Know how to implement modern IAM correctly
- Understand detection & monitoring strategies
- Have incident response playbook template
- Ready for cloud security roles

🔐 **Security Career Path:**
- High demand for cloud security professionals
- Certifications valuable (Security Specialty)
- Continuous learning necessary (threat landscape evolves)
- High impact on entire organization

---

**Thank you AWS Community for an incredibly valuable security workshop!** 🙏

Today I learned not just tools, but **understand the philosophy & culture** of cloud security.

**Least Privilege, Zero Trust, Defense in Depth** - simple principles yet powerful when applied consistently.

**I'm committed to building secure cloud systems!** 🔐🛡️✨