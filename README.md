# 🎓 AI-Powered Admission Intelligence System  
### Retrieval-Augmented Conversational Agent with Autonomous Knowledge Ingestion

An enterprise-style AI system built using n8n, OpenAI, and Pinecone to automate student admission queries with continuously updated knowledge from Google Drive.

---

## 🎯 Problem Statement

Admission teams face high volumes of repetitive student queries.
Information is distributed across PDFs and Google Drive folders.
Manual updates lead to inconsistencies and delayed responses.

This system solves that by:

- Providing 24/7 AI-powered conversational support
- Automatically ingesting new documents into a vector database
- Delivering context-aware, retrieval-augmented responses
- Eliminating manual knowledge maintenance

---

## System Architecture

The system follows a layered RAG architecture:

(docs/architecture.png)

### Architecture Layers

1. **User Interaction Layer**
   - Webhook-triggered chat interface
   - Stateful conversational memory

2. **Orchestration Layer**
   - n8n AI Agent
   - Tool-based vector retrieval

3. **Intelligence Layer**
   - OpenAI GPT-4o-mini (Reasoning)
   - OpenAI Embeddings (Vectorization)

4. **Knowledge Layer**
   - Pinecone Vector Store
   - Namespace isolation (`sdabac`)

5. **Autonomous Ingestion Layer**
   - Google Drive folder trigger
   - Recursive text chunking (500 / 20 overlap)
   - Automatic embedding & vector insertion

---

##  Workflow Breakdown

### Conversational Admission Assistant

- Chat Trigger → AI Agent
- Tool-based retrieval from Pinecone
- Memory buffer for contextual continuity
- Grounded responses using retrieved documents

### Knowledge Base Auto-Update Pipeline

- Google Drive Trigger (file created)
- File download
- Recursive character chunking
- Embedding generation
- Pinecone vector insertion

This ensures the assistant stays up-to-date without manual retraining.

---

## Example Interaction

**User:** What is the IMB application deadline?

**Agent:** The IMB application deadline is April 15.  
(Source: IMB_Admissions_Guide_2024.pdf)

---

##  Key Design Decisions

- Used namespace-based vector isolation for scalable multi-tenant architecture
- Implemented recursive chunking (500 tokens, 20 overlap) to balance semantic coherence and retrieval precision
- Separated ingestion and query pipelines for modularity
- Used tool-based retrieval instead of prompt stuffing
- Enabled conversational memory for improved contextual continuity

---

##  Scalability Considerations

- Pinecone supports horizontal scaling
- Namespace isolation enables support for multiple institutions
- Stateless ingestion pipeline allows parallel processing
- Modular workflow design for extension

---

## ⚠ Production Improvements (Future Work)

- Similarity score threshold filtering
- Source attribution in responses
- Error monitoring and alerting
- Query analytics dashboard
- Rate limiting and retry logic
- Observability and logging layer

---

##  Tech Stack

- n8n (Workflow Orchestration)
- OpenAI GPT-4o-mini
- OpenAI Embeddings API
- Pinecone Vector Database
- Google Drive API

---

##  How to Run

1. Import workflows into n8n
2. Configure credentials:
   - OpenAI
   - Pinecone
   - Google Drive
3. Create Pinecone index (`n8n`)
4. Set namespace (`sdabac`)
5. Activate both workflows

---

## Environment Variables

Refer to `.env.example`

---

## Project Type

AI Systems Engineering  
Retrieval-Augmented Generation (RAG)  
Event-Driven Automation Architecture  
Conversational AI Infrastructure  

---
