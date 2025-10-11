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

[Click here to view the n8n workflow code (ai-feedback-sorter.json)]([यहाँ_अपनी_ai-feedback-sorter.json_फाइल_का_लिंक_डालें])

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
