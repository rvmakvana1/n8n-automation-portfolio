# 🤖 n8n AI Automation Portfolio

> **AI Agent & Automation Specialist** — Building intelligent, multi-platform automations that solve real business problems. From RAG-powered voice agents to multi-tool AI systems handling 300k+ users, every project here is built end-to-end and production-tested.

---

## 👨‍💻 About Me

I specialize in designing and deploying **autonomous AI agents** and **end-to-end automation workflows** using **n8n** as the core orchestration engine. My focus is on building systems that don't just demo well — they handle real-world complexity: stateful conversations, structured business data, multi-language support (Hindi/English/Hinglish), and integrations across messaging platforms, voice APIs, and vector databases.

**What I build:**
- 🧠 RAG-powered AI agents with custom knowledge bases (Pinecone, Supabase)
- 💬 Conversational bots across WhatsApp, Instagram, Telegram & Voice
- ⚙️ Multi-tool agents that orchestrate Google Sheets, Calendar, Gmail, Airtable
- 🔁 Stateful, memory-aware systems with Postgres / Vector DB persistence

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| **Orchestration** | n8n (Self-hosted & Cloud) |
| **AI / LLMs** | OpenAI (GPT-4o, GPT-4o-mini), DeepSeek, Whisper |
| **Vector Databases** | Pinecone, Supabase Vector Store |
| **Databases** | Google Sheets, Airtable, Postgres |
| **Messaging APIs** | Meta WhatsApp API, Telegram Bot API, Manychat (Instagram) |
| **Voice** | ElevenLabs (TTS / STT) |
| **Frontend** | Lovable.dev |
| **Languages** | JavaScript (n8n Code Node), Python |

---

## 📂 Featured Projects

| # | Project | Stack Highlights |
|---|---|---|
| 1 | [FinFlow AI — Smart Finance Agent](#-project-1-finflow-ai--smart-finance-agent) | Hinglish · Tool Calling · Pinecone · Dual Workflow |
| 2 | [Instagram DM Lead Qualifier](#-project-2-instagram-dm-lead-qualifier-manychat--n8n) | Manychat · DeepSeek · Stateful Memory |
| 3 | [AI Second Brain & Memory Assistant](#-project-3-ai-second-brain--memory-assistant) | Whisper · Pinecone · Calendar · RAG |
| 4 | [AI Calling Agent (Voice + RAG)](#-project-4-ai-calling-agent-voice--rag) | ElevenLabs · Pinecone · Real-time Voice |
| 5 | [Telegram Subscriber Migration (300k+ Users)](#-project-5-telegram-subscriber-migration-system-300k-users) | Telegram Bot · Data Capture at Scale |
| 6 | [WhatsApp Restaurant Bot (Meta API)](#-project-6-whatsapp-restaurant-bot-meta-api) | Meta API · Multi-Tool Agent · DeepSeek |
| 7 | [AI Business Dashboard (Lovable + n8n)](#-project-7-ai-business-dashboard-lovable--n8n) | Lovable · Webhook · Multi-Tool Agent |
| 8 | [Scalable AI Expert Bot (Supabase + Postgres)](#-project-8-scalable-ai-expert-bot-supabase--postgres-memory) | Supabase Vector · Postgres Memory |
| 9 | [AI Real Estate Assistant (Structured Data RAG)](#-project-9-ai-real-estate-assistant-structured-data-rag) | Excel Ingestion · Custom JS · Supabase |
| 10 | [RAG Knowledge Base Agent](#-project-10-rag-knowledge-base-agent) | Pinecone · OpenAI Embeddings · Google Drive |
| 11 | [NSE Live Market Data Pipeline](#-project-11-nse-live-market-data-pipeline) | Custom API · JS Algorithm · Scheduled |

---

## 🥇 Project 1: FinFlow AI — Smart Finance Agent

> **An autonomous financial assistant that understands Hinglish, remembers context across sessions, and never makes a math error.**

![FinFlow Architecture](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow_Core_Orchestrator.png?raw=true)

### 📝 Overview
Standard LLMs are great at conversation but **terrible at math** — they hallucinate numbers in long expense calculations. FinFlow AI solves this with an **agentic architecture** that uses tool-calling for 100% calculation accuracy. It acts as a personal CFO inside Telegram: tracking expenses in Google Sheets, recalling debts via Pinecone, and proactively sending payment reminders.

### 💡 Problem → Solution

| Problem with Standard Chatbots ❌ | How FinFlow AI Solves It ✅ |
|---|---|
| Math hallucinations in calculations | Tool calling with calculator node — 100% accuracy |
| Can't differentiate "Paid to Ravi" vs "Received from Ravi" | Semantic understanding of credit/debit direction in Hinglish |
| No memory of past transactions | Pinecone vector DB for long-term recall |

### ⚙️ Architecture — Two Coordinated Workflows

**1. FinFlow_Core_Orchestrator (The Brain)**
- Receives text/audio from Telegram
- AI Router classifies intent (expense / query / greeting)
- Autonomously selects tools: Calculator, Google Sheets API, Pinecone Search
- Returns natural-language summary

**2. FinFlow_Reminder_Module (The Timekeeper)**
- Scheduled checks on upcoming payments
- Filters debt deadlines from Sheets/Calendar
- Sends proactive Telegram alerts before due dates

![Reminder Module](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow_Reminder_Module.png?raw=true)

### 📸 Live Demo

**Mixed Income & Expense in Hinglish:**
*"Ravi se 5000 udhar liye, Ravi ko 2000 wapas diye, Petrol 100"* — categorized correctly with accurate net balance.

![Logic Demo](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow%20AI%20%20Smart%20Finance%20Agent%2001.png?raw=true)

**Contextual Memory & Net Balance Logic:**

![Memory Demo](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow%20AI%20Smart%20Finance%20Agent%2004.png?raw=true)

### 🛠️ Tech Stack
n8n · OpenAI GPT-4o-mini · Pinecone · Google Sheets · Telegram Bot API · Calculator Tool

### 📥 Workflow Code
[📄 Download FinFlow Core Orchestrator (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow_Core_Orchestrator.json)

---

## 🥈 Project 2: Instagram DM Lead Qualifier (Manychat + n8n)

> **A multi-platform conversational AI that automates the entire lead qualification funnel directly inside Instagram DMs.**

### 📝 Overview
A sophisticated agentic system built for a business coach to qualify Instagram leads **24/7 without human intervention**. The architecture splits responsibilities cleanly: **Manychat** handles the Instagram DM frontend, while **n8n hosts the AI brain** — a DeepSeek agent with Simple Memory keyed on Manychat's `contactId` for stateful, human-like conversations.

### ✨ Key Features
- **Real-time DM automation** triggered by keywords (e.g., "Checklist")
- **Multi-step qualification flow** — agent asks questions one-by-one, waits for replies
- **Conditional upsell** — discovery call offered only to qualified leads
- **Automated lead capture** — qualified leads pushed to Google Sheets
- **Stateful memory** maintained across Manychat ↔ n8n via webhook payload

### 🖼️ Workflow Visuals

**Manychat Flow (Frontend)**

![Manychat Instagram Flow](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-instagram-manychat-flow-screenshot.png?raw=true)

**n8n Workflow (AI Brain)**

![Instagram AI Agent Brain](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-instagram-dm-lead-qualifier-screenshot.png?raw=true)

### 🛠️ Tech Stack
n8n · Manychat · Instagram · DeepSeek Chat Model · Google Sheets · Simple Memory

### 🧠 Key Learning
The core challenge was achieving **stateful conversations across two systems**. Solved by using Manychat's `contactId` as n8n's Memory Session ID — a scalable pattern for any social media agent.

### 📥 Workflow Code
[📄 Download Workflow (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-instagram-dm-lead-qualifier.json)

---

## 🧠 Project 3: AI Second Brain & Memory Assistant

> **A personal "Second Brain" that captures voice notes, stores memories permanently, and auto-schedules reminders — all from Telegram.**

### 📝 Overview
Two interconnected workflows that work together to handle memory storage and time-based actions. An AI router decides intent and delegates: notes get embedded into Pinecone, reminders get parsed and booked into Google Calendar, and questions get answered using only the user's own stored data.

### ✨ Key Features
- 🗣️ **Voice-to-Text** via OpenAI Whisper (Hindi/Hinglish supported)
- 🧠 **Long-term RAG memory** in Pinecone
- 📅 **Smart scheduling** — natural language → Google Calendar events
- 📂 **Automatic backup** to Google Sheets
- 💬 **Telegram interface** for seamless capture

### 🖼️ Workflow Visuals

**Workflow 1: Memory & RAG Logic**

![Main Workflow](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Second%20Brain%20App.png?raw=true)

**Workflow 2: Calendar & Reminders Automation**

![Calendar Workflow](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Second%20Brain%20Workflow%202.png?raw=true)

### 🛠️ Tech Stack
n8n · OpenAI (GPT-4o + Whisper) · Pinecone · Google Calendar · Google Sheets · Telegram

### 📥 Workflow Code
[📄 Download Core Logic (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Second%20Brain%20App%20-%20Core%20Logic.json)

---

## 📞 Project 4: AI Calling Agent (Voice + RAG)

> **A real-time voice AI that answers calls and responds based on a custom knowledge base — built with n8n + ElevenLabs.**

### 📝 Overview
A sophisticated voice agent capable of holding real conversations over phone calls. **ElevenLabs** handles speech-to-text and text-to-speech; **n8n** runs the RAG pipeline using **Pinecone** for context retrieval and **OpenAI** for response generation. The entire loop — voice input → transcription → vector search → AI generation → voice output — runs in real-time via webhooks.

### ✨ Key Features
- **Real-time voice conversation** with sub-second latency
- **Custom knowledge base** — answers based on user-provided documents only
- **Direct ElevenLabs ↔ n8n integration** via webhooks
- **Stateful call memory** using ElevenLabs' `call_id` as the session key
- **End-to-end voice loop** orchestrated entirely in n8n

### 🖼️ Workflow Visual

![RAG Calling Agent](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Rag%20Calling%20Voice%20%20Agent.png?raw=true)

### 🛠️ Tech Stack
n8n · ElevenLabs (Voice AI) · Pinecone · OpenAI (Embeddings + Chat) · Webhooks

### 🧠 Key Learning
Voice conversations require **immediate responses** and robust state management. The breakthrough was using ElevenLabs' `call_id` as n8n's Memory Session Key — making each phone call a self-contained, contextual session.

### 📥 Workflow Code
[📄 Download Calling Agent (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/RAG%20Calling%20Agent.json)

---

## 🚀 Project 5: Telegram Subscriber Migration System (300k+ Users)

> **A "Bridge Bot" that migrated 300,000+ subscribers to a new premium channel — capturing every user's data along the way.**

### 📝 Overview
A real client project solving a critical **data retention challenge**. Direct invite links don't reveal who joins — meaning a 300k subscriber base would migrate as anonymous users. This bridge bot solved that: users are sent to the bot first (instead of a direct link), and the moment they tap "Start," their User ID, Name, and Date are automatically logged to Google Sheets before they receive the channel invite.

### ✨ Impact
- ✅ **300,000+ subscribers** migrated successfully
- ✅ **100% data capture** — zero anonymous joins
- ✅ **Zero friction UX** — single-click flow for the user
- ✅ **CRM-ready database** for future communications

### 🖼️ Bot Interface

![Bot Interface](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Stock%20Market%20Telegram%20Bot.png?raw=true)

### 🛠️ Tech Stack
n8n · Telegram Bot API · Google Sheets (300k+ rows)

### 📥 Workflow Code
[📄 Download Workflow (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Stock%20Market%20Telegram%20Bot%20.json)

---

## 🍽️ Project 6: WhatsApp Restaurant Bot (Meta API)

> **A fully autonomous AI agent that runs an entire restaurant ordering system on official WhatsApp — using Google Sheets as a real-time database.**

### 📝 Overview
A multi-tool agent built for "MDA Restaurant" that handles the complete ordering experience over **official Meta WhatsApp Business API**. The agent intelligently switches between three Google Sheet "tools" — checking inventory, answering FAQs, and posting confirmed orders — all driven by a DeepSeek LLM and a precise system prompt.

### ✨ Key Features
- **Direct Meta WhatsApp Business API integration** (production-grade setup)
- **Google Sheets as a live database** — three sheets acting as three distinct tools
- **Multi-tool agent reasoning** — picks the right tool based on user intent
- **End-to-end order flow** — greeting → inventory check → order capture → confirmation

### 🖼️ Workflow Visual

![WhatsApp Order Bot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-whatsapp-restaurant-bot-screenshot.png?raw=true)

### 🛠️ Tech Stack
n8n · Meta WhatsApp Business API · DeepSeek · Google Sheets · Simple Memory

### 🧠 Key Learning
The hardest part wasn't n8n — it was **navigating Meta for Developers** to set up the WhatsApp Business App and generate permanent credentials. This project demonstrates I can handle complex enterprise API integrations end-to-end.

### 📥 Workflow Code
[📄 Download Workflow (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-whatsapp-restaurant-bot.json)

---

## 📊 Project 7: AI Business Dashboard (Lovable + n8n)

> **A custom internal tool that lets a manager run their entire business through a single chat interface.**

### 📝 Overview
This project combines a **Lovable** dashboard (frontend), **Google Sheets** (database), and an **n8n AI Agent** (backend) into a unified operating system. Managers type natural-language commands like *"Update Fernanda's budget"* or *"Send Martin an email"* — and the agent uses its tools to execute, then confirms back in chat. Real-time sync means dashboard updates appear instantly.

### ✨ Key Features
- **Natural language → real action** — no need to know n8n or Sheets
- **Multi-tool agent** — reads, writes, sends emails from one interface
- **Real-time dashboard sync** between agent actions and frontend
- **Webhook-powered chat loop** between Lovable and n8n

### 🖼️ Workflow Visuals

**Frontend Dashboard (Lovable)**

![Dashboard UI](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-business_lovable-dashboard-ui.png?raw=true)

**n8n Backend Agent**

![Agent Backend](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-business-dashboard-agent-screenshot.png?raw=true)

### 🛠️ Tech Stack
n8n · Lovable.dev · OpenAI · Google Sheets · Gmail · Webhooks

### 📥 Workflow Code
[📄 Download Workflow (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-business-dashboard-agent.json)

---

## 🏛️ Project 8: Scalable AI Expert Bot (Supabase + Postgres Memory)

> **An enterprise-grade AI agent with persistent memory — built for scale, not demos.**

### 📝 Overview
This isn't a hobby chatbot — it's an "AI Expert" architected for production. It uses **Supabase** as both data store and vector database for RAG, and **Postgres Chat Memory** for persistent, cross-session conversation history. The demo learns "The Rules of Golf" PDF, but the architecture works for any internal company knowledge base.

### ✨ Key Features
- **Unified workflow** for both data ingestion and live Q&A
- **Supabase vector pipeline** — open-source, scalable RAG backbone
- **Persistent Postgres memory** — agent remembers users across sessions, not just one chat
- **Production-ready architecture** for enterprise knowledge bases

### 🖼️ Workflow Visual

![Supabase RAG Workflow](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/AI%20Chatbot%20Workflow%20(n8n,%20OpenAI,%20Supabase).png?raw=true)

### 🛠️ Tech Stack
n8n · Supabase (Vector + Database) · OpenAI (Embeddings + Chat) · Postgres Chat Memory

### 📥 Workflow Code
[📄 Download Workflow (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/AI%20Chatbot%20Workflow%20(n8n%2C%20OpenAI%2C%20Supabase).json)

---

## 🏠 Project 9: AI Real Estate Assistant (Structured Data RAG)

> **A 24/7 virtual property expert that answers fact-based questions about listings — by learning directly from Excel files.**

### 📝 Overview
Most RAG demos work on PDFs. Real businesses store data in **structured spreadsheets**. This project tackles that gap: it auto-ingests Excel files from Google Drive, uses a **custom JavaScript node** to clean and format each row, then embeds the structured data into Supabase for high-accuracy retrieval.

### ✨ Key Features
- **Structured data RAG** — handles Excel/XLS, not just text
- **Custom JavaScript transformation** for clean, embeddable property records
- **Auto-updating knowledge base** — drop a file in Drive, agent learns it
- **Fact-based answers** about price, bedrooms, location — pulled from real listings

### 🖼️ Workflow Visual

![Real Estate Workflow](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-real-estate-rag-agent-screenshot.png?raw=true)

### 🛠️ Tech Stack
n8n · Google Drive · Extract from File · JavaScript Code Node · Supabase Vector · OpenAI

### 🧠 Key Learning
RAG isn't just for PDFs. The custom JS step proves the pipeline can adapt to **any business data format** — which is what real-world deployment requires.

### 📥 Workflow Code
[📄 Download Workflow (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-real-estate-rag-agent-json.json)

---

## 📚 Project 10: RAG Knowledge Base Agent

> **A self-updating Q&A agent that learns from any documents added to Google Drive.**

### 📝 Overview
A foundational RAG system split into two clean workflows. The first monitors Google Drive, chunks new documents, embeds them via OpenAI, and stores vectors in Pinecone. The second is the user-facing agent that searches Pinecone for context and generates accurate, source-grounded answers — even across multiple languages.

### ✨ Key Features
- **Two-workflow architecture** — separation of ingestion and inference
- **Auto-learning** from any new Google Drive uploads
- **Multilingual** semantic search via vector embeddings
- **Source-grounded answers** — no hallucinated facts

### 🖼️ Workflow Visuals

**Part 1: Knowledge Base Builder**
![KB Builder](https://raw.githubusercontent.com/rvmakvana1/n8n-automation-portfolio/main/rag-knowledge-base-builder-screenshot.png)

**Part 2: Chat Agent**
![Chat Agent](https://raw.githubusercontent.com/rvmakvana1/n8n-automation-portfolio/main/rag-chat-agent-screenshot.png)

### 🛠️ Tech Stack
n8n · Google Drive · Pinecone · OpenAI (Embeddings + Chat)

### 📥 Workflow Code
- [📄 Knowledge Base Builder (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/rag-knowledge-base-builder%20Step-1.json)
- [📄 Chat Agent (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/rag-chat-agent%20Step-2.json)

---

## 📈 Project 11: NSE Live Market Data Pipeline

> **A real-time financial data pipeline that fetches NIFTY option chain data and intelligently filters the most actionable strikes — every 3 minutes.**

### 📝 Overview
A scheduled automation that pulls live option chain data directly from the **National Stock Exchange (NSE) API**, then runs a custom JavaScript algorithm to identify the **At-The-Money (ATM)** strike price and extract the 7 most relevant rows (ATM ± 3). The filtered, market-relevant data flows automatically into Google Sheets — giving traders a focused, real-time view of where the action actually is.

### ✨ Key Features
- **Secure dynamic API handling** — manages NSE's session cookies and headers
- **Custom ATM detection algorithm** in JavaScript
- **Intelligent data filtering** — surfaces only the 7 most actionable strikes
- **Scheduled execution** every 3 minutes — fully autonomous

### 🖼️ Workflow Visual

![NSE Data Pipeline](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/NSE%20DATA%20.png)

### 🛠️ Tech Stack
n8n · HTTP Request · JavaScript Code Node · Google Sheets · Schedule Trigger

### 🧠 Key Learning
NSE's API isn't a public endpoint — it requires careful session handling and header management. Combining API engineering with custom filtering logic shows how automation can deliver **decision-ready data**, not just raw dumps.

### 📥 Workflow Code
[📄 Download Workflow (.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/NSE%20DATA%20AUTOMATION.json)

---

## 📬 Let's Connect

I'm actively building AI automation systems and open to **internship**, **freelance**, and **full-time** opportunities in the AI Agent / Automation space.

If you'd like to collaborate, discuss a project, or just chat about agentic AI — feel free to reach out.

---

⭐ **If you find these projects useful, consider starring this repo!**
