# n8n Automation Projects Repository

## 📌 Overview
This repository is a **central hub for automation projects built with n8n**.

Here you will find multiple **real-world workflows** focused on:
- Business process automation
- API integrations
- AI-powered automations
- Event-driven pipelines
- Productivity and operational efficiency

Each project in this repository represents a **practical use case**, designed to reflect scenarios commonly found in companies and production environments.

---

## 🎯 Purpose of This Repository
The main goals of this repository are to:

- Demonstrate hands-on experience with **n8n**
- Showcase **automation design skills**
- Apply **AI and LLMs** in real workflows
- Practice **clean project organization**
- Serve as a **professional portfolio** for recruiters and technical teams

This is not a collection of toy examples — each project aims to solve a **real problem**.

---

## 🧠 What Recruiters Will Find Here
- Modular and well-organized automation projects
- Clear documentation for each workflow
- Secure handling of credentials (no secrets in GitHub)
- Docker-based local setup
- Scalable and maintainable automation patterns
- Practical use of AI in automation contexts

---

## 📂 Repository Structure
```
n8n-source/
├── projects/
│   ├── gmail-auto-reply-llm/
│   │   ├── gmail-auto-reply-llm.json
│   │   └── README.md
|   ├── refund-guard-ai/
|   |   ├── refund_guard_ai.json
|   |   └── README.md
|   ├── invoice-ai/
|   |   ├── invoice-ai.json
|   |   └── README.md
|   └── agentic-customer-service/
|       ├── agente_principal.json
|       ├── agente_financeiro.json
|       ├── agente_suporte.json
|       ├── agente_sucesso_cliente.json
|       └── README.md
├── docker-compose.yml
├── .env.example
├── .gitignore
└── README.md
```

Each project contains:
- One or more **n8n workflow JSON files**
- A dedicated **README** explaining the use case, logic, and setup

---

## ⚙️ Running the Environment Locally

### Prerequisites
- Docker
- Docker Compose

### Start n8n
```bash
docker compose up -d
```

Access the editor at:
```
http://localhost:5678
```

Workflows can be imported directly from each project folder.

---

## 🔐 Security & Best Practices
- No API keys or credentials are stored in this repository
- Environment variables are managed via `.env` files
- OAuth credentials are configured directly inside n8n
- `.env` files are excluded using `.gitignore`

---

## 🚀 Future Projects (Examples)
- AI-powered email classification
- Customer support automation with LLMs
- Data enrichment pipelines
- CRM integrations
- Human-in-the-loop approval workflows
- Monitoring and alerting automations

---

## 👨‍💻 Author

**José Geraldo do Espírito Santo Júnior**  
📍 Brazil  
🔗 LinkedIn: https://www.linkedin.com/in/josejunior13/

---

## 📄 License
This repository is intended for educational, demonstration, and portfolio purposes.
