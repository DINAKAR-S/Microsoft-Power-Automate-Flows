# Document Processing Logic

This document explains the internal logic used in the Power Automate workflow.

---

## Step 1: Trigger
The workflow starts when a new file is created in a monitored folder.

Trigger:
- When a file is created (properties only)

---

## Step 2: File Retrieval
The document content is retrieved using its path so it can be passed to the OCR engine.

Action:
- Get file content using path

---

## Step 3: OCR Analysis
The document is sent to Azure Document Intelligence.

Action:
- Analyze Document (Prebuilt / Custom Model)

Extracted fields include:
- Full Name
- Document Number
- Date of Birth
- Expiry Date

---

## Step 4: JSON Parsing
OCR results are returned as JSON and parsed to extract individual fields.

Actions:
- Parse JSON
- Initialize Variables

---

## Step 5: Data Normalization
The following transformations are applied:
- Split full name into first, middle, last
- Standardize date formats
- Handle missing fields gracefully

---

## Step 6: Document Type Routing
A Switch condition determines the document type:
- Passport
- Driver License
- Other IDs

Each case applies document-specific logic and storage mapping.

---

## Step 7: Data Storage
Extracted values are inserted into Google Sheets for reporting and auditing.

Action:
- Add a row into a table

---

## Step 8: Notifications
Once processing is complete:
- Email notification is sent
- Microsoft Teams message is posted

Messages include:
- File name
- Detected name
- Processing status

---

## Step 9: Metadata Update
Document metadata is updated to reflect processing completion.

Action:
- Update file properties
