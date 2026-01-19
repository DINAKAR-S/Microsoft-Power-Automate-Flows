# Microsoft-Power-Automate

# Automated Identity Document Processing using Power Automate & Azure OCR

## Overview
This project demonstrates an enterprise-grade document automation workflow that automatically processes identity documents such as passports and driver licenses.

The solution uses Power Automate integrated with Azure Document Intelligence to extract structured information from uploaded documents, store the extracted data in Google Sheets, and notify users via Email and Microsoft Teams.

This project is designed as a portfolio-safe representation of real-world automation work.

---

## Business Problem
Manual processing of identity documents is slow, error-prone, and difficult to scale.  
Organizations require a reliable system to:
- Extract key fields automatically
- Store structured data for reporting
- Notify stakeholders upon completion

---

## Solution Summary
The workflow performs the following steps:
1. Detects new document uploads
2. Extracts text and fields using OCR
3. Classifies document type
4. Normalizes extracted data
5. Stores results in Google Sheets
6. Sends confirmation notifications

---

## Workflow Architecture
Trigger → OCR → Parsing → Classification → Storage → Notification

Refer to the screenshots folder for the complete Power Automate flow.

---

## Key Features
- Fully automated document intake
- OCR-based data extraction
- Switch-based document classification
- Structured data storage
- Email and Teams notifications
- Error handling and logging

---

## Technology Stack
- Power Automate
- Azure Document Intelligence (Prebuilt / Custom Models)
- Google Sheets
- Microsoft Teams
- Outlook Email

---

## Skills Demonstrated
- Workflow automation
- OCR integration
- JSON parsing and normalization
- Conditional logic and switch cases
- Enterprise data handling
- Notification systems
- Audit and logging design

---

## Security & Privacy
- No real documents or credentials included
- Company-specific identifiers removed
- Sample data used for demonstration only

---

## Use Cases
- Identity verification automation
- KYC document processing
- Back-office document digitization
- Compliance data extraction

---

## Author
Dinakar S
