# RefundGuard AI — Automated Refund Triage with LLMs (n8n Workflow)

## 📌 Overview
RefundGuard AI is an **AI-powered refund request triage system** built with **n8n**, **Large Language Models (LLMs)**, and **Google Workspace APIs**.

The workflow automatically processes refund requests submitted via a form, enriches customer data from Google Sheets, analyzes customer sentiment using AI, and routes each request based on deterministic business rules.

This project was designed as a **portfolio-grade, real-world automation**, following best practices used in production environments.

---

## 🚀 What This Workflow Does
- Receives refund requests through a webhook (form integration)
- Extracts structured data from unstructured form submissions using an LLM
- Performs **sentiment analysis** on customer comments
- Looks up customer data in Google Sheets (spend history, last purchase date)
- Applies deterministic business rules to classify the request
- Routes each case to the appropriate outcome:
  - Automatic approval
  - Automatic rejection
  - Escalation to finance (VIP customers)
  - Escalation to management (high-risk complaints)

---

## 🧠 Why This Project Matters
This workflow demonstrates skills that are highly valued in modern automation and AI-driven systems:

- Practical and controlled use of AI (LLMs used only where appropriate)
- Clear separation between AI logic and business rules
- Event-driven automation design
- Integration with external APIs using OAuth2
- Scalable and maintainable workflow architecture
- Real-world decision-making logic

Rather than delegating decisions to the LLM, **AI is used strictly for NLP tasks**, while business rules remain deterministic and auditable.

---

## 🛠️ Tech Stack
- **n8n** – Workflow automation platform
- **Docker & Docker Compose**
- **Google Gemini (LLM)**
- **Google Sheets API (OAuth2)**
- **Webhook-based integrations**
- **JavaScript (n8n Code node)**

---

## 📂 Project Structure
```
refundguard-ai/
├── refund_guard_ai.json
└── README.md
```

---

## ⚙️ How the Workflow Works

### 1️⃣ Webhook Intake
- Listens for POST requests from a form platform
- Receives customer name, email, selected product, and written feedback

---

### 2️⃣ AI-Powered Data Extraction & Sentiment Analysis
- Uses an LLM to:
  - Normalize and extract form fields
  - Classify customer sentiment as:
    - positive
    - neutral
    - negative
    - very_negative
- Returns structured JSON output only

---

### 3️⃣ Customer Data Enrichment
- Looks up the customer in Google Sheets using email as the unique key
- Retrieves:
  - Total amount spent
  - Date of last purchase

---

### 4️⃣ Deterministic Business Rules (Key Design Choice)
All decision logic is handled by a **JavaScript Code node**, not the LLM.

Rules include:
- Refund eligibility window (7 days)
- Customer lifetime value (VIP threshold)
- Complaint severity based on sentiment

This ensures:
- Predictable behavior
- Easier auditing
- Lower operational risk

---

### 5️⃣ Decision Routing
A single **Switch node** routes each request based on the computed action:
- Approve refund
- Deny refund
- Escalate to finance team
- Escalate to management

This keeps the workflow clean and scalable.

---

## 🔐 Security & Best Practices
- No credentials or API keys are stored in the repository
- OAuth credentials are managed directly inside n8n
- Business logic is deterministic and reviewable
- Webhook-based architecture supports access control extensions
- Workflow designed to be easily adapted for production

---

## 🧪 Local Execution
1. Start n8n using Docker:
```bash
docker compose up -d
```

2. Access n8n:
```
http://localhost:5678
```

3. Import the workflow:
- Workflows → Import → From File
- Select `refund_guard_ai.json`

4. Configure credentials:
- Google Sheets
- Google Gemini (LLM)

---

## 📈 Possible Enhancements
- Human-in-the-loop approval steps
- Persistent audit logging (Sheets or database)
- SLA-based escalation timers
- Dashboard and analytics layer
- Rate limiting and webhook authentication
- Multi-language sentiment analysis

---

## 👨‍💻 Author

**José Geraldo do Espírito Santo Júnior**  
📍 Brazil  
🔗 LinkedIn: https://www.linkedin.com/in/josejunior13/

---

## 📄 License
This project is intended for **educational, demonstration, and portfolio purposes**.
