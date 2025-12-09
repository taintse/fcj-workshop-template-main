---
title: "Event 5"
date: 2024-10-15T00:00:00Z
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---

{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Bài Thu Hoạch "AWS Cloud Mastery Series #3 - Security on AWS"

---

## Thông Tin Cơ Bản Về Sự Kiện

**Tên sự kiện:** AWS Cloud Mastery Series #3 - Security on AWS (Well-Architected Security Pillar)

**Ngày tổ chức:** Thứ Bảy, 29 tháng 11 năm 2025

**Thời gian:** 08:30 - 12:00

**Địa điểm:** AWS Vietnam Office, Bitexco Financial Tower, Quận 1, TP. Hồ Chí Minh

**Tổ chức bởi:** AWS Community, Kha Van

**Số lượng người tham dự:** 355 sinh viên & professionals

**Vai trò của tôi:** Người tham dự, Active Learner

---

## Mục Đích Của Sự Kiện

Sự kiện **AWS Cloud Mastery Series #3** được tổ chức nhằm:

- 🎯 Giới thiệu **5 Pillars của AWS Well-Architected Security Framework**
- 🔐 Thực hành **Identity & Access Management** modern
- 👁️ Hiểu **Detection & Continuous Monitoring** strategies
- 🛡️ Bảo vệ infrastructure và workloads
- 🔒 Bảo vệ dữ liệu với encryption & secrets management
- 🚨 Chuẩn bị **Incident Response playbooks** & automation

---

## Chương Trình Chi Tiết

### 08:30 – 08:50 | Opening & Security Foundation

#### AWS Well-Architected Security Pillar

**Khái niệm:**
- AWS Well-Architected Framework: 6 pillars (Operational Excellence, Security, Reliability, Performance, Cost Optimization, Sustainability)
- **Security Pillar** là foundation cho tất cả

#### 3 Nguyên Tắc Cốt Lõi

1. **Least Privilege** 🔑
   - Chỉ grant quyền cần thiết
   - Tránh overprovisioning permissions
   - Audit & remove unused access

2. **Zero Trust** 🚫
   - Assume breach (assume system compromised)
   - Verify every request
   - Don't trust by default

3. **Defense in Depth** 🛡️
   - Multiple layers of security
   - If one layer fails, others protect
   - Reduce single point of failure

#### Shared Responsibility Model

**AWS Responsibility:**
- Physical security của data centers
- Network infrastructure
- Hypervisor & underlying services

**Customer Responsibility:**
- IAM & access control
- Encryption keys
- Application security
- Patch management

**Key insight:** Security is a **shared responsibility**, not AWS's alone

#### Top Threats trong Cloud Environment Việt Nam

**Common Threats:**
- Compromised credentials (weak passwords, reuse)
- Misconfigured S3 buckets (public exposure)
- Unpatched systems
- Insider threats
- DDoS attacks
- Ransomware

**Why Việt Nam specific?**
- Growing cloud adoption
- Talent shortage in security
- Legacy systems migration challenges
- Regulatory requirements (PDPA, etc.)

---

### 08:50 – 09:30 | Pillar 1: Identity & Access Management

#### Modern IAM Architecture

**Core Components:**

1. **IAM Users vs Roles:**
   - **Users:** For people (developers, admins)
   - **Roles:** For services & temporary access
   - **Best Practice:** Use roles whenever possible

2. **Avoid Long-term Credentials:**
   - ❌ Never use AWS access keys for applications
   - ✅ Use IAM roles for EC2, Lambda, containers
   - ✅ Use temporary security credentials

3. **IAM Policies:**
   - Identity-based policies (attached to users/roles)
   - Resource-based policies (attached to resources)
   - Permission boundaries (set maximum permissions)
   - SCPs (Service Control Policies) for org-level control

#### IAM Identity Center

**Modern SSO Solution:**
- Replace IAM users with AWS IAM Identity Center
- Single sign-on across AWS accounts
- Support for SAML, OAuth
- Permission Sets (simplified policies)

**Use Case:**
- Enterprise with 100s of employees
- Need access across multiple accounts
- Centralized identity management

#### SCP & Permission Boundaries for Multi-account

**SCPs (Service Control Policies):**
- Applied at organization level
- Deny specific actions across all accounts
- Example: Prevent EC2 termination

**Permission Boundaries:**
- Set maximum permissions for user/role
- Prevent privilege escalation
- Example: Limit to specific regions

#### MFA, Credential Rotation, Access Analyzer

**Multi-Factor Authentication:**
- Hardware tokens, authenticator apps, SMS
- Mandatory for production access
- Prevent account takeover

**Credential Rotation:**
- Automated access key rotation (90 days)
- Reduce blast radius if key compromised

**Access Analyzer:**
- Find unintended access to resources
- Cross-account access analysis
- Identify public resources

#### Mini Demo: Validate IAM Policy + Simulate Access

**Demo Flow:**
1. Create IAM policy (S3 read-only)
2. Use IAM Policy Simulator to test
3. Show what actions allowed/denied
4. Simulate different scenarios

**Key Insight:** Always validate policies before applying - prevent outages

---

### 09:30 – 09:55 | Pillar 2: Detection & Continuous Monitoring

#### CloudTrail (Organization Level)

**Purpose:**
- Log all AWS API calls
- Who did what, when, and from where
- Compliance & forensics

**Organization Trail:**
- Single trail for entire organization
- Aggregate logs from all accounts
- Centralized analysis

#### GuardDuty

**Threat Detection Service:**
- Machine learning-based threat detection
- Analyzes CloudTrail, VPC Flow Logs, DNS logs
- Find malware, unusual behavior
- 30-day free trial then pay per log analyzed

**Detection Categories:**
- Reconnaissance (scanning)
- Instance compromise
- Cryptocurrency mining
- IAM compromises

#### Security Hub

**Centralized Security Dashboard:**
- Aggregate findings from GuardDuty, IAM Access Analyzer, Config, etc.
- Single pane of glass for security
- Compliance frameworks (CIS, PCI-DSS)

#### Logging at Every Layer

**VPC Flow Logs:**
- Network traffic logs
- Find unusual traffic patterns
- Forensic analysis

**ALB/S3 Logs:**
- Application load balancer access logs
- S3 object-level logging
- Track who accessed what

#### Alerting & Automation with EventBridge

**Pattern:**
```
CloudTrail logs → EventBridge rule → Lambda/SNS → Auto-response
```

**Example:**
- EC2 instance launched → Check if approved AMI
- If not approved → Terminate instance
- Send alert to security team

#### Detection-as-Code

**Concept:**
- Infrastructure-as-code for security rules
- Version control detection logic
- Apply same rules across environments

---

### 09:55 – 10:10 | Coffee Break

---

### 10:10 – 10:40 | Pillar 3: Infrastructure Protection

#### VPC Segmentation

**Best Practices:**
- Separate prod/non-prod VPCs
- Private subnets for databases
- Public subnets for load balancers

**Network ACLs vs Security Groups:**
- **Security Groups (stateful):**
  - Allow traffic, implicit deny other
  - Efficient for instance-level control
  
- **Network ACLs (stateless):**
  - Explicit allow/deny rules
  - Subnet-level control
  - Slower but more granular

**Private vs Public Placement:**
- **Public:** Bastion hosts, NAT gateways
- **Private:** Databases, application servers (no direct internet access)

#### WAF + Shield + Network Firewall

**AWS WAF (Web Application Firewall):**
- Protect against common web attacks
- SQL injection, XSS, DDoS
- Rate limiting, IP reputation

**AWS Shield:**
- Free tier: Protection against common DDoS
- Shield Advanced: 24/7 support, larger attacks

**Network Firewall:**
- Stateful firewall at VPC level
- Deep packet inspection
- Protection for entire VPC

#### Workload Protection: EC2, ECS/EKS Security Basics

**EC2 Security:**
- Use AMI from AWS or trusted sources
- Enable detailed monitoring
- Systems Manager for patching
- Encrypted EBS volumes

**ECS/EKS Security:**
- Container image scanning
- Network policies (Kubernetes)
- RBAC for access control
- Pod security policies

---

### 10:40 – 11:10 | Pillar 4: Data Protection

#### KMS (Key Management Service)

**Key Concepts:**
- Customer Master Key (CMK) managed by KMS
- Never exposed (hardware security module)
- Key policies control who can use keys
- Automatic rotation enabled

**Key Policies:**
- Who can manage key (key admins)
- Who can use key (data key generation)
- Cross-account access patterns

**Grants:**
- Temporary permissions for specific operations
- Useful for time-limited access

#### Encryption at-Rest & In-Transit

**At-Rest (stored data):**
- S3: Default encryption with KMS
- EBS: Encrypted by default
- RDS: Enable encryption at creation
- DynamoDB: Enable encryption

**In-Transit (data moving):**
- TLS/SSL for all connections
- HTTPS for web traffic
- VPN for site-to-site
- Never send plaintext

#### Secrets Manager & Parameter Store

**Secrets Manager:**
- Store sensitive data (passwords, API keys, DB credentials)
- Automatic rotation
- Encryption with KMS
- Audit trail

**Parameter Store:**
- Lighter-weight than Secrets Manager
- Store configuration values
- Free tier available

**Rotation Patterns:**
- Database credentials: Auto-rotate
- API keys: Manual rotation
- Certificates: Auto-renewal

#### Data Classification & Access Guardrails

**Classification:**
- Identify sensitive data (PII, financial)
- Apply different controls based on classification
- Example: PII data only accessible from specific VPC

**Guardrails:**
- Prevent downloading sensitive data to personal devices
- Restrict copy-paste in databases
- Audit all access to sensitive data

---

### 11:10 – 11:40 | Pillar 5: Incident Response

#### Incident Response Lifecycle (AWS Model)

**Phases:**

1. **Detection & Analysis:**
   - Identify incident
   - Understand scope & impact
   - Activate IR team

2. **Containment:**
   - Stop attack from spreading
   - Isolate affected systems
   - Preserve evidence

3. **Eradication:**
   - Remove threat
   - Patch vulnerabilities
   - Update configurations

4. **Recovery:**
   - Restore systems
   - Verify integrity
   - Monitor for recurrence

5. **Post-Incident:**
   - Document lessons learned
   - Update playbooks
   - Improve controls

#### IR Playbooks for Common Scenarios

**Playbook 1: Compromised IAM Key**
```
Detection → Disable IAM user
         → Audit recent actions (CloudTrail)
         → Check for unauthorized resources
         → Rotate credentials
         → Enable MFA
         → Update security policies
```

**Playbook 2: S3 Public Exposure**
```
Detection → Check CloudTrail for who made change
         → Identify affected data
         → Restrict access immediately
         → Scan for data exfiltration
         → Notify affected customers
         → RCA & process improvement
```

**Playbook 3: EC2 Malware Detection**
```
Detection → Isolate EC2 from network
         → Create snapshot for forensics
         → Analyze logs (CloudTrail, VPC Flow Logs)
         → Terminate instance
         → Patch other similar instances
         → Update antivirus/EDR rules
```

#### Snapshot, Isolation, Evidence Collection

**Quick Response:**
1. **Snapshot** infected system (preserve evidence)
2. **Isolate** from network (stop propagation)
3. **Collect evidence** (logs, memory dumps)
4. **Analyze offline** (forensics)

#### Auto-response with Lambda/Step Functions

**Pattern:**
```
GuardDuty finding → EventBridge rule → Lambda/Step Functions
                 → Automated response (isolate, snapshot, notify)
                 → Create ticket in ticketing system
```

**Example Auto-responses:**
- Disable IAM user on excessive failed logins
- Isolate EC2 instance on malware detection
- Restrict security group on port scanning

**Benefits:**
- Faster response time (seconds vs hours)
- Consistent playbook execution
- Reduce manual errors

---

### 11:40 – 12:00 | Wrap-Up & Q&A

#### 5 Pillars Summary

1. **IAM:** Modern identity, least privilege, MFA
2. **Detection:** Continuous monitoring, alerting, automation
3. **Infrastructure:** Network segmentation, WAF, firewalls
4. **Data:** Encryption at-rest & in-transit, secrets management
5. **Incident Response:** Playbooks, automation, learning

#### Common Pitfalls & Vietnamese Business Context

**Common Mistakes:**
- ❌ Long-term access keys for applications
- ❌ S3 buckets public by accident
- ❌ No encryption enabled
- ❌ No backup/disaster recovery
- ❌ No incident response plan

**Vietnamese Context:**
- Growing regulatory requirements (PDPA)
- Legacy systems migration security challenges
- Talent shortage in security
- Need for managed security services

#### Security Learning Roadmap

**Certifications:**
1. **AWS Security Specialty:** Technical depth
2. **Solutions Architect Professional:** Security architecture
3. **Advanced Security on AWS:** Expert level

**Continuous Learning:**
- AWS Security workshops & webinars
- Security conferences (BSides, OWASP)
- Practice labs & challenges
- Join security communities

---

## Những Kiến Thức Chính Mà Tôi Thu Lĩnh

### 1. **Security is Not a Feature, It's a Mindset** 🧠

- **Least Privilege:** Only grant what's needed
- **Zero Trust:** Never trust, always verify
- **Defense in Depth:** Multiple layers of protection
- **These principles** applicable across all cloud services

### 2. **IAM is Foundation of Cloud Security** 🔐

- Modern IAM ≠ old on-prem access control
- Roles > Users for most scenarios
- MFA mandatory for sensitive access
- Regular audits & access removal essential

### 3. **Detection & Monitoring are Continuous** 👁️

- CloudTrail provides audit trail
- GuardDuty finds threats automatically
- Security Hub aggregates all signals
- Automation responds faster than humans

### 4. **Data Protection is Non-negotiable** 🔒

- Encryption at-rest & in-transit
- Key management critical
- Secrets rotation automated
- Access to sensitive data audited

### 5. **Incident Response Needs Preparation** 🚨

- Playbooks written before incidents
- Automation speeds response
- Evidence preservation critical
- Postmortems drive improvement

### 6. **Security Requires Organizational Support** 🤝

- Not just infosec team responsibility
- Developers, ops, leadership all involved
- Budget allocation essential
- Training & awareness important

---

## Giá Trị Đạt Được

### Kỹ Năng & Kiến Thức

- ✅ **IAM Architecture:** Modern identity management patterns
- ✅ **Detection Strategy:** Continuous monitoring & alerting
- ✅ **Network Security:** VPC design, WAF, firewalls
- ✅ **Data Protection:** Encryption strategies & key management
- ✅ **Incident Response:** Playbooks & automation
- ✅ **Compliance:** Well-Architected framework knowledge

### Practical Confidence

- ✅ **Can Design:** Secure AWS infrastructure
- ✅ **Can Implement:** IAM policies correctly
- ✅ **Can Monitor:** Detect threats continuously
- ✅ **Can Respond:** To incidents systematically
- ✅ **Can Audit:** AWS environment for misconfigurations

### Mindset Shift

- ✅ **Understand Shared Responsibility:** Security depends on both AWS & customer
- ✅ **Appreciate Defense in Depth:** No single magic solution
- ✅ **Value Automation:** Faster & more consistent
- ✅ **Embrace Continuous Improvement:** Learning from incidents
- ✅ **Think like attacker:** Anticipate threats

---

## Công Cụ & Công Nghệ Học Được

| Công Cụ | Ứng Dụng | Ghi Chú |
|---------|---------|---------|
| **IAM** | Identity & access control | Users, roles, policies |
| **IAM Identity Center** | Enterprise SSO | Replace IAM users |
| **CloudTrail** | API audit logging | Organization-level |
| **GuardDuty** | Threat detection | ML-based anomalies |
| **Security Hub** | Security dashboard | Centralized findings |
| **VPC Flow Logs** | Network monitoring | Traffic analysis |
| **WAF** | Web application firewall | Attack prevention |
| **Shield** | DDoS protection | Free + Advanced |
| **Network Firewall** | VPC-level firewall | Stateful inspection |
| **KMS** | Key management | Encryption keys |
| **Secrets Manager** | Secret storage | Rotation & audit |
| **Parameter Store** | Configuration store | Lightweight secrets |
| **EventBridge** | Event routing | Automation trigger |
| **Lambda** | Serverless compute | Auto-response functions |

---

## Kết Luận

**AWS Cloud Mastery Series #3** là workshop bổ ích về security:

✨ **Điểm mạnh:**
- 5 Pillars framework rất comprehensive
- Balance giữa theory & practical examples
- Real-world incident scenarios relatable
- Modern IAM & Zero Trust concepts
- 355 engaged security-focused participants

💫 **Bài học quan trọng:**
- **Security is Shared Responsibility:** AWS provides tools, customer implements
- **Least Privilege always:** Never grant unnecessary access
- **Detect & respond quickly:** Automation critical
- **Data protection layers:** Encryption + access control
- **Incident response requires prep:** Playbooks before crisis

🎯 **Practical Takeaways:**
- Có thể design secure AWS infrastructure
- Biết cách implement modern IAM
- Hiểu detection & monitoring strategies
- Có incident response playbook template
- Ready cho security roles/responsibilities

🔐 **Security Career:**
- High demand for cloud security professionals
- Certifications valuable (Security Specialty)
- Continuous learning (threat landscape evolves)
- Impact on entire organization

---

**Cảm ơn AWS Community vì đã tổ chức một security workshop rất bổ ích!** 🙏

Hôm nay tôi không chỉ học tools mà **understand security philosophy & culture** of cloud.

**Least Privilege, Zero Trust, Defense in Depth** - simple principles nhưng powerful when applied consistently.

**I'm committed to building secure cloud systems!** 🔐🛡️✨