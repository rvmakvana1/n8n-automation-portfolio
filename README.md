#  n8n AI Automation Portfolio

> **AI Agent & Automation Specialist** — Building intelligent, multi-platform automations that solve real business problems. From RAG-powered voice agents to multi-tool AI systems handling 300k+ users, every project here is built end-to-end and production-tested.

---

##  About Me

I specialize in designing and deploying **autonomous AI agents** and **end-to-end automation workflows** using **n8n** as the core orchestration engine. My focus is on building systems that don't just demo well — they handle real-world complexity: stateful conversations, structured business data, multi-language support (Hindi/English/Hinglish), and integrations across messaging platforms, voice APIs, and vector databases.

**What I build:**
- 🧠 RAG-powered AI agents with custom knowledge bases (Pinecone, Supabase)
- 💬 Conversational bots across WhatsApp, Instagram, Telegram & Voice
- ⚙️ Multi-tool agents that orchestrate Google Sheets, Calendar, Gmail, Airtable
- 🔁 Stateful, memory-aware systems with Postgres / Vector DB persistence

---

##  Tech Stack

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
| 2 | [Instagram DM Lead Qualifier](#-project-2-ai-powered-instagram-dm-lead-qualifier-manychat--n8n) | Manychat · DeepSeek · Stateful Memory |
| 3 | [AI Second Brain & Memory Assistant](#-project-3-ai-second-brain--memory-assistant-with-reminders) | Whisper · Pinecone · Calendar · RAG |
| 4 | [AI Calling Agent (Voice + RAG)](#-project-4-ai-calling-agent-with-custom-knowledge-base-rag--elevenlabs) | ElevenLabs · Pinecone · Real-time Voice |
| 5 | [Telegram Subscriber Migration (300k+ Users)](#-project-5-telegram-subscriber-migration--data-capture-system) | Telegram Bot · Data Capture at Scale |
| 6 | [WhatsApp Restaurant Bot (Meta API)](#-project-6-ai-whatsapp-restaurant-bot-via-meta-api) | Meta API · Multi-Tool Agent · DeepSeek |
| 7 | [AI Business Dashboard (Lovable + n8n)](#-project-7-ai-powered-business-dashboard-n8n--google-sheets--lovable) | Lovable · Webhook · Multi-Tool Agent |
| 8 | [Scalable AI Expert Bot (Supabase + Postgres)](#-project-8-scalable-ai-expert-bot-rag-on-supabase--postgres-memory) | Supabase Vector · Postgres Memory |
| 9 | [AI Real Estate Assistant (Structured Data RAG)](#-project-9-ai-real-estate-assistant-rag-on-structured-excel-data) | Excel Ingestion · Custom JS · Supabase |
| 10 | [Advanced RAG Agent for Custom Knowledge Base](#-project-10-advanced-rag-agent-for-custom-knowledge-base) | Pinecone · OpenAI Embeddings · Google Drive |
| 11 | [NSE Live Market Data Pipeline](#-project-11-nse-live-market-data-pipeline) | Custom API · JS Algorithm · Scheduled |

---

##  Project 1: FinFlow AI — Smart Finance Agent

> **An autonomous financial assistant that understands "Hinglish," remembers context, and never makes a math error.**

![Architecture](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow_Core_Orchestrator.png?raw=true)

###  About The Project

We all know that standard LLMs (like ChatGPT) are great at talking but **terrible at Math**. If you ask them to calculate a long expense sheet, they often hallucinate the numbers.

I built **FinFlow AI** to solve this problem. It is not just a chatbot; it is an intelligent **Agentic Workflow** built on **n8n**. It acts as my personal CFO that lives in Telegram, tracks my expenses in Google Sheets, remembers my debts using Vector Database (Pinecone), and sends me timely reminders.

### 💡 The "Why?" (Problem vs. Solution)

| The Problem with Normal Chatbots ❌ | How FinFlow AI Solves It ✅ |
| :--- | :--- |
| **Math Hallucinations:** LLMs guess numbers. | **Tool Calling:** It uses a calculator tool for 100% accuracy. |
| **Context Blindness:** Can't tell the difference between "Paid to Ravi" vs "Received from Ravi". | **Semantic Understanding:** Understands the direction of money (Credit/Debit) even in mixed Hinglish. |
| **Short Term Memory:** Forgets that I borrowed money last month. | **Long Term Memory:** Uses **Pinecone Vector DB** to recall past transactions. |

### ⚙️ Technical Architecture

I have divided the system into **Two Core Workflows** to keep the architecture clean and scalable:

#### 1. 🧠 FinFlow_Core_Orchestrator (The Brain)
This is the main backend logic that handles user interactions.
* **Trigger:** Receives text or audio notes from Telegram.
* **AI Router:** Analyzes the intent (Is it an expense? A query? Or just a greeting?).
* **Tool Calling:** The AI autonomously decides which tool to use:
    * `Calculator`: For math operations.
    * `Google Sheets API`: To log data.
    * `Pinecone Vector Store`: To search past records.
* **Response:** Sends a natural language summary back to the user.

#### 2. ⏰ FinFlow_Reminder_Module (The Timekeeper)
A separate dedicated workflow for managing time-based tasks.
* **Scheduler:** Runs at specific intervals to check Google Calendar/Sheet events.
* **Logic:** Filters upcoming payments or debt deadlines.
* **Alert:** Sends a proactive notification on Telegram before the due date.

![Reminder Workflow](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow_Reminder_Module.png?raw=true)

### 📸 Live Demo & Logic Showcase

Here is how the agent handles complex, real-world scenarios:

#### ✅ Scenario 1: Mixed Income & Expense (Hinglish)
I gave it a complex prompt: *"Ravi se 5000 udhar liye (Income), Ravi ko 2000 wapas diye (Expense), Petrol 100 (Expense)."*
The bot successfully categorized each item and calculated the Net Balance perfectly.

![Logic Demo](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow%20AI%20%20Smart%20Finance%20Agent%2001.png?raw=true)

#### ✅ Scenario 2: Contextual Memory & Calculation
It remembers previous context. When I asked for the total, it didn't just add numbers; it understood the **Net Balance** logic (Income - Expense) and updated it with new information.

![Memory Demo](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow%20AI%20Smart%20Finance%20Agent%2004.png?raw=true)

###  Tech Stack

* **Orchestration:** [n8n](https://n8n.io/) (Self-hosted)
* **LLM:** OpenAI GPT-4o Mini (for cost-efficiency & speed)
* **Database (Structured):** Google Sheets
* **Database (Vector):** Pinecone (for RAG/Memory)
* **Interface:** Telegram Bot API
* **Tools:** Calculator Node, HTTP Requests

### 📥 Workflow Code
[📂 Download Workflow JSON](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/FinFlow_Core_Orchestrator.json)

---

##  Project 2: AI-Powered Instagram DM Lead Qualifier (Manychat + n8n)

### 📝 Project Overview
This is a highly advanced, multi-platform conversational AI agent designed to automate the entire lead qualification funnel for a business coach directly through Instagram DMs. This system handles real-time conversations, qualifies new leads based on a specific set of rules, captures their information, and even upsells them to a discovery call—all without any human intervention.

The architecture is a sophisticated blend: **Manychat** handles the Instagram DM connection and initial user interaction, while an **n8n Webhook** sends the user's messages to an **n8n** workflow. This n8n workflow acts as the "brain," using a **DeepSeek AI Agent** (with a detailed system prompt) and **Simple Memory** to manage a stateful, human-like conversation, qualifying the lead before sending the data to Google Sheets and returning the response to Manychat.

###  Tools Used
* **n8n:** The core backend "brain" of the operation, hosting the AI agent and logic.
* **Manychat:** The frontend integration layer, connecting Instagram DMs to n8n via external requests and managing the user interface.
* **Instagram:** The user-facing chat platform.
* **DeepSeek Chat Model:** The AI model used for natural, context-aware conversation.
* **Google Sheets:** Used as the database to capture qualified leads.
* **Simple Memory (n8n):** Crucial for maintaining a stateful conversation, allowing the bot to remember previous questions and answers using the Manychat `contactId`.

###  Key Features
* **Real-Time DM Automation:** The agent responds instantly to Instagram DMs triggered by specific keywords (e.g., "Checklist").
* **Complex Conversation Flow:** The AI follows a detailed conversational script, asks qualifying questions one by one, and waits for responses.
* **Lead Qualification Logic:** Based on the user's answers, the AI determines if a lead is "qualified" or "disqualified" according to predefined rules.
* **Automated Lead Capture:** Once qualified, the agent uses an n8n tool to automatically push the new lead's name and email to a Google Sheet.
* **Dynamic Upsell:** Offers a free checklist to all users but offers a high-value discovery call *only* to qualified leads.

### 🖼️ Workflow Visuals & Code

**Manychat Flow (Frontend)**
*This screenshot shows the Manychat automation that captures user input and interacts with the n8n backend.*

![Manychat Instagram Flow](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-instagram-manychat-flow-screenshot.png?raw=true)

**n8n Workflow (Backend "Brain")**
*This screenshot shows the n8n workflow that processes the conversation, uses AI, and manages data.*

![Instagram AI Agent Brain](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-instagram-dm-lead-qualifier-screenshot.png?raw=true)

**n8n Workflow Code File**
[📄 Click here for the n8n workflow code (ai-instagram-dm-lead-qualifier.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-instagram-dm-lead-qualifier.json)

### 🧠 Challenges & Learnings
The most complex challenge was successfully integrating Manychat with an external n8n AI agent via Webhooks for a *stateful* conversation. The solution involved using Manychat to send the user's message and `contactId` to n8n, letting n8n handle memory (using `contactId` as the Session ID) and logic, and then returning the response to Manychat. This project demonstrates a powerful, scalable architecture for building truly autonomous agents on social media.

---

## 🧠 Project 3: AI Second Brain & Memory Assistant (with Reminders)

An intelligent automation system built with **n8n** that acts as a personal "Second Brain." It captures voice/text notes, stores them permanently, and even schedules tasks in Google Calendar automatically using AI.

This project consists of **two interconnected workflows** working together to handle memories and actions.

###  Key Features

* **🗣️ Voice-to-Text Support:** Integrated **OpenAI Whisper** to handle Voice Notes accurately (supports Hinglish/Hindi).
* **🧠 Long-Term Memory (RAG):** Uses **Pinecone Vector Database** to store and retrieve user notes and context.
* **📅 Smart Reminders & Scheduling:** The AI detects time-based commands (e.g., "Remind me tomorrow at 10 AM to call Raj") and automatically creates events in **Google Calendar**.
* **🤖 Context-Aware Answers:** The AI Agent answers questions based *only* on your personal stored data.
* **📂 Data Backup:** Automatically logs every transaction/note into **Google Sheets** for safety.
* **💬 Telegram Interface:** Serves as a user-friendly frontend for all interactions.

###  Tech Stack Used

* **Workflow Automation:** [n8n](https://n8n.io/)
* **AI Model:** OpenAI (GPT-4o / GPT-3.5-turbo) & Whisper
* **Vector Database:** Pinecone
* **Productivity & Database:** Google Calendar & Google Sheets
* **Interface:** Telegram Bot API

### 🚀 How It Works (The Dual-Workflow System)

The system uses an AI Router to decide the user's intent:

1.  **If it's a Memory/Note:** The data is embedded and stored in Pinecone for future retrieval.
2.  **If it's a Reminder/Task:** The second workflow kicks in, extracts the date/time using AI, and books it in Google Calendar.
3.  **If it's a Question:** The AI searches past notes in Pinecone to provide a precise answer.

### 📸 Workflow Visuals

**Workflow 1: Main Logic, Memory & RAG**
*(Handles user input, routing, saving notes, and answering questions)*

![Main Workflow - Memory & RAG](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Second%20Brain%20App.png?raw=true)


**Workflow 2: Google Calendar & Reminders Automation**
*(Handles scheduling tasks and setting reminders automatically)*

![Second Workflow - Calendar Automation](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Second%20Brain%20Workflow%202.png?raw=true)

### 📥 Download Workflow

You can import this project file directly into your n8n instance.

[📄 Download Core Logic JSON](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Second%20Brain%20App%20-%20Core%20Logic.json)

---

## 📞 Project 4: AI Calling Agent with Custom Knowledge Base (RAG + ElevenLabs)

### 📝 Project Overview
This project showcases a sophisticated, real-time **AI Calling Agent** capable of holding voice conversations and answering questions based on a custom knowledge base. Built using **n8n**, this agent integrates directly with **ElevenLabs** (as the voice platform) via **Webhooks**.

When a user calls the agent, ElevenLabs converts their speech to text and sends it to the n8n Webhook. The n8n workflow then uses a RAG (Retrieval-Augmented Generation) pipeline: it searches a **Pinecone** vector database (populated with custom documents) for relevant information, uses **OpenAI** to generate a natural language response based on that context, and sends the text response back to ElevenLabs via the `Respond to Webhook` node. ElevenLabs converts this text back into speech for the user, enabling a seamless voice conversation powered by custom data.

###  Tools Used
* **n8n:** The core automation engine orchestrating the logic.
* **Webhook (n8n):** Receives real-time voice transcriptions from ElevenLabs.
* **ElevenLabs:** The voice AI platform handling Text-to-Speech (TTS), Speech-to-Text (STT), and call management.
* **Pinecone:** Vector database storing and providing semantic search capabilities for the custom knowledge base.
* **OpenAI Embeddings:** Used to convert text chunks into vectors for storage and search.
* **OpenAI Chat Model:** Generates the final conversational response based on retrieved context.
* **Simple Memory (n8n):** Essential for maintaining conversation state throughout the phone call using a unique `call_id`.
* **Respond to Webhook (n8n):** Sends the generated text response back to ElevenLabs.

###  Key Features
* **Real-time Voice Conversation:** Enables natural voice interaction with an AI agent.
* **Custom Knowledge Base (RAG):** The agent answers questions based on specific documents provided by the user, not just general knowledge.
* **Direct Webhook Integration:** Demonstrates real-time data exchange between n8n and a voice platform like ElevenLabs.
* **Stateful Memory Management:** Utilizes a unique identifier (`call_id` from ElevenLabs, passed via webhook) to remember the context of the ongoing phone call.
* **End-to-End Voice Automation:** Manages the entire loop from receiving voice, processing, retrieving info, generating response, and sending voice back.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![RAG Calling Agent Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Rag%20Calling%20Voice%20%20Agent.png?raw=true)

**Workflow Code File**
[📄 Click here for the Calling Agent Workflow code (rag-calling-agent.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/RAG%20Calling%20Agent.json)

### 🧠 Challenges & Learnings
The most critical challenge was establishing and maintaining **conversation memory** in a real-time voice call scenario. Unlike text chats, voice requires immediate responses and robust state management. The key was configuring **ElevenLabs** to send a unique `call_id` within the webhook payload and then utilizing this ID as the **Session Key** in n8n's `Simple Memory` node. This project highlights the complexities and solutions involved in building sophisticated, stateful voice AI agents integrated with custom knowledge bases.

---

## 🚀 Project 5: Telegram Subscriber Migration & Data Capture System

This project was designed to solve a critical **Data Retention Challenge** for a client with over **300,000 subscribers**.

###  Project Context (The Problem)
The client wanted to migrate their massive audience of **300k+ users** from an existing database to a **New Premium Channel**.

However, simply sharing a direct invite link was not an option because:
1.  **Data Loss:** Direct links do not reveal *who* joined.
2.  **No Tracking:** The client wanted to ensure every single user who moved to the new channel was captured in a database for future communication.

### 💡 The Solution (The "Bridge Bot")
I developed an automated **n8n Workflow** that acts as a smart bridge between the old subscribers and the new channel.

Instead of a direct link, users are sent to this bot. The workflow ensures:
1.  **Seamless Migration:** Users click the bot link → Click 'Start' → Get the Channel Link.
2.  **100% Data Capture:** The moment a user interacts, their **User ID, Name, and Date** are automatically saved to **Google Sheets**.
3.  **Zero Friction:** The bot instantly creates a personalized "Join Button" so the user experience remains fast and smooth.

### 📈 Impact
* ✅ **300,000+ subscribers** migrated successfully
* ✅ **100% data capture** — zero anonymous joins
* ✅ **Zero friction UX** — single-click flow for the user
* ✅ **CRM-ready database** for future communications

### 📸 Project Demo
*The interface where users are approved and given access to the channel.*

![Bot Interface](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Stock%20Market%20Telegram%20Bot.png?raw=true)

### 🛠️ Tech Stack
* **n8n** (Backend Automation Logic)
* **Telegram Bot API** (User Interface)
* **Google Sheets** (Database for 300k+ Leads)

### 📂 Workflow Code
The complete automation logic for this migration system can be found here:
[📄 View Workflow Code (JSON)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Stock%20Market%20Telegram%20Bot%20.json)

---

## 🍽️ Project 6: AI WhatsApp Restaurant Bot (via Meta API)

### 📝 Project Overview
This is a fully autonomous AI agent built in n8n that manages a restaurant's complete ordering system **directly through the official Meta WhatsApp API**. This bot acts as a smart food ordering assistant for "MDA Restaurant," handling the entire customer conversation in real-time.

A key feature of this agent is its resourcefulness: it uses **Google Sheets as its sole database and knowledge base**. It intelligently switches between different "tools" to check inventory, answer FAQs, and post confirmed orders to different sheets. The agent is powered by the **DeepSeek Chat Model** for natural and intelligent conversation.

###  Tools Used
* **n8n:** The core automation platform.
* **WhatsApp Trigger (Meta API):** Connects directly to the Meta for Developers App for instant, two-way communication.
* **DeepSeek Chat Model:** The AI brain for understanding context and deciding which tool to use.
* **Google Sheets (as Database):**
    * `GET Inventory` (Tool 1): A node that reads a sheet to check stock levels.
    * `get FAQ` (Tool 2): A node that reads a sheet to answer common questions.
    * `Post Order` (Tool 3): A node that writes to a sheet to confirm new orders.
* **Simple Memory:** To maintain a stateful conversation and remember the user's order.

###  Key Features
* **Direct Meta API Integration:** Uses the official `WhatsApp Trigger` node, demonstrating a complex setup with Meta's developer platform.
* **Google Sheets as a "Database":** The AI agent uses Google Sheets as its live database, proving that powerful AI systems can run on simple, cost-effective tools.
* **Multi-Tool Capability:** The agent is prompted to intelligently choose between its three different Google Sheet tools based on the user's request (e.g., checking inventory vs. answering a question).
* **End-to-End Order Management:** Handles the entire flow: from the initial "hello" to checking stock, taking the order, and finally confirming it by writing to a Google Sheet.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![WhatsApp Order Bot Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-whatsapp-restaurant-bot-screenshot.png?raw=true)

**Workflow Code File**
[📄 Click here for the workflow code (ai-whatsapp-restaurant-bot.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-whatsapp-restaurant-bot.json)

### 🧠 Challenges & Learnings
The most significant technical challenge of this project was not in n8n, but in navigating the complex **Meta for Developers platform** to successfully set up the WhatsApp Business App and generate the permanent secret keys and credentials. This is a major technical hurdle that was successfully overcome.

On the n8n side, the main challenge was crafting a precise prompt for the DeepSeek model, teaching it to reliably switch between its three different Google Sheet "tools" based purely on the user's WhatsApp message. This project demonstrates a complete, practical, and end-to-end automated system for any small business.

---

## 📊 Project 7: AI-Powered Business Dashboard (n8n + Google Sheets + Lovable)

### 📝 Project Overview
This project is a powerful, custom-built internal tool that allows a business manager to run their entire operation from a single, intelligent chat interface. It combines a **Lovable** dashboard (frontend), a **Google Sheet** (database), and an **n8n AI Agent** (backend).

A manager can type natural language commands (e.g., "Update Fernanda's budget" or "Send Martin an email") into the dashboard chat. The n8n agent receives this via a webhook, understands the command, uses its "tools" to perform the action (like updating the Google Sheet or sending a Gmail), and then confirms the task is complete, all within the chat.

###  Tools Used
* **n8n:** The central automation "brain" that hosts the AI Agent and manages the logic.
* **Lovable.dev:** Used to create the beautiful, real-time analytics dashboard and chat interface.
* **Google Sheets:** Acts as the live database, storing all client and project data.
* **OpenAI Chat Model:** The AI model that understands user commands and decides which tool to use.
* **Gmail Node:** Used as a tool by the agent to send emails directly from the chat interface.
* **Webhook:** The real-time connection between the Lovable chatbot and the n8n agent.

###  Key Features
* **AI-Powered Dashboard:** The agent turns a static dashboard into an interactive "operating system."
* **Natural Language Commands:** The manager doesn't need to know n8n or Google Sheets; they just need to chat. The agent (with its clear system prompt) does the rest.
* **Multi-Tool Capability:** The agent can intelligently choose between reading data, updating data, or sending emails, all from one command.
* **Real-time Sync:** Any changes made by the agent in the Google Sheet are instantly reflected on the Lovable dashboard.

### 🖼️ Workflow Visuals & Code

**Frontend Dashboard by Lovable**

![Headshot Studio Dashboard UI](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-business_lovable-dashboard-ui.png?raw=true)

**n8n Workflow (The Backend "Brain")**

![AI Business Dashboard Agent Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-business-dashboard-agent-screenshot.png?raw=true)

**n8n Workflow Code File**
[📄 Click here for the workflow code (ai-business-dashboard-agent.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-business-dashboard-agent.json)

### 🧠 Challenges & Learnings
The most powerful part of this project was creating a seamless loop between a user-friendly frontend (Lovable) and a powerful backend (n8n). The key was designing a clear system prompt and reliable tools (like `Get Rows` and `Update Rows`) that allow the AI to safely and accurately manage a live database (Google Sheets) simply through chat.

---

## 🏛️ Project 8: Scalable AI Expert Bot (RAG on Supabase + Postgres Memory)

### 📝 Project Overview
This project demonstrates a truly robust and scalable AI agent built in n8n. This isn't just a simple chatbot; it's an "AI Expert" designed to learn a specific knowledge base (in this case, "The Rules of Golf" PDF) and answer user questions with perfect accuracy.

What makes this build powerful is its "enterprise-grade" architecture:
1.  **Supabase Vector Store:** It uses Supabase for its RAG pipeline, a powerful open-source database that handles both data storage and vector search.
2.  **Persistent Postgres Memory:** It uses a dedicated `Postgres Chat Memory` node, allowing the agent to remember conversations permanently and across multiple sessions, a feature crucial for real-world business applications.

###  Tools Used
* **n8n:** The central automation platform.
* **Supabase:** Used as the primary vector database for both document ingestion and as a retrieval tool for the AI agent.
* **OpenAI:** Used for generating embeddings (`text-embedding-3-small`) and powering the chat model.
* **Postgres Chat Memory:** For storing conversation history in an external database, enabling true stateful conversation.
* **Default Data Loader:** To load, process, and split the source PDF document.

###  Key Features
* **Dual-Purpose Workflow:** A clean, unified workflow that handles both data ingestion (learning the PDF via a manual trigger) and live chat Q&A.
* **Supabase RAG Pipeline:** The agent retrieves factual information ("rules of golf") directly from the Supabase vector database to provide accurate, fact-based answers.
* **Scalable Memory:** By using a Postgres database for memory instead of temporary session memory, this agent can handle thousands of users and build long-term context.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![AI Chatbot Workflow (n8n, OpenAI, Supabase)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/AI%20Chatbot%20Workflow%20(n8n,%20OpenAI,%20Supabase).png?raw=true)

**Workflow Code File**
[📄 Click here for the workflow code (AI Chatbot Workflow (n8n, OpenAI, Supabase).json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/AI%20Chatbot%20Workflow%20(n8n%2C%20OpenAI%2C%20Supabase).json)

### 🧠 Challenges & Learnings
The most powerful automations are not just smart, they are robust. The key learning here was integrating **Supabase** as an all-in-one database and vector store, which is a highly scalable alternative to other tools. Combining this with **persistent Postgres memory** creates an enterprise-ready AI assistant that is both intelligent (RAG) and stateful (remembers conversations).

---

## 🏠 Project 9: AI Real Estate Assistant (RAG on Structured Excel Data)

### 📝 Project Overview
This project is a powerful AI assistant built for the **real estate industry**, demonstrating how to build a RAG agent on structured business data, not just simple text files.

This agent acts as a 24/7 virtual property expert. It answers specific user questions about property listings (e.g., "How many bedrooms?", "What is the price?") by retrieving facts from a **Supabase Vector Store**.

What makes this project unique is its data ingestion pipeline: it automatically "learns" from **structured Excel (XLS) files** added to Google Drive. It uses a **custom JavaScript node** to properly format each row of data before embedding it, ensuring the AI can understand and retrieve complex property details accurately.

###  Tools Used
* **n8n:** The central automation platform.
* **Google Drive Trigger:** To automatically detect and ingest new property listing files.
* **Extract from File:** To read data directly from Excel (XLS) files.
* **Code in JavaScript:** To iterate over Excel rows, clean, and format the structured data for the AI.
* **Supabase Vector Store:** The vector database for both storing property data and RAG retrieval.
* **OpenAI:** Used for generating embeddings and powering the chat model.
* **Simple Memory:** To maintain conversational context.

###  Key Features
* **RAG on Structured Data:** Moves beyond basic PDFs to handle structured Excel data, which is how most businesses store their information.
* **Custom Data Transformation:** Uses **JavaScript** to ensure data is clean and perfectly formatted before AI ingestion, guaranteeing high-quality answers.
* **High-Accuracy Answers:** The agent provides fact-based answers about properties by retrieving data directly from the Supabase vector store.
* **Automated Knowledge Updates:** The agent's knowledge base expands automatically as new property listing files are added to Google Drive.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![AI Real Estate Chatbot Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-real-estate-rag-agent-screenshot.png?raw=true)

**Workflow Code File**
[📄 Click here for the workflow code (ai-real-estate-rag-agent.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-real-estate-rag-agent-json.json)

### 🧠 Challenges & Learnings
The most interesting challenge was handling *structured data* from an Excel file, not just simple text. This required using a custom JavaScript node to iterate over each property listing and format it into clean, embeddable text. This proves the RAG pipeline can be adapted for any business data, not just PDFs.

---

## 📚 Project 10: Advanced RAG Agent for Custom Knowledge Base

### 📝 Project Overview
This project showcases an advanced AI system known as a Retrieval-Augmented Generation (RAG) agent. The system is built in two parts: the first part automatically processes and "learns" from documents uploaded to Google Drive, creating a specialized knowledge base in Pinecone. The second part is a chat agent that uses this custom knowledge base to answer user questions with high accuracy, even in multiple languages. This is a powerful, self-updating system that can be adapted for any company's internal documents.

###  Tools Used
* **n8n:** The core platform for both workflows.
* **Google Drive:** Used to trigger the learning process.
* **Pinecone:** The vector database for storing the knowledge.
* **OpenAI:** Used for creating vector embeddings and generating answers.

###  Key Features & How It Works

This system is divided into two distinct, automated workflows:

**Part 1: The Knowledge Base Builder**
This workflow constantly monitors a Google Drive folder. When a new document is added, it automatically reads the content, breaks it down into meaningful chunks, converts those chunks into vector embeddings using AI, and stores them in the Pinecone database. This part is responsible for the continuous learning of the system.

**Part 2: The Intelligent Q&A Agent**
This is the user-facing chat agent. When a user asks a question, the agent searches the Pinecone knowledge base to find the most relevant information from the uploaded documents. It then provides this information to the OpenAI model along with the original question, enabling the AI to generate a precise answer based on verified facts.

### 🖼️ Workflow Visuals & Code

Below are the screenshots and links to the code for both parts of the system.

#### Part 1: Knowledge Base Builder Workflow
![Knowledge Base Builder Screenshot](https://raw.githubusercontent.com/rvmakvana1/n8n-automation-portfolio/main/rag-knowledge-base-builder-screenshot.png)

[📄 Click here for the Knowledge Base Builder code (rag-knowledge-base-builder.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/rag-knowledge-base-builder%20Step-1.json)

#### Part 2: The Chat Agent Workflow
![Chat Agent Screenshot](https://raw.githubusercontent.com/rvmakvana1/n8n-automation-portfolio/main/rag-chat-agent-screenshot.png)

[📄 Click here for the Chat Agent Workflow code (rag-chat-agent.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/rag-chat-agent%20Step-2.json)

### 🧠 Challenges & Learnings
Building this RAG agent was a significant step up in complexity. The main challenge was designing the two-part architecture for continuous learning and real-time answering. A key learning was the power of vector embeddings, which allow the AI to search for information based on semantic meaning, not just keywords. This makes the system incredibly powerful and versatile, capable of working with any document and in multiple languages without any changes.

---

## 📈 Project 11: NSE Live Market Data Pipeline

### 📝 Project Overview
This workflow automates the process of fetching live option chain data for NIFTY from the National Stock Exchange (NSE) website every 3 minutes. It intelligently identifies the "At-the-Money" (ATM) strike price and extracts the 7 most relevant rows (ATM, 3 above, and 3 below). This filtered data is then automatically appended to a Google Sheet, providing the user with a real-time, focused view of the most active part of the market.

This project goes beyond simple data scraping — it demonstrates **secure dynamic API handling** (managing NSE's session cookies and headers), **custom JavaScript algorithms** (for ATM detection logic), and **intelligent data filtering** that delivers decision-ready data instead of raw dumps.

###  Tools Used
* **n8n:** The core automation platform used to build and run the workflow.
* **HTTP Request Node:** To call the NSE's background API and fetch live data, handling headers and cookies.
* **Code Node (JavaScript):** To implement the custom logic for identifying the At-the-Money (ATM) strike price.
* **Google Sheets:** The database where the final, filtered data is stored.
* **Schedule Trigger:** To run the workflow autonomously every 3 minutes.

###  Key Features
* **Scheduled Execution:** Runs automatically every 3 minutes during market hours.
* **Dynamic Data Scraping:** Fetches data from a secure and dynamic website API, handling session cookies and authentication headers.
* **Intelligent Filtering:** Custom JavaScript algorithm automatically pinpoints the most relevant market data (At-the-Money strike).
* **Automated Data Entry:** Saves the processed, decision-ready data directly into a Google Sheet for analysis.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![NSE Live Option Chain Workflow Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/NSE%20DATA%20.png)

**Workflow Code File**
[📄 Click here for the n8n workflow code (NSE DATA AUTOMATION.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/NSE%20DATA%20AUTOMATION.json)

### 🧠 Challenges & Learnings
The most interesting technical challenge was that NSE's option chain data isn't a public endpoint — it requires careful **session handling and header management** to maintain a valid request context. The solution involved configuring the HTTP Request node to mimic browser behavior and pass the right cookies. Combining this API engineering with custom JavaScript filtering logic shows how automation can deliver **decision-ready data**, not just raw dumps — a pattern applicable to any financial or market data pipeline.

---

## 📬 Let's Connect

I'm actively building AI automation systems and open to **internship**, **freelance**, and **full-time** opportunities in the AI Agent / Automation space.

If you'd like to collaborate, discuss a project, or just chat about agentic AI — feel free to reach out.

---

⭐ **If you find these projects useful, consider starring this repo!**
