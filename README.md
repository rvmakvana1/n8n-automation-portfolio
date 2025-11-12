# My n8n Automation Portfolio

Portfolio of an AI Agent & Automation Specialist leveraging n8n, OpenAI, DeepSeek & more. Demonstrating expertise in building intelligent, multi-platform automations from concept to deployment.

---

---

## Project 1: AI-Powered Instagram DM Lead Qualifier (Manychat + n8n)

### 📝 Project Overview
This is a highly advanced, multi-platform conversational AI agent designed to automate the entire lead qualification funnel for a business coach directly through Instagram DMs. This system handles real-time conversations, qualifies new leads based on a specific set of rules, captures their information, and even upsells them to a discovery call—all without any human intervention.

The architecture is a sophisticated blend: **Manychat** handles the Instagram DM connection and initial user interaction, while an **n8n Webhook** sends the user's messages to an **n8n** workflow. This n8n workflow acts as the "brain," using a **DeepSeek AI Agent** (with a detailed system prompt) and **Simple Memory** to manage a stateful, human-like conversation, qualifying the lead before sending the data to Google Sheets and returning the response to Manychat.

### 🛠️ Tools Used
* **n8n:** The core backend "brain" of the operation, hosting the AI agent and logic.
* **Manychat:** The frontend integration layer, connecting Instagram DMs to n8n via external requests and managing the user interface.
* **Instagram:** The user-facing chat platform.
* **DeepSeek Chat Model:** The AI model used for natural, context-aware conversation.
* **Google Sheets:** Used as the database to capture qualified leads.
* **Simple Memory (n8n):** Crucial for maintaining a stateful conversation, allowing the bot to remember previous questions and answers using the Manychat `contactId`.

### ✨ Key Features
* **Real-Time DM Automation:** The agent responds instantly to Instagram DMs triggered by specific keywords (e.g., "Checklist").
* **Complex Conversation Flow:** The AI follows a detailed conversational script, asks qualifying questions one by one, and waits for responses.
* **Lead Qualification Logic:** Based on the user's answers, the AI determines if a lead is "qualified" or "disqualified" according to predefined rules.
* **Automated Lead Capture:** Once qualified, the agent uses an n8n tool to automatically push the new lead's name and email to a Google Sheet.
* **Dynamic Upsell:** Offers a free checklist to all users but offers a high-value discovery call *only* to qualified leads.

### 🖼️ Workflow Visuals & Code

**Manychat Flow (Frontend)**
* *This screenshot shows the Manychat automation that captures user input and interacts with the n8n backend.*

![Manychat Instagram Flow](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-instagram-manychat-flow-screenshot.png?raw=true)

**n8n Workflow (Backend "Brain")**
* *This screenshot shows the n8n workflow that processes the conversation, uses AI, and manages data.*

![Instagram AI Agent Brain](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-instagram-dm-lead-qualifier-screenshot.png?raw=true)

**n8n Workflow Code File**

[Click here for the n8n workflow code (ai-instagram-dm-lead-qualifier.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-instagram-dm-lead-qualifier.json)

### 🧠 Challenges & Learnings
The most complex challenge was successfully integrating Manychat with an external n8n AI agent via Webhooks for a *stateful* conversation. The solution involved using Manychat to send the user's message and `contactId` to n8n, letting n8n handle memory (using `contactId` as the Session ID) and logic, and then returning the response to Manychat. This project demonstrates a powerful, scalable architecture for building truly autonomous agents on social media.

---

## Project 2: NSE Live Option Chain Data Automation

### Project Overview
This workflow automates the process of fetching live option chain data for NIFTY from the National Stock Exchange (NSE) website every 3 minutes. It intelligently identifies the "At-the-Money" (ATM) strike price and extracts the 7 most relevant rows (ATM, 3 above, and 3 below). This filtered data is then automatically appended to a Google Sheet, providing the user with a real-time, focused view of the most active part of the market.

### Tools Used
* **n8n:** The core automation platform used to build and run the workflow.
* **HTTP Request Node:** To call the NSE's background API and fetch live data, handling headers and cookies.
* **Code Node (JavaScript):** To implement the custom logic for identifying the At-the-Money (ATM) strike price.
* **Google Sheets:** The database where the final, filtered data is stored.

### Key Features
* **Scheduled Execution:** Runs automatically every 3 minutes.
* **Dynamic Data Scraping:** Fetches data from a secure and dynamic website API.
* **Intelligent Filtering:** Automatically pinpoints the most relevant market data (At-the-Money).
* **Automated Data Entry:** Saves the processed data directly into a Google Sheet.

### Project Files
### Workflow Visual
![NSE Live Option Chain Workflow Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/NSE%20DATA%20.png)
* [**n8n Workflow Code (NSE DATA AUTOMATION.json)**](./NSE%20DATA%20AUTOMATION.json)


---

## Project 3: AI-Powered Feedback Sorter & Responder

### 📝 Project Overview
This workflow automates the entire process of managing and responding to customer feedback. When a user submits a feedback form, this system intelligently analyzes the message using AI to determine its purpose. It automatically categorizes the feedback as a "Complaint," "Compliment," or a "Feature Request," then saves the data to a dedicated Airtable base and **sends targeted email notifications** to the appropriate teams for immediate action. This saves hours of manual work and ensures a rapid and organized response to all user feedback.

### 🛠️ Tools Used
* **n8n:** The core automation platform that connects all the services.
* **OpenAI:** The AI model used to analyze and categorize the feedback message.
* **Airtable:** The database where the categorized feedback is automatically stored in separate, organized tables.
* **Gmail (or Email Node):** Used for sending automated and conditional email notifications.

### ✨ Key Features
* **Automated Form Submission Trigger:** The workflow starts instantly when a new feedback form is submitted.
* **AI-Powered Categorization:** An AI Agent reads the user's message and accurately classifies it into one of three predefined categories.
* **Intelligent Routing:** A Switch node directs the data down different paths based on the AI's classification.
* **Structured Record Keeping:** Each piece of feedback is automatically saved to the correct table in an Airtable base, creating a clean and organized database.
* **Automated Email Notifications:** Based on the feedback category, the workflow automatically sends an email to the appropriate team. For example, complaints are sent to the support team for immediate action, while compliments might be sent to the marketing team for morale.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![AI Feedback Sorter Screenshot](https://raw.githubusercontent.com/rvmakvana1/n8n-automation-portfolio/main/ai-feedback-sorter-screenshot.png)
**Workflow Code File**

[Click here to view the n8n workflow code (ai-feedback-sorter.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-feedback-sorter.json)
### 🧠 Challenges & Learnings
The main challenge was to ensure the AI could accurately categorize diverse user feedback with a simple prompt. I learned that by giving the AI a very specific and focused role ("Your role is to determine..."), even a simple prompt can yield highly accurate and reliable results. This project demonstrates that complex decision-making and follow-up actions (like sending emails) can be effectively automated.


---

## Project 4: Personalized AI Poem Generator (ft. DeepSeek)

### 📝 Project Overview
This is a creative and engaging workflow that demonstrates the power of AI for hyper-personalization. It takes a user's details—such as their name, appearance, and profession—through a simple web form. An AI Agent, powered by the **DeepSeek Chat Model**, then uses these details to instantly create a unique, two-line poem specifically for that person. The generated poem is then automatically saved back into an Airtable database.

### 🛠️ Tools Used
* **n8n:** The core automation platform for building and running the workflow.
* **n8n Forms:** Used as the simple web interface for collecting user details.
* **DeepSeek Chat Model:** The creative AI engine that generates the personalized poem based on the user's input.
* **Airtable:** The database used to first log the user's submission and then update it with the AI-generated poem.

### ✨ Key Features
* **Simple Web Form Input:** An easy-to-use n8n form allows anyone to input their details without any technical knowledge.
* **Dynamic AI Prompting:** The AI prompt is dynamically populated with the data from the form, ensuring each poem is unique and relevant to the user.
* **Creative Content Generation:** This workflow showcases how specific AI models like DeepSeek can be used for creative tasks, not just analytical ones.
* **Two-Step Database Operation:** The system first creates a record in Airtable and then updates that same record with the AI's output, a robust pattern that ensures data integrity.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![AI Poem Generator Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-personalized-poem-generator-screenshot.png?raw=true])

**Workflow Code File**

[Click here to view the n8n workflow code (ai-poem-generator-deepseek.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-personalized-poem-generator.json)
### 🧠 Challenges & Learnings
The interesting part of this project was designing a workflow that handles creative generation. I learned that automation isn't limited to business-centric tasks; it can also be a powerful tool for creating personalized user experiences. Experimenting with the **DeepSeek model** specifically showed its strong capability in generating concise and creative text based on minimal input.


---

## Project 5: OpenAI-Powered Email Reply Agent

### 📝 Project Overview
This workflow functions as a personal inbox assistant, designed to automate the process of replying to incoming emails. The system runs on a schedule, automatically checks a Gmail inbox for new, unread messages, and uses a highly customized **OpenAI** Agent to draft professional, human-like replies. After logging the reply for record-keeping, it marks the original email as "read" to ensure it isn't processed again. This is a powerful productivity tool that saves significant time on email management.

### 🛠️ Tools Used
* **n8n:** The core automation platform.
* **Gmail:** Used for fetching incoming emails and marking them as read.
* **OpenAI:** The AI brain that analyzes the email content and drafts the reply based on a custom persona.
* **Airtable (or similar database):** Used to create a log of every email that has been automatically replied to.

### ✨ Key Features
* **Scheduled Operation:** The workflow runs automatically at set intervals to proactively manage the inbox.
* **Selective Processing:** It is configured to only fetch the top unread emails, making the process highly efficient.
* **Context-Aware AI Replies:** The AI Agent is equipped with a detailed system message that defines its role and user-specific information, enabling it to generate contextually relevant replies.
* **Automated Logging:** Every action taken by the agent is recorded in an Airtable base, creating a transparent log of all automated communications.
* **Inbox Cleanup:** By marking emails as "read" after processing, the workflow maintains a clean and robust automation loop.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![Email Reply Agent Screenshot](https://raw.githubusercontent.com/rvmakvana1/n8n-automation-portfolio/main/ai-email-reply-agent-screenshot.png)
**Workflow Code File**

[Click here to view the n8n workflow code (ai-email-reply-agent.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Email%20Reply%20Agent.json)
### 🧠 Challenges & Learnings
The primary challenge was to make the AI's replies sound genuinely human. This was solved by creating a very detailed XML-style system message that gave the AI a complete personality and context with OpenAI. A key learning was the importance of building a full "loop" in automation—not just performing the main action (replying), but also including setup (fetching mail) and cleanup (marking as read) to create a truly reliable system.


---

## Project 6: Advanced RAG Agent for Custom Knowledge Base

### 📝 Project Overview
This project showcases an advanced AI system known as a Retrieval-Augmented Generation (RAG) agent. The system is built in two parts: the first part automatically processes and "learns" from documents uploaded to Google Drive, creating a specialized knowledge base in Pinecone. The second part is a chat agent that uses this custom knowledge base to answer user questions with high accuracy, even in multiple languages. This is a powerful, self-updating system that can be adapted for any company's internal documents.

### 🛠️ Tools Used
* **n8n:** The core platform for both workflows.
* **Google Drive:** Used to trigger the learning process.
* **Pinecone:** The vector database for storing the knowledge.
* **OpenAI:** Used for creating vector embeddings and generating answers.

### ✨ Key Features & How It Works

This system is divided into two distinct, automated workflows:

**Part 1: The Knowledge Base Builder**
* This workflow constantly monitors a Google Drive folder. When a new document is added, it automatically reads the content, breaks it down into meaningful chunks, converts those chunks into vector embeddings using AI, and stores them in the Pinecone database. This part is responsible for the continuous learning of the system.

**Part 2: The Intelligent Q&A Agent**
* This is the user-facing chat agent. When a user asks a question, the agent searches the Pinecone knowledge base to find the most relevant information from the uploaded documents. It then provides this information to the OpenAI model along with the original question, enabling the AI to generate a precise answer based on verified facts.

### 🖼️ Workflow Visuals & Code

Below are the screenshots and links to the code for both parts of the system.

#### Part 1: Knowledge Base Builder Workflow
![Knowledge Base Builder Screenshot](https://raw.githubusercontent.com/rvmakvana1/n8n-automation-portfolio/main/rag-knowledge-base-builder-screenshot.png)

[Click here for the Knowledge Base Builder code (rag-knowledge-base-builder.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/rag-knowledge-base-builder%20Step-1.json)

#### Part 2: The Chat Agent Workflow
![Chat Agent Screenshot](https://raw.githubusercontent.com/rvmakvana1/n8n-automation-portfolio/main/rag-chat-agent-screenshot.png)

[Click here for the Chat Agent Workflow code (rag-chat-agent.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/rag-chat-agent%20Step-2.json)

### 🧠 Challenges & Learnings
Building this RAG agent was a significant step up in complexity. The main challenge was designing the two-part architecture for continuous learning and real-time answering. A key learning was the power of vector embeddings, which allow the AI to search for information based on semantic meaning, not just keywords. This makes the system incredibly powerful and versatile, capable of working with any document and in multiple languages without any changes.


---

---

## Project 7: AI WhatsApp Restaurant Bot (via Meta API)

### 📝 Project Overview
This is a fully autonomous AI agent built in n8n that manages a restaurant's complete ordering system **directly through the official Meta WhatsApp API**. This bot acts as a smart food ordering assistant for "MDA Restaurant," handling the entire customer conversation in real-time.

A key feature of this agent is its resourcefulness: it uses **Google Sheets as its sole database and knowledge base**. It intelligently switches between different "tools" to check inventory, answer FAQs, and post confirmed orders to different sheets. The agent is powered by the **DeepSeek Chat Model** for natural and intelligent conversation.

### 🛠️ Tools Used
* **n8n:** The core automation platform.
* **WhatsApp Trigger (Meta API):** Connects directly to the Meta for Developers App for instant, two-way communication.
* **DeepSeek Chat Model:** The AI brain for understanding context and deciding which tool to use.
* **Google Sheets (as Database):**
    * `GET Inventory` (Tool 1): A node that reads a sheet to check stock levels.
    * `get FAQ` (Tool 2): A node that reads a sheet to answer common questions.
    * `Post Order` (Tool 3): A node that writes to a sheet to confirm new orders.
* **Simple Memory:** To maintain a stateful conversation and remember the user's order.

### ✨ Key Features
* **Direct Meta API Integration:** Uses the official `WhatsApp Trigger` node, demonstrating a complex setup with Meta's developer platform.
* **Google Sheets as a "Database":** The AI agent uses Google Sheets as its live database, proving that powerful AI systems can run on simple, cost-effective tools.
* **Multi-Tool Capability:** The agent is prompted to intelligently choose between its three different Google Sheet tools based on the user's request (e.g., checking inventory vs. answering a question).
* **End-to-End Order Management:** Handles the entire flow: from the initial "hello" to checking stock, taking the order, and finally confirming it by writing to a Google Sheet.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![WhatsApp Order Bot Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-whatsapp-restaurant-bot-screenshot.png?raw=true)

**Workflow Code File**

[Click here for the workflow code (ai-whatsapp-restaurant-bot.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-whatsapp-restaurant-bot.json)

### 🧠 Challenges & Learnings
The most significant technical challenge of this project was not in n8n, but in navigating the complex **Meta for Developers platform** to successfully set up the WhatsApp Business App and generate the permanent secret keys and credentials. This is a major technical hurdle that was successfully overcome.

On the n8n side, the main challenge was crafting a precise prompt for the DeepSeek model, teaching it to reliably switch between its three different Google Sheet "tools" based purely on the user's WhatsApp message. This project demonstrates a complete, practical, and end-to-end automated system for any small business.


---

## Project 8 : AI Calling Agent with Custom Knowledge Base (RAG + ElevenLabs)

### 📝 Project Overview
This project showcases a sophisticated, real-time **AI Calling Agent** capable of holding voice conversations and answering questions based on a custom knowledge base. Built using **n8n**, this agent integrates directly with **ElevenLabs** (as the voice platform) via **Webhooks**.

When a user calls the agent, ElevenLabs converts their speech to text and sends it to the n8n Webhook. The n8n workflow then uses a RAG (Retrieval-Augmented Generation) pipeline: it searches a **Pinecone** vector database (populated with custom documents) for relevant information, uses **OpenAI** to generate a natural language response based on that context, and sends the text response back to ElevenLabs via the `Respond to Webhook` node. ElevenLabs converts this text back into speech for the user, enabling a seamless voice conversation powered by custom data.

### 🛠️ Tools Used
* **n8n:** The core automation engine orchestrating the logic.
* **Webhook (n8n):** Receives real-time voice transcriptions from ElevenLabs.
* **ElevenLabs:** The voice AI platform handling Text-to-Speech (TTS), Speech-to-Text (STT), and call management.
* **Pinecone:** Vector database storing and providing semantic search capabilities for the custom knowledge base.
* **OpenAI Embeddings:** Used to convert text chunks into vectors for storage and search.
* **OpenAI Chat Model:** Generates the final conversational response based on retrieved context.
* **Simple Memory (n8n):** Essential for maintaining conversation state throughout the phone call using a unique `call_id`.
* **Respond to Webhook (n8n):** Sends the generated text response back to ElevenLabs.

### ✨ Key Features
* **Real-time Voice Conversation:** Enables natural voice interaction with an AI agent.
* **Custom Knowledge Base (RAG):** The agent answers questions based on specific documents provided by the user, not just general knowledge.
* **Direct Webhook Integration:** Demonstrates real-time data exchange between n8n and a voice platform like ElevenLabs.
* **Stateful Memory Management:** Utilizes a unique identifier (`call_id` from ElevenLabs, passed via webhook) to remember the context of the ongoing phone call.
* **End-to-End Voice Automation:** Manages the entire loop from receiving voice, processing, retrieving info, generating response, and sending voice back.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![RAG Calling Agent Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Rag%20Calling%20Voice%20%20Agent.png?raw=true)

**Workflow Code File**

[Click here for the Calling Agent Workflow code (rag-calling-agent.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/RAG%20Calling%20Agent.json)

### 🧠 Challenges & Learnings
The most critical challenge was establishing and maintaining **conversation memory** in a real-time voice call scenario. Unlike text chats, voice requires immediate responses and robust state management. The key was configuring **ElevenLabs** to send a unique `call_id` within the webhook payload and then utilizing this ID as the **Session Key** in n8n's `Simple Memory` node. This project highlights the complexities and solutions involved in building sophisticated, stateful voice AI agents integrated with custom knowledge bases.


---

## Project 9: Scalable AI Expert Bot (RAG on Supabase + Postgres Memory)

### 📝 Project Overview
This project demonstrates a truly robust and scalable AI agent built in n8n. This isn't just a simple chatbot; it's an "AI Expert" designed to learn a specific knowledge base (in this case, "The Rules of Golf" PDF) and answer user questions with perfect accuracy.

What makes this build powerful is its "enterprise-grade" architecture:
1.  **Supabase Vector Store:** It uses Supabase for its RAG pipeline, a powerful open-source database that handles both data storage and vector search.
2.  **Persistent Postgres Memory:** It uses a dedicated `Postgres Chat Memory` node, allowing the agent to remember conversations permanently and across multiple sessions, a feature crucial for real-world business applications.

### 🛠️ Tools Used
* **n8n:** The central automation platform.
* **Supabase:** Used as the primary vector database for both document ingestion and as a retrieval tool for the AI agent.
* **OpenAI:** Used for generating embeddings (`text-embedding-3-small`) and powering the chat model.
* **Postgres Chat Memory:** For storing conversation history in an external database, enabling true stateful conversation.
* **Default Data Loader:** To load, process, and split the source PDF document.

### ✨ Key Features
* **Dual-Purpose Workflow:** A clean, unified workflow that handles both data ingestion (learning the PDF via a manual trigger) and live chat Q&A.
* **Supabase RAG Pipeline:** The agent retrieves factual information ("rules of golf") directly from the Supabase vector database to provide accurate, fact-based answers.
* **Scalable Memory:** By using a Postgres database for memory instead of temporary session memory, this agent can handle thousands of users and build long-term context.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![AI Chatbot Workflow (n8n, OpenAI, Supabase).png](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/AI%20Chatbot%20Workflow%20(n8n,%20OpenAI,%20Supabase).png?raw=true)

**Workflow Code File**

[Click here for the workflow code (AI Chatbot Workflow (n8n, OpenAI, Supabase).json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/AI%20Chatbot%20Workflow%20(n8n%2C%20OpenAI%2C%20Supabase).json)

### 🧠 Challenges & Learnings
The most powerful automations are not just smart, they are robust. The key learning here was integrating **Supabase** as an all-in-one database and vector store, which is a highly scalable alternative to other tools. Combining this with **persistent Postgres memory** creates an enterprise-ready AI assistant that is both intelligent (RAG) and stateful (remembers conversations).


---

## Project 10: AI Real Estate Assistant (RAG on Structured Excel Data)

### 📝 Project Overview
This project is a powerful AI assistant built for the **real estate industry**, demonstrating how to build a RAG agent on structured business data, not just simple text files.

This agent acts as a 24/7 virtual property expert. It answers specific user questions about property listings (e.g., "How many bedrooms?", "What is the price?") by retrieving facts from a **Supabase Vector Store**.

What makes this project unique is its data ingestion pipeline: it automatically "learns" from **structured Excel (XLS) files** added to Google Drive. It uses a **custom JavaScript node** to properly format each row of data before embedding it, ensuring the AI can understand and retrieve complex property details accurately.

### 🛠️ Tools Used
* **n8n:** The central automation platform.
* **Google Drive Trigger:** To automatically detect and ingest new property listing files.
* **Extract from File:** To read data directly from Excel (XLS) files.
* **Code in JavaScript:** To iterate over Excel rows, clean, and format the structured data for the AI.
* **Supabase Vector Store:** The vector database for both storing property data and RAG retrieval.
* **OpenAI:** Used for generating embeddings and powering the chat model.
* **Simple Memory:** To maintain conversational context.

### ✨ Key Features
* **RAG on Structured Data:** Moves beyond basic PDFs to handle structured Excel data, which is how most businesses store their information.
* **Custom Data Transformation:** Uses **JavaScript** to ensure data is clean and perfectly formatted before AI ingestion, guaranteeing high-quality answers.
* **High-Accuracy Answers:** The agent provides fact-based answers about properties by retrieving data directly from the Supabase vector store.
* **Automated Knowledge Updates:** The agent's knowledge base expands automatically as new property listing files are added to Google Drive.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![AI Real Estate Chatbot Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-real-estate-rag-agent-screenshot.png?raw=true)

**Workflow Code File**

[Click here for the workflow code (ai-real-estate-rag-agent.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-real-estate-rag-agent-json.json)

### 🧠 Challenges & Learnings
The most interesting challenge was handling *structured data* from an Excel file, not just simple text. This required using a custom JavaScript node to iterate over each property listing and format it into clean, embeddable text. This proves the RAG pipeline can be adapted for any business data, not just PDFs.


---

## Project 11: AI-Powered Business Dashboard (n8n + Google Sheets + Lovable)

### 📝 Project Overview
This project is a powerful, custom-built internal tool that allows a business manager to run their entire operation from a single, intelligent chat interface. It combines a **Lovable** dashboard (frontend), a **Google Sheet** (database), and an **n8n AI Agent** (backend).

A manager can type natural language commands (e.g., "Update Fernanda's budget" or "Send Martin an email") into the dashboard chat. The n8n agent receives this via a webhook, understands the command, uses its "tools" to perform the action (like updating the Google Sheet or sending a Gmail), and then confirms the task is complete, all within the chat.

### 🛠️ Tools Used
* **n8n:** The central automation "brain" that hosts the AI Agent and manages the logic.
* **Lovable.dev:** Used to create the beautiful, real-time analytics dashboard and chat interface.
* **Google Sheets:** Acts as the live database, storing all client and project data.
* **OpenAI Chat Model:** The AI model that understands user commands and decides which tool to use.
* **Gmail Node:** Used as a tool by the agent to send emails directly from the chat interface.
* **Webhook:** The real-time connection between the Lovable chatbot and the n8n agent.

### ✨ Key Features
* **AI-Powered Dashboard:** The agent turns a static dashboard into an interactive "operating system."
* **Natural Language Commands:** The manager doesn't need to know n8n or Google Sheets; they just need to chat. [cite_start]The agent (with its clear system prompt ) does the rest.
* **Multi-Tool Capability:** The agent can intelligently choose between reading data, updating data, or sending emails, all from one command.
* **Real-time Sync:** Any changes made by the agent in the Google Sheet are instantly reflected on the Lovable dashboard.

### 🖼️ Workflow Visuals & Code

**(Optional) Frontend Dashboard by Lovable**
![Headshot Studio Dashboard UI](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-business_lovable-dashboard-ui.png?raw=true)

**n8n Workflow (The Backend "Brain")**
![AI Business Dashboard Agent Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-business-dashboard-agent-screenshot.png?raw=true)

**n8n Workflow Code File**
[Click here for the workflow code (ai-business-dashboard-agent.json)](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/ai-business-dashboard-agent.json)

### 🧠 Challenges & Learnings
The most powerful part of this project was creating a seamless loop between a user-friendly frontend (Lovable) and a powerful backend (n8n). [cite_start]The key was designing a clear system prompt  and reliable tools (like `Get Rows` and `Update Rows`) that allow the AI to safely and accurately manage a live database (Google Sheets) simply through chat.
