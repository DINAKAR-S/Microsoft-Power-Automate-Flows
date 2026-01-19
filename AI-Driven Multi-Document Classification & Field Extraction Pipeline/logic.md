# Document Routing & Extraction Logic

## Global Processing
- OCR output is normalized
- AI model determines document type
- JSON response parsed centrally

---

## Switch-Based Routing
Each document type has its own processing branch:

- PASS → Passport fields
- DRIV → Driver License fields
- PRPT → Property Title fields
- COCU → Certificate of Currency fields
- ACDE → Accountant Declaration fields
- ASLI → Assets & Liabilities fields

---

## Benefits
- Easy to add new document types
- Independent error handling per case
- Clear ownership of extraction logic
****
