📄 AI Document Summarizer & Knowledge Base Builder

AI-powered document processing pipeline built with n8n + Mistral OCR + OpenAI + Google Sheets

Automatically transform raw business documents into structured, searchable intelligence in seconds.

🚀 Overview

Business teams receive dozens of documents weekly:

Supplier catalogs

Market research reports

Competitor analysis

Product specifications

Most of these files sit unread in Google Drive.

This workflow automatically:

Detects new documents

Extracts text using OCR

Summarizes and categorizes using AI

Stores structured insights in Google Sheets

Logs errors gracefully

Drop a file → Get structured intelligence.

🧠 Problem Statement

For Luxe Scents (B2B perfume brand):

⏳ 30–45 minutes to manually read one supplier document

📄 10+ documents weekly

🕒 7+ hours wasted per week

❌ No centralized searchable knowledge base

Manual document processing was slowing procurement decisions.

⚡ Solution Architecture
🔁 Workflow Overview

New File Uploaded to Google Drive
↓
Google Drive Trigger (n8n)
↓
Mistral OCR (Text Extraction)
↓
OpenAI GPT-4o (Summarization & Categorization)
↓
Structured Parsing
↓
Google Sheets Knowledge Base
↓
Error Logging (if needed)

🛠️ Tech Stack

n8n – Workflow automation engine

Mistral OCR API – Document text extraction

OpenAI GPT-4o – AI summarization & structuring

Google Drive API – File trigger & download

Google Sheets API – Knowledge base storage

📊 AI Output Structure

Each document is converted into structured JSON:

{
  "title": "Arabian Oud & Co Product Catalog 2026",
  "document_type": "supplier_catalog",
  "one_line_summary": "2026 product offerings and terms from Arabian Oud & Co.",
  "key_takeaways": "Rose Oud Concentrate $45/100ml MOQ 50 | Amber Musk Blend $38/100ml MOQ 100",
  "action_items": "Review product offerings | Contact sales@arabianoud.com",
  "relevant_to": "procurement",
  "urgency": "read_this_week"
}
🏷️ Urgency Labels - Label Meaning
🔥 read_now	Time-sensitive
⚡ read_this_week	Important
📦 archive	Reference only
📁 Supported File Types

✅ PDF

✅ Google Docs

✅ Word (.docx)

✅ Plain Text (.txt)

✅ Images with text (OCR)

📊 Google Sheets Knowledge Base Structure
Sheet 1: Knowledge Base

| File Name | Document Type | Title | One Line Summary | Key Takeaways | Action Items | Relevant To | Urgency | File ID | Processed At |

Sheet 2: Errors

| Error Message | File Name | Timestamp |

🧪 Sample Test Document

Example:

Supplier: Arabian Oud & Co
Location: Dubai, UAE
Product Catalog 2026:
- Rose Oud Concentrate – $45 per 100ml – MOQ 50
- Amber Musk Blend – $38 per 100ml – MOQ 100
Payment Terms: 30% advance, 70% on delivery
Lead Time: 3–4 weeks

Upload to Drive → Knowledge base updates automatically.

🛡️ Error Handling

Download failure → Logged to Errors sheet

OCR failure → Logged to Errors sheet

OpenAI parse failure → Fallback values used

All errors timestamped

System fails safely — never silently.

📈 Business Impact
Metric	Before	After
Time to read a document	30–45 mins	0 mins
Weekly document processing	7+ hours	0 hours
Searchability	None	Full Google Sheets search
Team visibility	Fragmented	Centralized
🏗️ Repository Structure
ai-document-summarizer-n8n/
│
├── README.md
├── workflow2_document_summarizer.json
└── sample_documents/
    ├── supplier-catalog.txt
    ├── market-research.txt
    └── competitor-analysis.txt
🚀 Setup Instructions
Prerequisites

n8n instance (Cloud or Self-hosted)

Mistral API key

OpenAI API key

Google account

Installation

Clone the repository:

git clone https://github.com/GS-Ganesh/ai-document-summarizer-n8n.git

Import Document Summarizer & Knowledge Base Builder.json into n8n

Create Google Drive folder:

Luxe Scents - Documents

Create Google Sheet:

Luxe Scents - Knowledge Base

Add 2 tabs:

Knowledge Base

Errors

Connect credentials:

Google Drive (Trigger + Download)

Google Sheets

Mistral API

OpenAI API

Activate workflow

Upload any document to Drive

🔮 Future Enhancements

🔔 Slack notifications for urgent documents

🏷️ Auto-tag supplier names

📩 Weekly digest email summary

🗂️ Notion integration

📊 Excel & CSV support

🎯 Use Cases

Procurement teams

Operations managers

Legal document review

Research teams

Vendor evaluation workflows

💡 Why This Project Matters

This project demonstrates:

End-to-end AI workflow automation

Multi-API integration

Structured AI output design

Production-level error handling

Real business impact

👨‍💻 Author

Built as part of an AI Automation Engineer portfolio.

If you found this useful:

⭐ Star the repository
🚀 Fork it
💬 Connect on LinkedIn - https://www.linkedin.com/in/ganesha-g-s-28b50337a/
