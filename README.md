# 🤖 Build Custom Workflows Automatically with GPT-4o, RAG & Web Search (n8n)

![n8n](https://img.shields.io/badge/n8n-workflow-orange)
![AI](https://img.shields.io/badge/AI-GPT--4o-blue)
![RAG](https://img.shields.io/badge/RAG-Pinecone-green)
![Status](https://img.shields.io/badge/status-production--ready-success)

An advanced **AI-powered n8n workflow** that automatically **designs, validates, and outputs fully wired n8n workflow templates** using **GPT-4o**, **Retrieval-Augmented Generation (RAG)**, and **live web search**.

This system acts as an **AI Workflow Architect** — you describe an automation in natural language, and it generates a **ready-to-import n8n workflow JSON**.

---

## 🚀 What This Workflow Does

- ✅ Accepts a natural-language automation request
- ✅ Uses GPT-4o to reason and design workflows
- ✅ Queries n8n documentation via RAG (Pinecone)
- ✅ Uses SerpAPI for real-time web research
- ✅ Produces a validated n8n workflow JSON file
- ✅ Guarantees correct node wiring and structure

---

## 🧠 Core AI Capabilities

- **GPT-4o (via OpenRouter)** for reasoning and planning  
- **RAG (Pinecone Vector Store)** for grounded answers  
- **SerpAPI** for live web search  
- **Structured JSON output validation**  
- **Automatic workflow export**

---

## 🏗️ System Architecture

```text
User Chat Request
      ↓
Chat Trigger (n8n)
      ↓
Preference Injection (Models & Tools)
      ↓
AI Agent (LangChain)
 ├─ GPT-4o (OpenRouter)
 ├─ Pinecone Vector Store (RAG)
 └─ SerpAPI (Web Search)
      ↓
OpenAI Validator (JSON Check)
      ↓
Code Node (Extract JSON)
      ↓
Convert to File (Workflow Template)

```
---

## 🧩 Sub-Processes :

🔹 Sub-Process #1: Web Crawler (Documentation Ingestion)

Purpose:
Crawl and collect n8n documentation for RAG training.

Manual Trigger
   ↓
Set URL (docs.n8n.io)
   ↓
HTTP Request (Firecrawl Extract)
   ↓
Wait (30s)
   ↓
Get Results
   ↓
IF (Completed?)
   ├─ YES → Output Docs
   └─ NO  → Wait (10s) → Retry

---

🔹 Sub-Process #2: RAG Trainer

Purpose:
Convert documentation into embeddings and store them in Pinecone.

Documentation Input
   ↓
Default Data Loader
   ↓
Recursive Character Text Splitter
   ↓
OpenAI Embeddings
   ↓
Train Pinecone Vector Store

---


🔹 Sub-Process #3: AI Workflow Builder (Main Engine)

Purpose:
Generate complete n8n workflows automatically.

Chat Trigger
   ↓
Set Preferences
   ├─ Chat Model
   ├─ Vector DB
   ├─ Embeddings
   └─ Web Search Tool
   ↓
AI Agent (LangChain)
 ├─ GPT-4o (reasoning)
 ├─ Pinecone (context retrieval)
 └─ SerpAPI (web research)
   ↓
OpenAI Validator (JSON validation)
   ↓
Code Node (Extract JSON)
   ↓
Convert to JSON File

---

⚙️ Key Nodes Used

* @n8n/n8n-nodes-langchain.chatTrigger

* @n8n/n8n-nodes-langchain.agent

* @n8n/n8n-nodes-langchain.lmChatOpenRouter

* @n8n/n8n-nodes-langchain.embeddingsOpenAi

* Pinecone Vector Store

* SerpAPI Tool

* Code (JSON extraction)

* Convert to File

---

## 🔐 Required Credentials

| Service    | Used For                     |
| ---------- | ---------------------------- |
| OpenRouter | GPT-4o chat model            |
| OpenAI     | Embeddings & JSON validation |
| Pinecone   | Vector database (RAG)        |
| SerpAPI    | Web search                   |
| Firecrawl  | Documentation crawling       |

---

## 🧪 How to Run the System

1️⃣ Import Workflow

*n8n → Workflows → Import
*Upload the .json file

2️⃣ Configure Credentials

* Attach credentials to:
   -                   OpenRouter Chat Model
                       OpenAI Embeddings
                       Pinecone Vector Store
                       SerpAPI
                       Firecrawl (HTTP Header Auth)

3️⃣ Train RAG (One-Time)

*Run Web Crawler
*Execute RAG Trainer
*Verify Pinecone index

4️⃣ Generate Workflows

*Trigger Chat Trigger
*Example prompt: "Build an n8n workflow that classifies incoming Gmail emails using AI"
*Download generated workflow JSON

---






   
