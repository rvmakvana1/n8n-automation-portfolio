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
