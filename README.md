# Najmun Nahar Khan
**Founder & CEO @ RoosCloset Labs | Applied ML Engineer & Cloud Architect**

[![Website](https://img.shields.io/badge/Official_Website-rooscloset.store-2563EB?style=for-the-badge)](https://www.rooscloset.store)
[![Email](https://img.shields.io/badge/Contact_Sales-najmun@rooscloset.store-1E40AF?style=for-the-badge)](mailto:najmun@rooscloset.store)

> Architecting production-grade, multi-tenant machine learning solutions natively on the AWS Cloud. I specialize in dismantling monolithic data pipelines and reconstructing them into highly capitalized, zero-trust cloud infrastructure using **AWS CDK (TypeScript)**. 

---

# 🏛️ Flagship Production Architectures

## 1. [RoosCloset Retail Intelligence](https://github.com/najmun-ai/rooscloset-retail-intelligence)
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
## 2. [BoroBhai Civic Infrastructure](https://github.com/najmun-ai/Bangla-AI)
**B2G Civic Technology | Serverless Conversational AI**  
**BoroBhai** is an AI-powered civic assistant that helps Bengali-speaking citizens navigate government documentation and administrative processes through conversational AI. Users ask questions in Bengali or Banglish, and BoroBhai responds with:
- **Generated Documents**: CVs, letters, leave applications, salary certificates, trade licenses, agreements, and more
- **File Manipulation**: PDF compression/merging, image resizing, Excel generation
- **Voice Input**: Transcription in Bengali (bn-BD) via Groq/Web Speech API
- **Smart Retrieval**: Context-aware knowledge base with hybrid search (semantic + keyword)
- **Dual Persona**: Compassionate tone for civic guidance, formal for legal/administrative documents

### Key Features

- **Split-pane Chat UI**: Real-time messaging with document preview
- **Voice-First Input**: Bengali speech recognition (fallback to text)
- **Document Generation**: 12+ professional templates (CV, letter, agreement, salary cert, etc.)
- **File Tools**: Compress PDFs, merge files, resize images, generate Excel sheets
- **Knowledge Base**: 179 expert-reviewed civic procedures + empathy markers
- **Cost Efficient**: ~$22/month all-in (Bedrock + Groq + S3 + EC2)
- **RTL Layout**: Full right-to-left support for Bengali UI

### Tech Stack

**Frontend**: Next.js 14 (App Router), React 18, Tailwind CSS, Vercel AI SDK, MediaRecorder API  
**Backend**: AWS Lambda (Python), AWS Bedrock (Claude 3.5 Sonnet), Amazon Titan Embeddings  
**Data**: S3 (file storage + presigned URLs), DynamoDB (optional session management)  
**Voice**: Groq Whisper API (STT) + Web Speech API (bn-BD)  
**Infrastructure**: AWS CDK (TypeScript), HTTP API Gateway
