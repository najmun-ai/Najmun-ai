# Najmun Nahar Khan
**Founder & CEO @ RoosCloset Labs | Applied ML Engineer & Cloud Architect**

[![Website](https://img.shields.io/badge/Official_Website-rooscloset.store-2563EB?style=for-the-badge)](https://www.rooscloset.store)
[![Email](https://img.shields.io/badge/Contact_Sales-najmun@rooscloset.store-1E40AF?style=for-the-badge)](mailto:najmun@rooscloset.store)

> Architecting production-grade, multi-tenant machine learning solutions natively on the AWS Cloud. I specialize in dismantling monolithic data pipelines and reconstructing them into highly capitalized, zero-trust cloud infrastructure using **AWS CDK (TypeScript)**. 

---

## 🏛️ Flagship Production Architectures

### 1. [RoosCloset Retail Intelligence](https://github.com/najmun-ai/rooscloset-retail-intelligence)
**B2B Enterprise SaaS | Real-Time Causal Inference & Semantic Cataloging**  
Our enterprise retail suite solves the $100B fashion e-commerce return hemorrhage by replacing correlation dashboards with actionable causal intelligence.

* **ATLAS (Catalog Engine):** A 5-stage multimodal pipeline orchestrated via **AWS Step Functions**. It ingests raw S3 imagery, utilizes **Amazon Rekognition** for garment detection, generates ViT-L/14 style embeddings via **Amazon SageMaker**, and extracts 180+ attributes via **Amazon Bedrock (Claude 3)**.
* **MIRROR (Return Intelligence):** A real-time checkout scoring engine. It pushes high-risk order events through **Amazon Kinesis** data streams to async Lambda workers, which execute DoWhy causal inference graphs to identify true return catalysts, prescribing ROI-mapped interventions.

```text
API Gateway ──▶ Lambda (XGBoost Scoring) ──▶ DynamoDB (State)
                      │
                      ▼
               Kinesis Data Streams ──▶ Lambda (DoWhy Causal Graph) ──▶ EventBridge
```

2. BoroBhai Civic Infrastructure

B2G Civic Technology | Serverless Conversational AI
Digital infrastructure securely guiding Bengali-speaking citizens through complex municipal workflows at fractions of a cent per session.

· Hybrid Retrieval: Orchestrates Claude 3.5 Sonnet and Amazon Titan Embeddings to semantically query a vector knowledge base of 179 expert-reviewed civic procedures.
· Serverless Execution: Completely stateless architecture behind HTTP API Gateway. Generates dynamic municipal documents (CVs, applications, licenses) via headless Lambda manipulation and serves them via time-limited, pre-signed Amazon S3 URLs.

⚙️ Core AWS Engineering Stack

My infrastructure is 100% defined as Infrastructure-as-Code (IaC) via AWS CDK. Multi-tenant isolation is strictly enforced through tenant-prefixed S3 paths, partition-keyed DynamoDB tables, and per-tenant OpenSearch indices.

Architectural Domain AWS Native Services Deployed Implementation Focus
Compute & Orchestration AWS Lambda, Step Functions, API Gateway Stateless execution, 5-stage pipeline error handling, and API throttling.
Machine Learning & AI SageMaker, Bedrock, Rekognition XGBoost endpoints, CLIP embeddings, and Foundation Model multi-modal reasoning.
Data & Persistence S3, DynamoDB, OpenSearch Serverless Lifecycle-managed data lakes, high-throughput feature stores, and k-NN vector indexing.
Streaming & Events Kinesis, EventBridge, SQS Real-time payload sharding, async causal processing, and pipeline backpressure buffering.
Security & Observability Cognito, IAM, CloudWatch, X-Ray Zero-trust authentication, least-privilege role scoping, and distributed tracing.

All repositories pinned below contain fully documented Infrastructure-as-Code (CDK) deployments and technical architecture specifications.
