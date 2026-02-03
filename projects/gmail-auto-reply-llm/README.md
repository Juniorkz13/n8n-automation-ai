# n8n AI Automation – Gmail Auto Reply with LLM

## 📌 Overview
This project demonstrates a **real-world AI-powered automation** built with **n8n**, integrating **Gmail** and a **Large Language Model (LLM)** to automatically receive emails, understand their content, and generate intelligent replies based on a custom prompt.

The goal of this project is to showcase **applied AI**, **workflow automation**, and **API integrations** in a way that mirrors professional, production-like environments used by companies.

---

## 🚀 What This Automation Does
- Listens for new incoming emails in Gmail
- Extracts and processes the email content
- Sends the content to a Large Language Model (LLM)
- Generates a contextual, prompt-based response
- Automatically replies to the sender via Gmail

---

## 🧠 Why This Project Matters
Recruiters and companies value engineers who can:
- Apply AI to solve real problems
- Integrate external services via APIs
- Build automated pipelines, not just models
- Think about scalability, cost, and reliability

This project demonstrates:
- **AI integration in automation**
- **Event-driven workflows**
- **Prompt engineering**
- **Secure credential management**
- **Low-code + code hybrid approach**

---

## 🛠️ Tech Stack
- **n8n** – Workflow automation (self-hosted via Docker)
- **Docker & Docker Compose**
- **Gmail API (OAuth2)**
- **Google Gemini (LLM)**
- **JavaScript (inside n8n Code nodes)**

---

## 📂 Project Structure
```
n8n-source/
├── gmail-auto-reply-llm/
│   ├── gmail-auto-reply-llm.json
│   └── README.md
├── docker-compose.yml
├── .env.example
├── .gitignore
└── README.md
```

---

## ⚙️ How to Run Locally

### 1️⃣ Prerequisites
- Docker
- Docker Compose
- Google Cloud Project with:
  - Gmail API enabled
  - OAuth2 credentials configured

---

### 2️⃣ Environment Setup
Clone the repository and create your environment file:

```bash
cp .env.example .env
```

Fill in required environment variables if needed.

---

### 3️⃣ Start n8n
```bash
docker compose up -d
```

Access n8n at:
```
http://localhost:5678
```

---

### 4️⃣ Import the Workflow
In n8n:
- Go to **Workflows**
- Click **Import → From File**
- Select `gmail-auto-reply-llm.json`

Reconnect credentials (OAuth is not exported for security reasons).

---

## 🔐 Security & Best Practices
- No credentials or API keys are stored in this repository
- `.env` files are ignored via `.gitignore`
- OAuth credentials are managed directly inside n8n
- Designed to avoid infinite email reply loops

---

## 📈 Possible Improvements
- Human-in-the-loop approval before sending replies
- Intent classification before response generation
- Response templates per category
- Logging replies to Google Sheets or a database
- Rate limiting and cost control
- Multi-language support

---

## 👨‍💻 Author

**José Geraldo do Espírito Santo Júnior**  
📍 Brazil  
🔗 LinkedIn: https://www.linkedin.com/in/josejunior13/

---

## 📄 License
This project is for educational and portfolio purposes.
