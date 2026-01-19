# Architecture Overview

This workflow uses a multi-layer enterprise automation architecture.

---

## Layers

### 1. Ingestion
- SharePoint / Folder-based document intake
- Deal name and ID captured

### 2. OCR Layer
- Azure Document Intelligence extracts raw text

### 3. AI Classification
- Azure OpenAI determines document type
- Extracts relevant fields only

### 4. Orchestration
- Power Automate Switch routes per document type

### 5. Zoho Integration
- OAuth2 access token retrieved
- Data pushed to Zoho Creator forms
- Records linked to Deal ID

---

## Design Principles
- Modular per document type
- Scalable switch-based routing
- Clean API separation
- Enterprise-grade error isolation
