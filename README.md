# Gmail-to-Airtable-Slack-Automation

This project is an end-to-end **AI Support Agent** built in **n8n**. It is designed to fully automate the triage, analysis, and initial processing of inbound support tickets from a Gmail inbox.

The system continuously monitors a support email address, uses an AI agent to analyze and prioritize new messages, logs the structured data into an Airtable database, and sends priority-based notifications to a Slack channel.

---

## Key Features

*   **Real-Time Email Processing**: A **Gmail Trigger** monitors a support inbox in real-time, initiating the workflow the moment a new support request arrives.
*   **Intelligent AI Triage Agent**: A **Google Gemini** node acts as the core "brain." It analyzes the email's subject and body to:
    *   Determine the **Priority** (High, Medium, Low) based on custom rules.
    *   Assign a **Category** (e.g., "Technical Bug," "Billing").
    *   Generate a concise, natural-language **Summary** of the user's problem.
*   **Structured Data Logging**: The workflow takes the structured JSON output from the AI, cleans it, and logs it as a new, perfectly organized record in an **Airtable** base, which acts as the central support ticket dashboard.
*   **Priority-Based Alerting System**: A **Switch** node intelligently routes the workflow down different paths based on the AI-assigned priority. Each path is connected to a dedicated **Slack** node that sends a customized alert to the support channel and send text to signal the urgency of the ticket (e.g., 🚨 for High, ⚠️ for Medium).

---

## Tech Stack

*   **Automation Platform**: n8n
*   **Email Integration**: Gmail API
*   **AI Engine**: Google Gemini API 
*   **Data Logging**: Airtable
*   **Notifications**: Slack 
*   **Data Transformation**: JavaScript

---

## Workflow Overview

The entire system is orchestrated via a single, robust n8n workflow.

![Workflow Diagram](https://github.com/Muneeb20019/Gmail-to-Airtable-Slack-Automation/blob/main/Gmail%20bot.png?raw=true)

---

## Setup & Configuration

1.  **Import Workflow**: Import the `workflow.json` from this repository into your n8n instance.
2.  **Configure Credentials**: Add credentials for Gmail, Google Gemini (or OpenAI), Airtable, and Slack within n8n.
3.  **Update Node Endpoints**:
    *   In the `Gmail Trigger`, ensure it is connected to the correct support inbox.
    *   In the `Log Ticket in Airtable` node, update the Base ID and Table ID to point to your Airtable.
    *   In all three `Slack` nodes, update the destination channel to your desired support channel.
4.  **Activate Workflow**: Turn the workflow on to begin real-time monitoring.

---

## Author

- **Muneeb Ali Khan**
  - [LinkedIn] (https://www.linkedin.com/in/muneeb-ali-khan-2a1675365)
