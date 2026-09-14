# ADK Project - Cymbal Travel AI Agents

This repository contains the prototype and production-ready agentic workflows built using Google's **Agent Development Kit (ADK)** for **Cymbal Travel**. 

## Project Structure
## Project Structure

```text
adk_project/
├── my_google_search_agent/       # Travel Scout Agent
│   ├── .env                      # Environment configuration
│   └── agent.py                  # Agent definition with Google Search tool
│
├── geo_validator/                # Destination Verifier Agent
│   ├── .env                      # Environment configuration
│   └── agent.py                  # Agent definition with Pydantic output schema
│
├── llm_auditor/                  # Brochure Auditor Multi-Agent Pipeline
│   ├── .env                      # Environment configuration
│   └── agent.py                  # Critic and Reviser sequential workflow
│
├── requirements.txt              # Project dependencies
└── README.md                     # Project documentation

The project is organized into three primary agent components:

1. **`my_google_search_agent/` (Travel Scout)**
   - **Purpose:** Scours the web for real-time travel updates, event information, and general tourism queries.
   - **Features:** Integrated with the `google_search` tool for grounding responses in real-time search results.

2. **`geo_validator/` (Destination Verifier)**
   - **Purpose:** Validates destination data and ensures precise, structured outputs.
   - **Features:** Enforces strict JSON schemas using Pydantic (`CountryCapital`) models and disabled transfers to keep the agent focused.

3. **`llm_auditor/` (Brochure Auditor)**
   - **Purpose:** A sequential multi-agent pipeline designed to audit marketing claims.
   - **Features:** Comprises a **Critic Agent** (fact-checks claims against the web) and a **Reviser Agent** (automatically corrects and rewrites inaccurate text).

---

## Prerequisites

- Python 3.10+
- Google Cloud SDK (`gcloud`)
- Agent Development Kit (`google-adk`)

---

## Setup & Installation

1. **Clone the repository:**
2. export PATH=$PATH:"${HOME}/.local/bin"
python3 -m pip install google-adk
pip install -r requirements.txt

gcloud auth application-default login

GOOGLE_GENAI_USE_ENTERPRISE=true
GOOGLE_CLOUD_PROJECT=your-project-id
GOOGLE_CLOUD_LOCATION=global
MODEL=gemini-3.5-flash

adk web --allow_origins "regex:https://.*\.cloudshell\.dev"


Open http://127.0.0.1:8000 in your browser to interact with the agents.

adk run my_google_search_agent

python3 geo_validator/agent.py
   ```bash
   git clone [https://github.com/anuruddh-sharma71/ADK_PROJECT.git](https://github.com/anuruddh-sharma71/ADK_PROJECT.git)
   cd ADK_PROJECT
