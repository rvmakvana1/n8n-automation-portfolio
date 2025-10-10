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
![NSE Live Option Chain Workflow Screenshot](./NSE%20DATA.png)
* [**n8n Workflow Code (NSE DATA AUTOMATION.json)**](./NSE%20DATA%20AUTOMATION.json)
