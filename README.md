# Internal Data SQL Agent



[![Live Demo](https://img.shields.io/badge/Live%20Demo-Streamlit-FF4B4B?style=for-the-badge)](https://databasesqlagent.streamlit.app/)



An intelligent, context-aware SQL Agent built to securely query and analyze internal company sales, product, and pricing data using natural language. 



## Overview

This agent translates natural language into syntactically correct PostgreSQL queries, executes them against a live cloud database, and synthesizes the data into human-readable insights. It features conversational memory to resolve complex pronouns and follow-up questions, and is wrapped in a strict security firewall to prevent prompt injection and block out-of-scope queries.


## Tech Stack

* **Frontend:** Streamlit

* **Orchestration:** LangChain (ReAct Agent Architecture)

* **LLM:** OpenAI (`gpt-4o-mini`)

* **Database:** PostgreSQL (Cloud-hosted via Neon)



## Key Features

* **Conversational Memory:** Retains context across the session to answer multi-step follow-up questions.

* **Security Firewall:** Custom Few-Shot routing mechanism intercepts malicious commands (e.g., `DROP TABLE`) and restricts the agent entirely to the internal data scope.

* **Self-Correcting Queries:** Uses the LangChain SQLToolkit to read schema errors and rewrite queries on the fly without user intervention.

* **Cloud-Native Architecture:** Connects to a remote PostgreSQL instance via SQLAlchemy connection URIs, fully decoupled from local storage.



## Local Setup

1. Clone the repository.

2. Create a virtual environment and install dependencies:

	```bash

	pip install -r requirements.txt

