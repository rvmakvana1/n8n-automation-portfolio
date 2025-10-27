# My n8n Automation Portfolio

Welcome to my portfolio of AI and workflow automation projects. Here, I showcase various solutions I've built using tools like n8n, OpenAI, and more.

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
