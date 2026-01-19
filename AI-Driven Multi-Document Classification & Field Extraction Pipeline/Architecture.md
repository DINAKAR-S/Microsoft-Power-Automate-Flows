# Architecture Overview

This workflow uses a hybrid AI + rules-based architecture.

---

## Core Layers

### 1. Ingestion Layer
- Monitors document upload location
- Captures metadata and file content

### 2. OCR Layer
- Azure Document Intelligence extracts raw text
- Supports both prebuilt and custom models

### 3. AI Classification Layer
- Azure OpenAI classifies document type
- Extracts only relevant fields per document

### 4. Orchestration Layer
- Power Automate Switch routes processing
- Each case handles a specific document type

### 5. Storage & Notification Layer
- Structured data stored in tables
- Email and Teams notifications sent

---

## Design Principles
- Scalable document onboarding
- Minimal hardcoding
- AI-first extraction strategy
- Enterprise-grade error isolation
