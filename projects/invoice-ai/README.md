# InvoiceAI — Automated Invoice Processing Pipeline (n8n + LLMs)

## 📌 Overview
InvoiceAI is an **end-to-end automated invoice and receipt processing pipeline** built with **n8n** and **Large Language Models (LLMs)**.

The workflow continuously monitors an email inbox, detects PDF invoice attachments, extracts structured financial data using AI, classifies each document as **corporate or personal**, stores files in the correct Google Drive folders, and registers all data in a structured spreadsheet.

This project was designed as a **portfolio-grade automation**, following real-world backoffice, accounting, and finance automation patterns.

---

## 🚀 What This Project Does
- Monitors a Gmail inbox for incoming invoices and receipts
- Automatically downloads PDF attachments
- Processes multiple attachments per email safely
- Uses AI to extract structured data from documents
- Classifies expenses as **corporate** or **personal**
- Renames files following a standardized accounting convention
- Uploads documents to the correct Google Drive folders
- Registers all extracted data into Google Sheets

---

## 🧠 Key Design Principles
- **AI used only where it adds value** (OCR, semantic extraction, classification)
- **Deterministic workflow logic** for routing and storage
- **Strict JSON schema enforcement** to reduce AI hallucinations
- **Separation of concerns** between data extraction, classification, and persistence
- **Scalable pipeline design** capable of handling multiple documents per execution

---

## 🧩 How the Workflow Works

### 1️⃣ Email Intake (Gmail Trigger)
- Continuously polls a Gmail inbox
- Automatically downloads all attachments
- Filters out emails without attachments

---

### 2️⃣ Attachment Handling
- Splits binary attachments into individual items
- Processes each document independently using batch control
- Prevents concurrency and data mixing issues

---

### 3️⃣ AI-Powered Document Analysis
- Uses a Large Language Model to read invoice PDFs
- Extracts structured fields such as:
  - Invoice date
  - Supplier
  - Amount
  - Currency
  - Taxes
  - Invoice number
  - Category
  - Payment method
- Classifies documents as **corporate** or **personal**
- Generates a standardized file name

The AI is strictly instructed to:
- Never invent missing data
- Return `null` when information is not present
- Output **valid JSON only**

---

### 4️⃣ Document Classification & Storage
- Corporate invoices are uploaded to a dedicated Google Drive folder
- Personal receipts are stored in a separate folder
- This mirrors real-world accounting separation practices

---

### 5️⃣ Accounting Registration
- All extracted data is appended to a Google Sheets document
- Each row includes:
  - Financial metadata
  - Document classification
  - Direct link to the stored file
  - Originating email address

This creates a lightweight but effective accounting ledger.

---

## 🛠️ Tech Stack
- **n8n** – Workflow automation and orchestration
- **Docker / Docker Compose**
- **Google Gemini (LLM)**
- **Gmail API (OAuth2)**
- **Google Drive API**
- **Google Sheets API**
- **JavaScript (n8n expressions & parsing logic)**

---

## 🔐 Security & Best Practices
- No credentials stored in the repository
- OAuth2 used for all Google services
- Deterministic workflow logic for critical decisions
- Retry logic for AI processing failures
- Designed to be easily extended with validation rules and logging

---

## 📂 Project Structure
```
invoice-ai/
├── invoice-ai.json
└── README.md
```

---

## 📈 Possible Enhancements
- Manual review flow for low-confidence extractions
- Centralized error logging and monitoring
- ERP or accounting system integration
- Supplier whitelist and validation rules
- Cost and performance monitoring for AI usage
- Database-based storage instead of spreadsheets

---

## 👨‍💻 Author

**José Geraldo do Espírito Santo Júnior**  
📍 Brazil  
🔗 LinkedIn: https://www.linkedin.com/in/josejunior13/

---

## 📄 License
This project is intended for **educational, demonstration, and portfolio purposes**.
