# 🤖 AI Agent – RAG Automation using n8n

AI-powered automation agent built using n8n with a dual-agent architecture.

## 🧠 What It Does

- Automates research via APIs/web sources
- Structures output into standardized JSON
- Uses LLM for content synthesis
- Publishes structured output automatically

## 🏗 Architecture

Research Agent → Structured JSON → Publishing Agent → Output

## 🛠 Tech Stack

- n8n
- OpenAI API
- Webhooks
- HTTP Requests
- JSON Transformations

## 🚀 How to Run

1. Import `workflow.json` into n8n
2. Add credentials (OpenAI, etc.)
3. Configure environment variables
4. Activate workflow

## 🔐 Environment Variables

Refer to `.env.example`
