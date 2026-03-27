#  Autonomous AI Administrative Assistant (n8n + MCP + Google Workspace)

###  Project Overview
This project is a sophisticated, multi-workflow AI system designed to handle complex administrative tasks autonomously. Unlike standard linear automations, this system uses a **Model Context Protocol (MCP)** architecture. It allows an AI Agent to dynamically "decide" which tools to use—whether it’s checking a database, drafting an email, or managing a calendar—to fulfill a natural language request.

###  Architecture
The system operates through two interconnected n8n workflows:

1.  **The AI Agent (Client):** * Acts as the "brain" of the operation using **GPT-4o-mini**.
    * Features a **PostgreSQL Chat Memory** bridge, allowing the agent to remember past interactions and user preferences across different sessions.
    * Communicates with the MCP Server to execute specialized tasks.

2.  **The MCP Server (Tools):**
    * Serves as the "hands" of the agent, providing secure, structured access to external APIs.
    * Contains a suite of custom-defined tools for **Gmail, Google Sheets,** and **Google Calendar**.

###  Key Workflows & Features

####  Email & Database Management
The agent can read and write to **Google Sheets** to track leads, project statuses, or contact info. It can simultaneously draft or send **Gmail** messages based on the data it finds, ensuring that the database and communication remain perfectly in sync.

####  Intelligent Appointment Scheduling
The system handles the full lifecycle of meeting management:
* **Search**: Checks for existing conflicts in Google Calendar.
* **Create**: Books new appointments via natural language commands.
* **Update/Delete**: Reschedules or cancels events dynamically.

####  Persistent Memory
By utilizing a **PostgreSQL** backend for LangChain memory, the agent maintains context. If you tell the agent "Follow up with the person I added to the sheet yesterday," it has the historical context to identify the correct entry and take action.

###  Technical Stack
* **Automation Platform**: n8n (Version 1.7+ with MCP support)
* **LLM**: OpenAI GPT-4o-mini
* **Memory**: PostgreSQL (Vector/Chat Memory)
* **Protocol**: Model Context Protocol (MCP)
* **Integrations**: Google Workspace (Sheets, Gmail, Calendar)

###  Implementation Goal
I developed this project to demonstrate how AI can move beyond simple "triggers" and into the realm of **Agentic Workflows**, where the AI understands intent, accesses the necessary tools, and manages a professional ecosystem with minimal human oversight.
