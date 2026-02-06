# Agentic Customer Service Platform (n8n + LLMs)

## 📌 Overview
This project implements an **Agentic, Multi-Agent Customer Service Platform** using **n8n** and **Large Language Models (LLMs)**.

The system is designed to handle customer conversations in a **financial services context**, routing each user message to the correct specialist agent based on intent, while keeping business logic **controlled, auditable, and production-ready**.

Instead of relying on a single AI to do everything, this architecture follows a **multi-agent orchestration pattern**, where each agent has a **clear responsibility and strict scope of action**.

---

## 🧠 Architectural Concept
This project follows the **Agent Router + Specialist Agents** pattern:

- A **Principal Agent (Router)** classifies customer intent
- Specialized agents handle specific domains
- The router remains invisible to the end user
- Each agent operates under strict rules and boundaries

This approach improves:
- Reliability
- Compliance
- Maintainability
- User experience

---

## 🤖 Agents in This System

### 1️⃣ Principal Agent (Conversation Router)
**Role:** Invisible dispatcher

**Responsibilities:**
- Receive user messages from Telegram
- Classify customer intent
- Route the message to the correct specialist agent
- Return the specialist’s response verbatim to the user

**Key Design Rules:**
- Never solves problems directly (except greetings)
- Never explains internal routing logic
- Ensures the customer feels immediately assisted by a specialist

---

### 2️⃣ Financial Agent
**Role:** Billing and payment specialist

**Responsibilities:**
- Handle payment status inquiries
- Provide invoice and second-copy payment links
- Validate customer data using Google Sheets as the single source of truth

**Key Constraints:**
- Never invent financial information
- Uses tools (Google Sheets) for all validations
- Escalates out-of-scope topics back to the router

---

### 3️⃣ Technical Support Agent
**Role:** Financial education and technical explanations

**Responsibilities:**
- Explain financial concepts (CDB, Selic, FIIs, Treasury, etc.)
- Educate users without providing personalized investment advice

**Compliance Rules:**
- No investment recommendations
- Redirects personalized advice requests to Customer Success

---

### 4️⃣ Customer Success Agent
**Role:** Relationship management and scheduling

**Responsibilities:**
- Qualify customer intent before scheduling
- Schedule meetings with senior advisors
- Create Google Calendar events with Google Meet links
- Confirm appointments with professional messaging

This agent automates high-touch processes while preserving a premium experience.

---

## 🔄 How the System Works (Flow)

1. Customer sends a message (text or voice) via Telegram  
2. Voice messages are transcribed automatically  
3. The Principal Agent classifies intent  
4. The message is routed to the appropriate specialist agent  
5. The specialist agent processes the request using tools if needed  
6. The response is returned directly to the customer  

At no point does the user see internal routing or system messages.

---

## 🛠️ Tech Stack
- **n8n** – Workflow automation and orchestration
- **Docker / Docker Compose**
- **Google Gemini (LLM)**
- **Telegram Bot API**
- **Google Sheets API (OAuth2)**
- **Google Calendar API**
- **JavaScript (n8n expressions & code)**

---

## 🔐 Security & Best Practices
- No credentials stored in the repository
- OAuth2 used for Google services
- Deterministic logic for business-critical decisions
- Clear agent boundaries to prevent hallucinations
- Reset mechanism to avoid out-of-scope responses

---

## 📂 Project Structure
```
agentic-customer-service/
├── agente_principal.json
├── agente_financeiro.json
├── agente_suporte.json
├── agente_sucesso_cliente.json
└── README.md
```

---

## 📈 Possible Enhancements
- Centralized logging and analytics
- SLA-based escalation timers
- Human-in-the-loop approval flows
- Rate limiting and abuse prevention
- CRM integration
- Multi-language support

---

## 👨‍💻 Author

**José Geraldo do Espírito Santo Júnior**  
📍 Brazil  
🔗 LinkedIn: https://www.linkedin.com/in/josejunior13/

---

## 📄 License
This project is intended for **educational, demonstration, and portfolio purposes**.
