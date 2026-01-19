# AI-Driven Multi-Document Classification & Field Extraction Pipeline

## Overview
This project demonstrates a highly scalable, AI-powered document processing pipeline built using Power Automate, Azure Document Intelligence, and Azure OpenAI.

The workflow automatically classifies multiple document types and extracts document-specific fields using a hybrid OCR + LLM-based approach.

It supports both identity documents and complex financial/legal documents.

---

## Supported Document Types
- Passport
- Driver License
- Property Title
- Certificate of Currency
- Accountant’s Declaration
- Assets & Liabilities Statement

Each document type follows a dedicated extraction and storage path.

---

## Business Problem
Organizations receive a wide variety of documents with different structures:
- Identity documents
- Financial statements
- Legal property records
- Insurance certificates

Traditional OCR alone is not enough to classify and normalize such data reliably.

---

## Solution Approach
This solution combines:
- OCR for text extraction
- LLM-based classification and field mapping
- Rule-based routing using Power Automate

---

## High-Level Flow
1. File upload triggers the workflow
2. OCR extracts raw document text
3. AI model classifies document type
4. Relevant fields are extracted dynamically
5. Switch logic routes to document-specific processors
6. Structured data stored in tables
7. Processing confirmation sent to users

---

## Architecture Components
- Power Automate
- Azure Document Intelligence (v4.x API)
- Azure OpenAI (GPT-based classification)
- Spreadsheet-based structured storage
- Email & Microsoft Teams notifications

---

## Key Features
- Multi-document classification in a single flow
- AI-assisted dynamic field extraction
- Modular switch-based architecture
- Clean separation per document type
- Centralized parsing and normalization
- Audit-ready structured outputs

---

## Skills Demonstrated
- Advanced Power Automate design
- Azure OCR integration
- Prompt engineering for document AI
- JSON parsing at scale
- Switch-case orchestration patterns
- Enterprise document automation

---

## Security & Privacy
- All identifiers generalized
- Sample prompts and schemas only
- No credentials or real documents included

---

## Author
Dinakar S
