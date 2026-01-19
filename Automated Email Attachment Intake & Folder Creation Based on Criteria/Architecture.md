# Architecture Overview

This workflow uses an event-driven intake architecture.

---

## Components
- Email Inbox
- Power Automate Flow
- Document Storage (SharePoint / OneDrive)

---

## Flow Design
1. Email arrives
2. Flow extracts metadata
3. Deal folder is created
4. Attachments saved automatically

---

## Design Principles
- Simple and reliable
- Minimal dependencies
- Easy to extend with OCR or classification flows
- Clean separation of intake vs processing
