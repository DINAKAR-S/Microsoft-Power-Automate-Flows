# Processing Logic

## Step 1: Trigger
Triggered when a new file is created in the monitored folder.

---

## Step 2: Variable Initialization
- DealName
- DealID

These variables ensure all extracted data is linked to the correct deal.

---

## Step 3: OCR
Azure Document Intelligence extracts raw document content.

---

## Step 4: AI Classification
Azure OpenAI:
- Classifies document type
- Extracts document-specific fields
- Returns structured JSON

---

## Step 5: Global Parsing
- Normalize AI response
- Prepare payload for downstream systems

---

## Step 6: Switch Routing
Each document type follows a dedicated processing branch.

---

## Step 7: Zoho Creator Integration
Extracted fields are sent to the appropriate Zoho Creator form.
