---
title: "Event 4"
date: 2024-10-15T00:00:00Z
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---



# Bài Thu Hoạch "AWS Cloud Mastery Series #2 - DevOps on AWS"

---

## Thông Tin Cơ Bản Về Sự Kiện

**Tên sự kiện:** AWS Cloud Mastery Series #2 - DevOps on AWS

**Ngày tổ chức:** Thứ Hai, 17 tháng 11 năm 2025

**Thời gian:** 08:30 - 17:00 (Full-day workshop)

**Địa điểm:** AWS Vietnam Office, Bitexco Financial Tower, Quận 1, TP. Hồ Chí Minh

**Tổ chức bởi:** AWS Community, Kha Van

**Số lượng người tham dự:** 316 sinh viên & professionals

**Vai trò của tôi:** Người tham dự, Active Learner

---

## Mục Đích Của Sự Kiện

Sự kiện **AWS Cloud Mastery Series #2** được tổ chức nhằm:

- 🎯 Giới thiệu **DevOps culture & mindset** - không chỉ tools
- 🔧 Thực hành AWS DevOps services (CI/CD, IaC, containers)
- 🚀 Xây dựng **automated deployment pipelines**
- 📦 Hiểu containers & microservices architecture
- 📊 Implement monitoring & observability solutions
- 💡 Học best practices từ startups & enterprises

---

## Chương Trình Chi Tiết

### **PHIÊN SÁNG (08:30 - 12:00)**

---

### 08:30 – 09:00 | Welcome & DevOps Mindset

**Nội dung:**
- Recap từ AI/ML session (Series #1)
- **DevOps Culture & Principles:**
  - Breaking silos between Dev & Ops
  - Shared responsibility & automation mindset
  - Continuous improvement philosophy
  - Fail fast, learn faster

**DevOps Key Metrics (DORA):**
- **Deployment Frequency:** Như nhiều lần deploy mỗi ngày/tuần
- **Lead Time for Changes:** Time từ commit đến production
- **Mean Time To Recovery (MTTR):** Thời gian fix incidents
- **Change Failure Rate:** % deployments gây incidents

**Why these metrics matter:**
- Measure organizational DevOps maturity
- Track improvement over time
- Benchmark against industry standards

---

### 09:00 – 10:30 | AWS DevOps Services – CI/CD Pipeline

#### Source Control Strategy

**AWS CodeCommit:**
- Git-based version control (AWS-managed)
- Alternative to GitHub/GitLab
- Integration with AWS services

**Git Strategies:**
- **GitFlow:** feature branches, release branches, hotfixes
  - Best for: Formal releases, multiple environments
  - Complexity: Higher, more branches
  
- **Trunk-based Development:** commit frequently to main
  - Best for: Continuous deployment, faster feedback
  - Requires: Strong CI/CD pipeline, good testing

**Best Practices:**
- Code reviews mandatory
- Pull requests tied to issues
- Branch protection rules
- Commit message standards

#### Build & Test: CodeBuild

**CodeBuild Features:**
- Fully managed build service
- Supports: Java, Python, Node.js, Docker, etc.
- Buildspec.yml for configuration
- Parallel test execution

**Build Pipeline:**
```
Source → Compile → Unit Tests → Integration Tests → Artifacts
```

**Testing Strategy:**
- Unit tests (fast feedback)
- Integration tests (component interaction)
- End-to-end tests (user flows)
- Performance tests (load testing)

#### Deployment: CodeDeploy

**Deployment Strategies:**

1. **Blue/Green Deployment:**
   - Maintain 2 identical environments
   - Switch traffic when new version ready
   - Pros: Zero downtime, instant rollback
   - Cons: Requires double resources

2. **Canary Deployment:**
   - Route small % traffic to new version
   - Monitor metrics
   - Gradually increase traffic
   - Pros: Detect issues early with minimal impact
   - Cons: Takes time

3. **Rolling Deployment:**
   - Gradually replace instances
   - Pros: No extra resources needed
   - Cons: Brief service degradation possible

**Rollback Strategy:**
- Automated rollback on health check failures
- Manual rollback capability
- Database migration reversibility

#### Orchestration: CodePipeline

**Pipeline Stages:**
```
Source → Build → Test → Deploy → Production
```

**Features:**
- Trigger on code push
- Approval gates before production
- Artifact management
- Pipeline visualization
- Parallel execution support

#### Live Demo: Full CI/CD Pipeline

**Demo Flow:**
1. Developer pushes code to CodeCommit
2. Webhook triggers CodePipeline
3. CodeBuild runs tests & builds artifact
4. CodeDeploy deploys to staging
5. Manual approval gate
6. Deploys to production (Blue/Green)
7. Automated rollback if health checks fail

**Key Insight:** "From code commit to production in minutes, safely"

---

### 10:30 – 10:45 | Break

---

### 10:45 – 12:00 | Infrastructure as Code (IaC)

#### AWS CloudFormation

**Khái niệm:**
- Describe AWS infrastructure as YAML/JSON templates
- Infrastructure becomes code = version control, reproducibility
- Stack management (create, update, delete)

**Template Structure:**
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: 'Web application stack'
Parameters:
  Environment: Type: String (dev, staging, prod)
Resources:
  - EC2 Instances
  - RDS Database
  - Security Groups
  - Load Balancer
Outputs:
  - Application URLs
```

**Key Features:**
- **Stack Operations:** Create, update, delete infrastructure
- **Change Sets:** Preview changes before applying
- **Drift Detection:** Detect manual changes to infrastructure
- **Nested Stacks:** Modular, reusable templates

**Use Cases:**
- Replicate environments (dev → staging → prod)
- Disaster recovery (rebuild infrastructure)
- Multi-region deployments
- Compliance automation

#### AWS CDK (Cloud Development Kit)

**Khái niệm:**
- Write infrastructure using programming languages (Python, TypeScript, Java)
- Higher-level abstractions than CloudFormation
- Compiles to CloudFormation templates

**Advantages vs CloudFormation:**
- **Language-based:** Type safety, IDE support, loops/conditions
- **Constructs:** Pre-built patterns (L1, L2, L3 levels)
- **Reusable:** Code libraries & patterns
- **Less verbose:** More concise than YAML

**Example (TypeScript):**
```typescript
new ec2.Instance(this, 'WebServer', {
  vpc: vpc,
  instanceType: ec2.InstanceType.of(
    ec2.InstanceClass.T3,
    ec2.InstanceSize.MEDIUM
  ),
  machineImage: new ec2.AmazonLinuxImage(),
});
```

**When to use:**
- **CloudFormation:** Simple infrastructure, learning
- **CDK:** Complex patterns, reusable libraries, large projects

#### Demo: Deploying with CloudFormation & CDK

**Demo 1: CloudFormation**
- Create template for web application
- Deploy stack
- Update infrastructure
- Show change set
- Detect drift

**Demo 2: CDK**
- Write infrastructure in TypeScript
- Synthesize to CloudFormation
- Deploy using CDK
- Show generated template

**Key Comparison:**
| Aspect | CloudFormation | CDK |
|--------|---|---|
| Learning Curve | Easier | Steeper |
| Flexibility | Good | Excellent |
| Code Reuse | Nested stacks | NPM packages |
| Verbosity | More YAML | Less code |

---

### 12:00 – 13:00 | Lunch Break (Self-arranged)

---

### **PHIÊN CHIỀU (13:00 - 17:00)**

---

### 13:00 – 14:30 | Container Services on AWS

#### Docker Fundamentals

**Containerization Concept:**
- Package application + dependencies into container
- Same behavior on laptop, staging, production
- Lightweight vs VMs

**Microservices Architecture:**
- Monolith → Microservices
- Each service: independent, scalable, deployable
- Communication: APIs, message queues
- Benefits: Scalability, resilience, technology diversity

**Container Benefits:**
- Consistent environment
- Faster deployment
- Resource efficiency
- Scaling agility

#### Amazon ECR (Elastic Container Registry)

**Features:**
- Push/pull Docker images
- Image scanning for vulnerabilities
- Lifecycle policies (auto-delete old images)
- Cross-account access
- Integration with CodeBuild

**Best Practices:**
- Tag images with version/commit hash
- Use lifecycle policies to manage storage
- Enable image scanning
- Private repositories by default

#### Amazon ECS vs EKS

**ECS (Elastic Container Service):**
- AWS-native orchestration
- Simpler, less operational overhead
- EC2 or Fargate launch types
- Integrated with AWS services (ALB, IAM, CloudWatch)

**EKS (Elastic Kubernetes Service):**
- Kubernetes orchestration (industry standard)
- More powerful, steeper learning curve
- Self-healing, auto-scaling
- Multi-cloud portability

**Comparison:**
- **Choose ECS:** AWS-first, simpler operations
- **Choose EKS:** Need Kubernetes portability, complex orchestration

**Deployment Strategies:**
- Rolling updates (no downtime)
- Blue/green deployments
- Canary releases

#### AWS App Runner

**Simplified Container Deployment:**
- Deploy from source code or container image
- Automatic scaling, load balancing
- No need to manage infrastructure
- Perfect for: Startups, simple applications

**Use Case:** Developer push code → automatic CI/CD → running service

#### Demo & Case Study: Microservices Deployment

**Architecture Comparison:**
1. **Monolith on EC2:** Simple but scaling difficult
2. **Microservices on ECS:** Managed, AWS-integrated
3. **Microservices on EKS:** Powerful, portable
4. **Serverless with Lambda:** Ultimate simplicity

**Real-world Case Study:**
- Startup: App Runner
- Scale-up: Migrate to ECS
- Enterprise: Kubernetes (EKS)

---

### 14:30 – 14:45 | Break

---

### 14:45 – 16:00 | Monitoring & Observability

#### CloudWatch

**Metrics:**
- Track application & infrastructure metrics
- Custom metrics from application
- Automated dashboards
- Real-time data visualization

**Logs:**
- Centralized log aggregation
- Query with Insights
- Real-time monitoring
- Log retention policies

**Alarms:**
- Trigger on metric thresholds
- SNS notifications
- Lambda actions
- Auto-scaling triggers

**Best Practices:**
- Monitor business metrics (not just infrastructure)
- Use log grouping by application
- Meaningful alarm thresholds

#### AWS X-Ray

**Distributed Tracing:**
- Track requests across services
- Visualize architecture
- Identify bottlenecks

**Insights:**
- Performance analysis
- Error attribution
- Service dependency map

**Use Cases:**
- Debug slow requests
- Understand service interactions
- Optimize performance

#### Demo: Full-Stack Observability Setup

**Demo Flow:**
1. Application sending metrics to CloudWatch
2. Logs aggregated & queried
3. X-Ray tracing microservices
4. Dashboard showing health
5. Alert triggering on anomaly

**Architecture:**
```
Application → CloudWatch (metrics & logs)
           → X-Ray (distributed tracing)
           → Dashboard (visualization)
           → Alarms (automated response)
```

**Key Insight:** "If you're not monitoring it, you can't improve it"

---

### 16:00 – 16:45 | DevOps Best Practices & Case Studies

#### Deployment Strategies

**Feature Flags:**
- Decouple deployment from release
- Deploy to production but feature hidden
- Gradual rollout to users
- A/B testing capability

**A/B Testing:**
- Test new features with subset of users
- Data-driven decisions
- Reduce risk

#### Automated Testing & CI/CD Integration

**Testing Pyramid:**
```
        E2E Tests (few)
      Integration Tests (some)
    Unit Tests (many)
```

**CI/CD Integration:**
- Run tests on every commit
- Fail fast, fail early
- Prevent bad code from reaching production

#### Incident Management & Postmortems

**Incident Response:**
- Automated alerts
- On-call rotation
- Runbooks for common issues
- Timeline of events

**Postmortems:**
- Document what happened
- Root cause analysis
- Action items to prevent recurrence
- Blameless culture

#### Case Studies

**Startup DevOps Transformation:**
- Started: Manual deployments
- Problem: Slow release cycle
- Solution: Implemented CI/CD
- Result: Deploy 10x per day, faster feature delivery

**Enterprise DevOps Journey:**
- Started: Monolith, quarterly releases
- Problem: Risk, slow innovation
- Solution: Microservices, automated deployment
- Result: Competitive advantage, reduced MTTR

---

### 16:45 – 17:00 | Q&A & Wrap-up

**Topics:**
- DevOps career pathways:
  - DevOps Engineer
  - Platform Engineer
  - Site Reliability Engineer (SRE)
  - Cloud Architect

**AWS Certification Roadmap:**
- AWS Solutions Architect Associate
- AWS DevOps Engineer Professional
- AWS Security Specialty

**Next Steps:**
- Practice labs
- Build personal project
- Join DevOps community

---

## Những Kiến Thức Chính Mà Tôi Thu Lĩnh

### 1. **DevOps là Mindset, Không Chỉ Tools** 🎯

- **Collaboration:** Dev + Ops + QA working together
- **Automation:** Everything automated possible
- **Measurement:** Data-driven improvements
- **Culture:** Blameless postmortems, learning focus

### 2. **CI/CD Pipeline là Backbone của Modern Development** 🔄

- Automated testing & deployment
- Shorter feedback loop
- Reduced manual errors
- Faster time to market

### 3. **Infrastructure as Code Makes Everything Reproducible** 📝

- Version control infrastructure
- Disaster recovery simplified
- Multi-environment consistency
- CloudFormation vs CDK: both valuable

### 4. **Containers Changed How We Deploy** 📦

- Consistency across environments
- Microservices becomes practical
- Kubernetes (EKS) vs AWS-native (ECS)
- Choose based on your needs

### 5. **Observability is Essential for Production** 📊

- Can't improve what you don't measure
- Monitoring alone not enough - need traces
- Proactive alerting saves money
- Postmortems drive improvement

### 6. **DevOps is a Career, Not Just a Role** 💼

- Multiple specializations: DevOps, Platform, SRE
- High demand, good salaries
- Continuous learning (tools evolve quickly)
- Impact on entire organization

---

## Giá Trị Đạt Được

### Kỹ Năng & Kiến Thức

- ✅ **CI/CD Mastery:** Understand full pipeline from code to production
- ✅ **Infrastructure as Code:** Both CloudFormation & CDK
- ✅ **Container Orchestration:** ECS, EKS, App Runner comparisons
- ✅ **Observability:** CloudWatch, X-Ray, comprehensive monitoring
- ✅ **Deployment Strategies:** Blue/green, canary, rolling updates
- ✅ **Best Practices:** Testing, incident management, postmortems

### Practical Confidence

- ✅ **Can Design:** CI/CD pipelines for applications
- ✅ **Can Deploy:** Infrastructure using IaC
- ✅ **Can Orchestrate:** Container deployments at scale
- ✅ **Can Monitor:** Full-stack observability solutions
- ✅ **Can Respond:** To incidents systematically

### Mindset Shift

- ✅ **Appreciate DevOps Culture:** Beyond just tools
- ✅ **Automation Focus:** Save time, reduce errors
- ✅ **Data-Driven:** Metrics & measurements matter
- ✅ **Continuous Improvement:** DevOps is journey, not destination
- ✅ **Blameless Culture:** Learning from incidents, not blame

---

## Công Cụ & Công Nghệ Học Được

| Công Cụ | Ứng Dụng | Ghi Chú |
|---------|---------|---------|
| **AWS CodeCommit** | Source control | Git-based, AWS-managed |
| **AWS CodeBuild** | Build & test | Parallel execution, Docker support |
| **AWS CodeDeploy** | Automated deployment | Blue/green, canary, rolling |
| **AWS CodePipeline** | CI/CD orchestration | Full pipeline automation |
| **CloudFormation** | IaC - YAML/JSON | Template-based infrastructure |
| **AWS CDK** | IaC - Programming | Language-based constructs |
| **Amazon ECR** | Container registry | Image storage & scanning |
| **Amazon ECS** | Container orchestration | AWS-native, simpler |
| **Amazon EKS** | Kubernetes orchestration | Industry standard, portable |
| **AWS App Runner** | Simplified containers | Perfect for startups |
| **CloudWatch** | Monitoring & logging | Metrics, logs, alarms |
| **AWS X-Ray** | Distributed tracing | Performance insights |

---

## Kết Luận

**AWS Cloud Mastery Series #2** là một full-day workshop cực kỳ toàn diện:

✨ **Điểm mạnh:**
- Full-day format (8.5 hours) cover rất đầy đủ
- Balance giữa lý thuyết & hands-on demos
- Real-world case studies rất hữu ích
- DevOps mindset được tôn vinh, không chỉ tools
- 316 engaged participants, cộng đồng mạnh

💫 **Bài học quan trọng:**
- **DevOps là phong trào:** Not just tools, but culture
- **Automation saves time:** Invest in CI/CD now
- **IaC essential:** CloudFormation or CDK, both important
- **Containers are standard:** ECS or EKS, master one deeply
- **Observability critical:** Can't improve what you don't measure

🎯 **Practical Impact:**
- Có thể thiết kế CI/CD pipeline cho projects
- Có thể deploy infrastructure as code
- Hiểu deployment strategies & tradeoffs
- Biết cách setup monitoring & alerting
- Sẵn sàng cho DevOps roles

🚀 **Career Implications:**
- DevOps là high-demand field
- Multiple specializations (Platform, SRE, etc.)
- Continuous learning required (tools evolve)
- Good salaries, impact on org

---

**Cảm ơn AWS Community vì đã tổ chức một full-day workshop tuyệt vời!** 🙏

Ngày hôm nay tôi không chỉ học tools mà **understand mindset & culture** behind DevOps movement.

**CI/CD, IaC, Containers, Monitoring** - những khối tương tự Lego, cộng lại tạo thành powerful DevOps platform.

**I'm ready to build better, deploy faster, and monitor smarter!** 🚀✨