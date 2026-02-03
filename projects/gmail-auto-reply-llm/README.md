# Gmail Auto Reply with AI (n8n Workflow)

## 📌 Overview
This project implements an **AI-powered email automation** using **n8n**, **Gmail**, and a **Large Language Model (LLM)**.

The workflow listens for incoming emails, evaluates whether they are relevant, generates a contextual response using AI, replies automatically via Gmail, and logs every interaction for auditability and monitoring.

This project was designed as a **real-world automation use case**, following production-oriented best practices.

---

## 🚀 What This Workflow Does
- Listens for new incoming Gmail messages
- Restricts execution to authorized test email addresses
- Filters messages based on business intent (regex-based)
- Generates intelligent replies using an LLM
- Replies directly within the original Gmail thread
- Logs all interactions to Google Sheets

---

## 🧠 Why This Project Matters
This automation demonstrates practical skills that companies look for, including:
- Applied AI (not just model usage)
- Event-driven automation
- API integrations with OAuth2
- Prompt engineering
- Observability and logging
- Secure handling of credentials

---

## 🛠️ Tech Stack
- **n8n** – Workflow automation
- **Docker & Docker Compose**
- **Gmail API (OAuth2)**
- **Google Gemini (LLM)**
- **Google Sheets API**
- **JavaScript expressions (n8n)**

---

## 📂 Project Structure
```
gmail-auto-reply-llm/
├── gmail-auto-reply-llm.json
└── README.md
```

---

## ⚙️ How the Workflow Works

### 1️⃣ Gmail Trigger
- Monitors incoming emails using polling
- Captures sender, subject, body, and thread information

---

### 2️⃣ Sender Restriction (Test Mode)
Only emails sent from a predefined test address are processed.
This prevents unintended replies during development and testing.

---

### 3️⃣ Intent Validation
A regex-based filter ensures that only emails related to:
- courses
- pricing
- enrollment
- training programs

are processed by the AI.

This reduces cost, noise, and risk.

---

### 4️⃣ AI Response Generation
- Uses an LLM with conversational memory (thread-based)
- Generates concise, professional, HTML-formatted responses
- Responds in the same language as the incoming email

---

### 5️⃣ Gmail Reply
- Replies directly to the original email thread
- Ensures proper message referencing and avoids loops

---

## 🧾 Logging & Observability (Key Feature)
Every successful interaction is logged to **Google Sheets**, including:

| Field | Description |
|-----|------------|
| timestamp | Execution date and time |
| from_email | Sender email address |
| thread_id | Gmail conversation thread |
| question | Original email content |
| ai_response | AI-generated reply |

### Why logging matters:
- Auditability
- Debugging
- Quality monitoring
- Cost and usage analysis

---

## 🔐 Security & Best Practices
- No credentials or API keys are stored in the repository
- `.env` files are excluded via `.gitignore`
- OAuth credentials are managed directly inside n8n
- Workflow is designed to avoid email loops and spam behavior

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

3. Import the workflow JSON:
- Workflows → Import → From File

4. Configure credentials (Gmail, Sheets, LLM)

---

## 📈 Possible Enhancements
- Human-in-the-loop approval
- Business-hour response control
- Artificial response delay
- Intent classification via AI
- Analytics dashboard (Sheets / Looker)
- Production mode using Gmail labels

---

## 👨‍💻 Author

**José Geraldo do Espírito Santo Júnior**  
📍 Brazil  
🔗 LinkedIn: https://www.linkedin.com/in/josejunior13/

---

## 📄 License
This project is intended for educational, demonstration, and portfolio purposes.
