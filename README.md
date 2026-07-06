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
### 2. [BoroBhai Civic Infrastructure](https://github.com/najmun-ai/Bangla-AI)
**B2G Civic Technology | Serverless Conversational AI**  
Digital infrastructure securely guiding Bengali-speaking citizens through complex municipal workflows at fractions of a cent per session.

* **Hybrid Retrieval:** Orchestrates Claude 3.5 Sonnet and Amazon Titan Embeddings to semantically query a vector knowledge base of 179 expert-reviewed civic procedures.
* **Serverless Execution:** Completely stateless architecture behind HTTP API Gateway. Generates dynamic municipal documents (CVs, applications, licenses) via headless Lambda manipulation and serves them via time-limited, pre-signed Amazon S3 URLs.


┌─────────────────────────────────────────────────────────────────┐
│                   User Interface Layer                          │
│  Next.js 14 App Router | React 18 | Tailwind CSS | Web Speech   │
│  • Chat pane (messages + streaming)                             │
│  • Document pane (preview + download)                           │
│  • Voice input (bn-BD transcription)                            │
│  • File upload (S3 presigned URLs)                              │
└──────────────────────┬──────────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────────┐
│                    API Integration Layer                        │
│  Next.js API Routes | Node.js Runtime | Vercel AI SDK           │
│  • /api/chat → AWS Bedrock invocation + streaming               │
│  • /api/upload → S3 presigned URL generation                    │
│  • /api/stt → Groq Whisper transcription (fallback)            │
│  • /api/presign-upload → Client-side file PUT                  │
└──────────────────────┬──────────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────────┐
│                  Bedrock Orchestration Layer                    │
│  AWS Bedrock | Claude 3.5 Sonnet | Tool-Use Enabled            │
│  • Receives user message + system prompt + tools                │
│  • Evaluates: chat response OR invoke tool(s)                   │
│  • Routes tool calls to Lambda functions                        │
│  • Streams final response to frontend                           │
│                                                                 │
│  Tools Available:                                               │
│  ├─ compress_pdf (PyMuPDF)                                      │
│  ├─ merge_pdfs (PyMuPDF)                                        │
│  ├─ resize_image (Pillow)                                       │
│  ├─ generate_excel (openpyxl)                                   │
│  ├─ generate_letter_docx (python-docx + Jinja2)               │
│  └─ generate_cv_docx (python-docx + templates)                 │
└──────────────────────┬──────────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────────┐
│                    Lambda Functions Layer                       │
│  AWS Lambda (Python 3.11) | Docker Container Support            │
│  • proofsheet-orchestrator: Bedrock invocation + agentic loop   │
│  • proofsheet-file-tools: PDF/image/Excel/DOCX generation      │
│  • proofsheet-presign: S3 presigned URL generation              │
└──────────────────────┬──────────────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────────────┐
│                   Storage & Retrieval Layer                     │
│  AWS S3 | DynamoDB | In-Memory KB | Amazon Titan Embeddings     │
│  • S3: User files (compressed/, images/, exports/, letters/)    │
│  • DynamoDB: Chat history (optional, for session recovery)      │
│  • In-Memory KB: 179 pre-embedded chunks (1024-dim Titan)       │
│  • Retrieval: Hybrid search (cosine similarity + BM25)          │
│  • Lifecycle: Auto-delete files after 7 days                    │
└─────────────────────────────────────────────────────────────────┘
