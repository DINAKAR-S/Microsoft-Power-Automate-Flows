# AI-Driven Document Classification with Zoho Creator Integration

## Overview
This project demonstrates an enterprise-grade automation pipeline that classifies documents using AI, extracts structured data, and seamlessly pushes the results into Zoho Creator forms linked to deal records.

The solution combines Power Automate, Azure Document Intelligence, Azure OpenAI, and Zoho Creator APIs.

---

## Business Problem
Financial and legal workflows rely on multiple document types such as:
- Accountant’s Declarations
- Assets & Liabilities
- Valuations
- Loan Statements
- Tax and Trust Documents

Manual entry of extracted data into CRM or internal systems is slow and error-prone.

---

## Solution
This workflow:
1. Detects uploaded documents
2. Extracts text using OCR
3. Classifies document type using AI
4. Extracts document-specific fields
5. Retrieves Zoho OAuth access token
6. Pushes structured data into Zoho Creator
7. Links extracted data to a Deal record

---

## High-Level Architecture
File Upload → OCR → AI Classification → Switch Routing → Zoho OAuth → Zoho Creator Insert

---

## Technology Stack
- Power Automate
- Azure Document Intelligence (v4.x)
- Azure OpenAI (GPT-based classification)
- Zoho OAuth2
- Zoho Creator REST APIs

---

## Skills Demonstrated
- AI-based document classification
- Prompt engineering
- OAuth2 token management
- REST API integrations
- Enterprise workflow orchestration
- Zoho Creator form automation

---

## Security & Privacy
- OAuth tokens abstracted
- Sample schemas only
- No real credentials included

---

## Author
Dinakar S

