---
title: "Event 3"
date: 2024-10-15T00:00:00Z
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---



# Report: "AWS Cloud Mastery Series #1 - AI/ML/GenAI on AWS"

---

## Event Information

**Event Name:** AWS Cloud Mastery Series #1 - AI/ML/GenAI on AWS

**Date:** Saturday, November 15, 2025

**Time:** 08:30 - 12:00

**Venue:** AWS Vietnam Office, Bitexco Financial Tower, District 1, Ho Chi Minh City

**Organized by:** AWS Community, Kha Van

**Attendees:** 348 students & professionals

**My Role:** Active Participant & Learner

---

## Event Purpose

**AWS Cloud Mastery Series #1** was organized to:

- 🎯 Introduce the complete AI/ML landscape in Vietnam
- 🤖 Focus on **Generative AI** - the hottest technology today
- 💼 Hands-on practice with AWS AI/ML services
- 🚀 Build real-world GenAI chatbots using Amazon Bedrock
- 📚 Deep dive into RAG, Prompt Engineering, Agents
- 🤝 Build a learning community around AI/ML on AWS

---

## Event Schedule

### 08:30 – 09:00 | Welcome & Introduction

**Content:**
- Participant registration and networking
- Workshop overview and learning objectives
- Ice-breaker activity
- Overview of AI/ML landscape in Vietnam

**Significance:**
- Create warm & collaborative atmosphere
- Help participants connect with each other
- Set clear expectations for the workshop
- Context about AI/ML adoption trends in Vietnam

---

### 09:00 – 10:30 | AWS AI/ML Services Overview

#### Amazon SageMaker - End-to-End ML Platform

**Key Concepts:**
- **What is SageMaker:** Fully managed ML platform by AWS
- **Use Cases:** Regression, classification, clustering, time series forecasting
- **Architecture:** Data preparation → Training → Deployment → Monitoring

#### Data Preparation & Labeling

**Important Features:**
- **Data Wrangler:** Visual data preparation tool
- **Ground Truth:** Labeling service for training data
- **Feature Store:** Centralized ML features repository
- **Data Quality Monitoring:** Detect data drift & anomalies

#### Model Training, Tuning & Deployment

**Training Capabilities:**
- **Built-in algorithms:** Xgboost, linear learner, image classification, etc.
- **Hyperparameter Optimization:** Automatic tuning
- **Distributed Training:** Multi-GPU/Multi-node support
- **Cost Optimization:** Spot instances support

**Deployment Options:**
- **Real-time endpoints:** Low-latency predictions
- **Batch transform:** Large-scale inference
- **Edge deployment:** SageMaker Edge Manager
- **Multi-model endpoints:** Host multiple models efficiently

#### Integrated MLOps Capabilities

**Pipeline & Automation:**
- **SageMaker Pipelines:** Orchestrate end-to-end ML workflows
- **Model Registry:** Version control & governance
- **Model Monitor:** Track production performance
- **Automated Retraining:** Trigger on performance metrics

#### Live Demo: SageMaker Studio Walkthrough

**Demo Features:**
- Studio interface & project setup
- Data exploration & visualization
- Model training & hyperparameter tuning
- Deployment to endpoints
- Monitoring & performance tracking

**Key Takeaway:** From data to production in minutes, not weeks

---

### 10:30 – 10:45 | Coffee Break

- Refreshment break & networking
- Informal Q&A with instructors

---

### 10:45 – 12:00 | Generative AI with Amazon Bedrock

#### Foundation Models Comparison

**Available Models:**
- **Claude (Anthropic):** Advanced reasoning, safety-focused
- **Llama (Meta):** Open source, flexible, efficient
- **Titan (AWS):** Multi-lingual, AWS-optimized

**Comparison:**
- **Capabilities:** Reasoning, code generation, multilingual, safety
- **Performance:** Speed vs accuracy tradeoff
- **Cost:** Token-based pricing
- **Selection Guide:** Choose based on use case needs

**Key Insight:** Biggest model ≠ best model; choose what fits your use case

#### Prompt Engineering Techniques

**Best Practices:**
- **Clear Instructions:** Specific, detailed prompts
- **Examples:** Provide examples for in-context learning
- **Role-playing:** Give LLM a role/persona
- **Chain-of-Thought:** Ask model to think step-by-step
- **Few-shot Learning:** Show 2-3 examples before asking
- **Temperature & Top-p:** Control output randomness

**Real Examples:**
- ❌ Bad: "Summarize this"
- ✅ Good: "Summarize this document in 3 bullet points, focusing on financial impact"

#### Retrieval-Augmented Generation (RAG)

**Problem Statement:**
- LLMs have knowledge cutoff (outdated information)
- Hallucinations - LLMs generate inaccurate information
- No access to private/proprietary data

**RAG Solution:**
- **Retrieve:** Find relevant documents from knowledge base
- **Augment:** Combine retrieved docs with user query
- **Generate:** LLM generates answer based on retrieved context

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
- Factual accuracy (grounded in documents)
- Up-to-date information (controlled updates)
- Private data access (proprietary documents)
- Transparency (show source documents)

#### Bedrock Agents

**Multi-Step Workflows:**
- Agents can break down tasks into steps
- **Planning:** Decide action sequence
- **Reasoning:** Evaluate results & adjust
- **Tool Use:** Call APIs, databases, etc.

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
- **Hate speech:** Detect & filter
- **Violence:** Flag violent content
- **Adult content:** Content moderation
- **Custom filters:** Domain-specific guardrails

**Safety Features:**
- Input filtering: Screen user prompts
- Output filtering: Check LLM responses
- Monitoring & logging: Track safety metrics
- Customizable thresholds: Define sensitivity

**Why Important:** Prevent misuse, ensure compliance, maintain trust

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

**Code Snippet:**
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

**Key Takeaway:** Build production-ready GenAI apps in minutes

---

### 12:00 | Lunch Break (Self-arranged)

---

## Key Knowledge & Insights

### 1. **GenAI is a Paradigm Shift, Not Just Incremental Improvement** 🚀

**Before GenAI:**
- ML: Supervised learning, classification, prediction
- Limited to structured data
- Extensive feature engineering needed

**With GenAI:**
- Foundation models learn from unstructured text/images
- Zero-shot, few-shot learning (in-context learning)
- Broad applicability across domains

**Implication:** AI skills landscape transforming fundamentally

### 2. **Amazon SageMaker Democratizes ML** 💼

**Before SageMaker:**
- ML projects slow, complex, require experts
- High barrier to entry

**With SageMaker:**
- Low-code/no-code approach
- Fully managed infrastructure
- End-to-end pipeline automation
- MLOps best practices built-in

**Insight:** AI/ML no longer exclusive to data scientists

### 3. **RAG Solves Real-World GenAI Problems** 🎯

**Hallucination Problem:**
- LLMs generate convincing but wrong answers
- Knowledge cutoff (outdated information)

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

**Why Important:**
- Users may provide harmful prompts
- LLMs can amplify biases
- Regulatory requirements (privacy, safety standards)

### 6. **Hands-On Experience Accelerates Learning** 💻

**Live Demos:**
- See real SageMaker interface
- Understand workflow step-by-step
- See actual code examples
- Know common pitfalls

**Biggest Insight:** "It's much easier than I thought to build GenAI apps"

---

## Value Delivered

### Skills & Knowledge

- ✅ **Comprehensive Overview:** Full stack of AI/ML on AWS
- ✅ **SageMaker Proficiency:** Know how to use SageMaker for ML projects
- ✅ **GenAI Concepts:** Deep dive into RAG, agents, prompt engineering
- ✅ **Practical Implementation:** Hands-on experience building solutions
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

## Technologies & Tools Learned

| Technology | Application | Notes |
|-----------|------------|-------|
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

## Conclusion

**AWS Cloud Mastery Series #1** was a high-quality workshop:

✨ **Strengths:**
- Timely & relevant topic (GenAI is hottest)
- Balance between theory & hands-on practice
- Live demos realistic & executable
- Clear instructor expertise
- 348 engaged learners community
- AWS perspective & best practices

💫 **Key Takeaways:**
- **GenAI Democratized:** Anyone can build GenAI apps now
- **SageMaker Powerful:** Full ML lifecycle support
- **RAG Solves Problems:** Ground GenAI with real data
- **Responsible AI Crucial:** Safety & ethics matter
- **Agents Next:** Beyond simple text generation

🎯 **Practical Takeaways:**
- Can start building GenAI chatbots immediately
- SageMaker is go-to platform for ML projects
- RAG pattern applicable to many use cases
- Prompt engineering is practical skill (not magic)

🚀 **Next Steps for Deeper Learning:**
- Try hands-on labs on AWS
- Build a personal GenAI project
- Explore advanced SageMaker features
- Attend AWS Cloud Mastery Series #2, #3, etc.

---

**Thank you AWS Community for this high-quality workshop!** 🙏

Today I didn't just learn AWS tools but understood the **transformation of AI landscape** - from traditional ML to GenAI paradigm.

**The future is AI-powered, and I'm ready to build it!** 🤖✨