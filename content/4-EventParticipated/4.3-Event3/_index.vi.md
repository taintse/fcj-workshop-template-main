---
title: "Event 3"
date: 2024-10-15T00:00:00Z
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---



# Bài Thu Hoạch "AWS Cloud Mastery Series #1 - AI/ML/GenAI on AWS"

---

## Thông Tin Cơ Bản Về Sự Kiện

**Tên sự kiện:** AWS Cloud Mastery Series #1 - AI/ML/GenAI on AWS

**Ngày tổ chức:** Thứ Bảy, 15 tháng 11 năm 2025

**Thời gian:** 08:30 - 12:00

**Địa điểm:** AWS Vietnam Office, Bitexco Financial Tower, Quận 1, TP. Hồ Chí Minh

**Tổ chức bởi:** AWS Community, Kha Van

**Số lượng người tham dự:** 348 sinh viên & professionals

**Vai trò của tôi:** Người tham dự, Active Learner

---

## Mục Đích Của Sự Kiện

Sự kiện **AWS Cloud Mastery Series #1** được tổ chức nhằm:

- 🎯 Giới thiệu toàn cảnh AI/ML landscape tại Việt Nam
- 🤖 Tập trung vào **Generative AI** - công nghệ hot nhất hiện nay
- 💼 Thực hành hands-on với các AWS AI/ML services
- 🚀 Xây dựng chatbot GenAI thực tế using Amazon Bedrock
- 📚 Hiểu sâu về RAG, Prompt Engineering, Agents
- 🤝 Tạo cộng đồng học tập về AI/ML trên AWS

---

## Chương Trình Chi Tiết

### 08:30 – 09:00 | Đón Tiếp & Giới Thiệu

**Nội dung:**
- Đăng ký & networking cho participants
- Giới thiệu overview của workshop
- Mục tiêu học tập chính
- Ice-breaker activity
- Tổng quan về AI/ML landscape ở Việt Nam

**Ý nghĩa:**
- Tạo không khí warm & collaborative
- Giúp các participants quen biết nhau
- Set expectations cho buổi workshop
- Context về tình hình AI/ML tại Việt Nam: spikes in adoption, talent shortage

---

### 09:00 – 10:30 | AWS AI/ML Services Overview

#### Amazon SageMaker - End-to-End ML Platform

**Khái niệm chính:**
- **SageMaker là gì:** Fully managed ML platform của AWS
- **Use cases:** Regression, classification, clustering, time series forecasting
- **Architecture:** Data preparation → Training → Deployment → Monitoring

#### Data Preparation & Labeling

**Các tính năng quan trọng:**
- **Data Wrangler:** Visual data preparation tool
- **Ground Truth:** Labeling service for training data
- **Feature Store:** Centralized repository for ML features
- **Data Quality Monitoring:** Detect data drift & anomalies

#### Model Training, Tuning & Deployment

**Training capabilities:**
- **Built-in algorithms:** Xgboost, linear learner, image classification, etc.
- **Hyperparameter Optimization:** Automatic tuning
- **Distributed Training:** Multi-GPU/Multi-node training
- **Cost optimization:** Spot instances support

**Deployment options:**
- **Real-time endpoints:** Low-latency predictions
- **Batch transform:** Large-scale inference
- **Edge deployment:** SageMaker Edge Manager
- **Multi-model endpoints:** Host multiple models efficiently

#### Integrated MLOps Capabilities

**Pipeline & Automation:**
- **SageMaker Pipelines:** Orchestrate end-to-end ML workflows
- **Model Registry:** Version control & governance for models
- **Model Monitor:** Track model performance in production
- **Automated retraining:** Trigger retraining based on metrics

#### Live Demo: SageMaker Studio Walkthrough

**Demo Features:**
- Studio interface & project setup
- Data exploration & visualization
- Model training & hyperparameter tuning
- Deployment to endpoints
- Monitoring & performance tracking

**Key Takeaway:** From data to production model in minutes, not weeks

---

### 10:30 – 10:45 | Coffee Break

- Ngắt giải, networking & discussion
- Q&A informal với instructors

---

### 10:45 – 12:00 | Generative AI with Amazon Bedrock

#### Foundation Models Comparison

**Available Models:**
- **Claude (Anthropic):** Advanced reasoning, safety-focused
- **Llama (Meta):** Open source, flexible, efficient
- **Titan (AWS):** Multi-lingual, optimized for AWS integration

**So sánh:**
- **Capabilities:** Reasoning, code generation, multilingual, safety
- **Performance:** Speed vs accuracy tradeoff
- **Cost:** Token-based pricing
- **Selection guide:** Choose based on use case requirements

**Key insight:** Không phải model nào lớn nhất là tốt nhất, mà là phù hợp với use case

#### Prompt Engineering Techniques

**Best Practices:**
- **Clear Instructions:** Specific, detailed prompts
- **Examples:** Provide examples for in-context learning
- **Role-playing:** Give LLM a role/persona
- **Chain-of-Thought:** Ask model to think step-by-step
- **Few-shot Learning:** Show 2-3 examples before asking
- **Temperature & Top-p:** Control randomness of outputs

**Real Examples:**
- ❌ Bad: "Summarize this"
- ✅ Good: "Summarize this document in 3 bullet points, focusing on financial impact"

#### Retrieval-Augmented Generation (RAG)

**Problem Statement:**
- LLMs có knowledge cutoff (outdated information)
- Hallucinations - LLMs tạo ra information không chính xác
- Không có access tới private/proprietary data

**RAG Solution:**
- **Retrieve:** Tìm relevant documents từ knowledge base
- **Augment:** Combine retrieved docs with user query
- **Generate:** LLM generate answer based on retrieved context

**Architecture:**
```
User Query → Embedding → Similarity Search → Retrieve Docs 
→ Combine Query + Docs → LLM → Response
```

**Knowledge Base Integration:**
- Document ingestion & chunking
- Embedding generation & storage
- Vector database (OpenSearch, Pinecone, etc.)
- Similarity search & ranking

**Benefits:**
- Factual accuracy (grounded in real documents)
- Up-to-date information (control via document updates)
- Private data access (proprietary documents)
- Transparency (show source documents)

#### Bedrock Agents

**Multi-Step Workflows:**
- Agents có khả năng break down tasks thành steps
- **Planning:** Quyết định action sequence
- **Reasoning:** Evaluate results & adjust
- **Tool use:** Call APIs, databases, etc.

**Tool Integrations:**
- AWS services: Lambda, DynamoDB, S3
- External APIs: weather, stock prices, CRM
- Custom tools: Define custom actions

**Use Cases:**
- Customer service automation
- Data analysis & reporting
- Process automation
- Decision support systems

#### Guardrails for Safety

**Content Filtering:**
- **Hate speech:** Detect & filter inappropriate language
- **Violence:** Flag violent content
- **Adult content:** Content moderation
- **Custom filters:** Define domain-specific guardrails

**Safety Features:**
- Input filtering: Screen user prompts
- Output filtering: Check LLM responses
- Monitoring & logging: Track safety metrics
- Customizable thresholds: Define sensitivity levels

**Why important:** Prevent misuse, ensure compliance, maintain brand trust

#### Live Demo: Building GenAI Chatbot with Bedrock

**Demo Scenario:** E-commerce customer support chatbot

**Steps:**
1. **Setup:** Create Bedrock agent
2. **Connect Knowledge Base:** Upload FAQ documents
3. **Define Tools:** Connect to product catalog API
4. **Test Interactions:**
   - Simple Q&A: "What's your return policy?"
   - Multi-step: "Show me laptops under $1000 & their warranty"
   - Context awareness: Remember conversation history

**Code snippet:**
```python
import boto3
bedrock = boto3.client('bedrock')
response = bedrock.converse(
    model_id='anthropic.claude-3-sonnet',
    messages=[{
        'role': 'user',
        'content': 'What warranty do you offer?'
    }],
    guardrail_config={
        'strength': 'STANDARD'
    }
)
```

**Key Takeaway:** Build production-ready GenAI apps trong minutes

---

### 12:00 | Lunch Break (Self-arranged)

---

## Những Kiến Thức & Cảm Hứng Chính

### 1. **GenAI là Paradigm Shift, Không Chỉ Incremental Improvement** 🚀

**Trước GenAI:**
- ML: Supervised learning, classification, prediction
- Limited to structured data
- Extensive feature engineering needed

**Với GenAI:**
- Foundation models learn từ unstructured text/images
- Zero-shot, few-shot learning (in-context learning)
- Broad applicability across domains

**Implication:** AI skills landscape đang thay đổi fundamentally

### 2. **Amazon SageMaker Democratizes ML** 💼

**Trước SageMaker:**
- ML projects lâu, phức tạp, cần chuyên gia
- High barrier to entry

**Với SageMaker:**
- Low-code/no-code approach
- Fully managed infrastructure
- End-to-end pipeline automation
- MLOps best practices built-in

**Insight:** AI/ML không còn exclusive cho data scientists

### 3. **RAG Solves Real-World GenAI Problems** 🎯

**Hallucination Problem:**
- LLMs tạo convincing but wrong answers
- Knowledge cutoff (outdated info)

**RAG Solution:**
- Ground responses in actual documents
- Always up-to-date
- Auditable (show sources)

**Use Cases:**
- Customer support (grounded in company docs)
- Internal knowledge management
- Educational platforms
- Research assistance

### 4. **Agents Represent the Future of AI Automation** 🤖

**Current Chatbots:**
- Respond but don't take action
- Limited to text output

**Agents:**
- Multi-step reasoning
- Tool use & integration
- Autonomous execution
- Problem-solving capability

**Examples:**
- Book appointment + send reminder + update calendar
- Analyze data + generate report + send email
- Research question + synthesize info + update wiki

### 5. **Responsible AI Matters** 🛡️

**Guardrails:**
- Safety filters prevent misuse
- Content moderation
- Compliance with regulations
- Brand protection

**Why important:**
- Users may provide harmful prompts intentionally/unintentionally
- LLMs can amplify biases
- Regulatory requirements (data privacy, safety standards)

### 6. **Hands-On Experience Accelerates Learning** 💻

**Live Demos:**
- See real SageMaker interface
- Understand workflow step-by-step
- See actual code examples
- Know common pitfalls

**Biggest Insight:** "It's much easier than I thought to build GenAI apps"

---

## Giá Trị Đạt Được

### Kỹ Năng & Kiến Thức

- ✅ **Comprehensive Overview:** Hiểu full stack của AI/ML on AWS
- ✅ **SageMaker Proficiency:** Biết cách use SageMaker cho ML projects
- ✅ **GenAI Concepts:** Deep dive into RAG, agents, prompt engineering
- ✅ **Practical Implementation:** Hands-on experience building real solutions
- ✅ **Best Practices:** Security, governance, monitoring, cost optimization

### Mindset & Understanding

- ✅ **GenAI is Accessible:** Not just for PhDs anymore
- ✅ **Responsible AI:** Safety & ethics matter
- ✅ **Multi-model Approach:** Different models for different use cases
- ✅ **Production-Ready:** From prototype to production with SageMaker
- ✅ **Future is Agents:** Beyond simple chatbots

### Practical Confidence

- ✅ **Can Build:** GenAI chatbots using Bedrock
- ✅ **Can Deploy:** ML models using SageMaker
- ✅ **Can Optimize:** RAG for knowledge-grounded responses
- ✅ **Can Monitor:** Track model performance & safety
- ✅ **Next Steps Clear:** Know where to go for deeper learning

---

## Công Cụ & Công Nghệ Học Được

| Công Nghệ | Ứng Dụng | Ghi Chú |
|-----------|---------|---------|
| **Amazon SageMaker** | End-to-end ML platform | Training, tuning, deployment |
| **SageMaker Studio** | ML development environment | Visual interface |
| **Amazon Bedrock** | Generative AI API | Foundation models access |
| **Claude (Anthropic)** | Advanced reasoning model | Best for complex tasks |
| **Llama (Meta)** | Open source LLM | Flexible, cost-effective |
| **Titan (AWS)** | AWS-native model | Multi-lingual, optimized |
| **RAG Architecture** | Knowledge-grounded generation | Accuracy + up-to-date |
| **Prompt Engineering** | LLM optimization | Technique-based improvement |
| **Bedrock Agents** | Multi-step AI workflows | Autonomous task execution |
| **Guardrails** | Safety & content filtering | Responsible AI |

---

## Kết Luận

**AWS Cloud Mastery Series #1** là workshop rất chất lượng:

✨ **Điểm mạnh:**
- Chủ đề timely & relevant (GenAI is the hottest topic)
- Balance giữa theory & hands-on practice
- Live demos thực tế & executable
- Instructor expertise rõ ràng
- Cộng đồng 348 learners engaged
- AWS veteran perspective & best practices

💫 **Bài học quan trọng:**
- **GenAI democratized:** Anyone can build GenAI apps now
- **SageMaker is powerful:** Full ML lifecycle support
- **RAG solves problems:** Ground GenAI with real data
- **Responsible AI crucial:** Safety & ethics matter
- **Agents are next:** Beyond simple text generation

🎯 **Practical takeaways:**
- Có thể bắt đầu build GenAI chatbots ngay
- SageMaker là go-to platform cho ML projects
- RAG pattern applicable cho many use cases
- Prompt engineering là practical skill (not magic)

🚀 **Next steps để go deeper:**
- Thử hands-on labs trên AWS
- Build một personal GenAI project
- Explore advanced SageMaker features
- Attend AWS Cloud Mastery Series #2, #3, etc.

---

**Cảm ơn AWS Community vì đã tổ chức một workshop chất lượng cao!** 🙏

Ngày hôm nay tôi không chỉ học được AWS tools mà còn understand được **transformation của AI landscape** - từ traditional ML sang GenAI paradigm.

**The future is AI-powered, and I'm ready to build it!** 🤖✨