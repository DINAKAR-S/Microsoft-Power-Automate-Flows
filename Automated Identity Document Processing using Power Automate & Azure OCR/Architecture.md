# Architecture Overview

This project uses an event-driven automation architecture.

---

## Components
- Document Upload Folder
- Power Automate Workflow
- Azure Document Intelligence
- Google Sheets
- Email & Teams Notification Services

---

## Flow Description
1. User uploads a document
2. Workflow triggers automatically
3. OCR extracts structured fields
4. Data is normalized and validated
5. Results stored in spreadsheet
6. Notifications sent to user

---

## Design Principles
- Automation-first
- Scalable workflow design
- Clear separation of concerns
- Error handling and auditability
