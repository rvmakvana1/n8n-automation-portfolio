# My n8n Automation Portfolio

Welcome to my portfolio of AI and workflow automation projects. Here, I showcase various solutions I've built using tools like n8n, OpenAI, and more.

---

## Project 1: AI Recipe Generator & Airtable Automation

### 📝 Project Overview
This workflow acts as an intelligent recipe assistant. A user can provide the name of a dish via a simple chat interface, and the AI agent automatically generates a complete, detailed recipe and saves it neatly into an Airtable database. This project demonstrates the power of connecting AI with no-code platforms to automate content creation.

### 🛠️ Tools Used
* **n8n:** The core platform for building and running the workflow.
* **OpenAI (GPT Model):** The AI brain responsible for understanding the request and generating the recipe content.
* **Airtable:** The database where all the generated recipes are stored in a structured format.

### ✨ Key Features
* **Chat-based Interaction:** Easy to use, just type the name of the dish.
* **Structured AI Output:** The AI is configured to return the recipe in a precise JSON format, ensuring data consistency.
* **Automated Data Entry:** The workflow automatically creates a new record in Airtable for each recipe, eliminating manual data entry.
* **Data Transformation:** The workflow intelligently formats complex data (like lists of ingredients and instructions) into a simple text format suitable for Airtable fields.

### 🧠 Challenges & Learnings
One of the key challenges was ensuring the AI's output was consistently in the correct format for the database. I solved this by implementing n8n's native "JSON Mode" for the OpenAI model and creating a robust prompt with clear instructions. This taught me the importance of strict data validation in AI-powered automation.
![n8n Workflow Screenshot](https://raw.githubusercontent.com/rvmakvana1/n8n-automation-portfolio/refs/heads/main/Screenshot%202025-10-08%20213456.png)


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

## Project 7: AI Calling Agent with Custom Knowledge Base (RAG)

### 📝 Project Overview
This project showcases a voice-based AI Calling Agent that can have a real-time phone conversation with a user. The agent's core function is to answer specific questions by retrieving information from a **pre-built custom knowledge base** (stored in a Pinecone vector database). This workflow represents the "live" part of a full RAG system, handling the user interaction, information retrieval, and voice response. It's a powerful example of how to create automated, intelligent customer support or virtual assistant systems.

### 🛠️ Tools Used
* **n8n:** The core automation platform.
* **Webhook:** To receive real-time data from the calling platform.
* **Calling Platform (e.g., ElevenLabs):** Handles the voice-to-text and text-to-voice for the phone call.
* **Pinecone:** The vector database where the custom knowledge is searched.
* **OpenAI:** Used for generating human-like, conversational answers based on the retrieved information.

### ✨ Key Features
* **Real-time Call Handling:** The workflow is triggered instantly by a webhook when a user makes a phone call.
* **Smart Information Retrieval:** The agent takes the user's spoken question, searches the Pinecone knowledge base to find the most relevant facts from the custom documents.
* **Context-Aware Generation:** The AI model receives both the user's question and the retrieved information to generate a precise answer grounded in facts.
* **Voice Response:** The workflow sends the text answer back to the calling platform, which converts it to speech for the user to hear, completing the conversational loop.

### 🖼️ Workflow Visual & Code

**Workflow Screenshot**

![Calling Agent Screenshot](https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/Rag%20Calling%20Voice%20%20Agent.png?raw=true)

**Workflow Code File**

[Click here for the Calling Agent Workflow code (rag-calling-agent.json)]([https://github.com/rvmakvana1/n8n-automation-portfolio/blob/main/RAG%20Calling%20Agent.json)

### 🧠 Challenges & Learnings
The most significant challenge was maintaining conversation memory. Unlike a simple chat, a phone call requires the agent to remember the context of the entire conversation. The solution involves ensuring the calling platform sends a unique `call_id` with every webhook request and using that ID as the "Session ID" in n8n's `Simple Memory` node. This project was a major learning experience in bridging the gap between text-based AI and real-time voice interaction.
