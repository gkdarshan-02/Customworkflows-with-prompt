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
