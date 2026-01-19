# Flow Logic Explanation

## Step 1: Email Trigger
Trigger:
- When a new email arrives (V3)

The flow activates whenever a new email is received.

---

## Step 2: Variable Initialization
A variable is initialized to store:
- Deal name or deal identifier
- Folder path reference

This allows consistent reuse throughout the flow.

---

## Step 3: Folder Creation
Action:
- Create new folder

A folder is created dynamically using the deal name to ensure:
- Clear separation of documents
- Easy retrieval later

---

## Step 4: Attachment Loop
Action:
- Apply to each (Attachments)

Processes all attachments in the email.

---

## Step 5: Attachment Retrieval
Action:
- Get attachment (V2)

Retrieves binary content for each attachment.

---

## Step 6: File Creation
Action:
- Create file

Saves each attachment into the newly created deal folder.

---

## Result
All documents from the email are:
- Stored in the correct location
- Properly grouped by deal
- Ready for downstream processing
