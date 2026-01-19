# Zoho OAuth2 Authentication & Zoho Creator Record Integration

This document explains how the workflow securely authenticates with Zoho using OAuth2 and inserts extracted document data into a related Zoho Creator form.

---

## 1. Zoho OAuth2 – Access Token Generation

Zoho APIs require a short-lived **access token**, which is generated using a long-lived **refresh token**.

### Token Endpoint
```

[https://accounts.zoho.com.au/oauth/v2/token](https://accounts.zoho.com.au/oauth/v2/token)

```

### HTTP Method
```

POST

```

### Query Parameters
| Parameter | Description |
|--------|------------|
| refresh_token | Long-lived refresh token |
| client_id | Zoho OAuth client ID |
| client_secret | Zoho OAuth client secret |
| grant_type | refresh_token |

### Example Request
```

[https://accounts.zoho.com.au/oauth/v2/token](https://accounts.zoho.com.au/oauth/v2/token)
?refresh_token=REFRESH_TOKEN
&client_id=CLIENT_ID
&client_secret=CLIENT_SECRET
&grant_type=refresh_token

````

---

## 2. OAuth Response Schema

The response from Zoho OAuth follows this schema:

```json
{
  "type": "object",
  "properties": {
    "access_token": {
      "type": "string"
    },
    "refresh_token": {
      "type": "string"
    },
    "api_domain": {
      "type": "string"
    },
    "token_type": {
      "type": "string"
    },
    "expires_in": {
      "type": "integer"
    }
  }
}
````

---

## 3. Parsing OAuth Response in Power Automate

The OAuth response is parsed using **Parse JSON**.

### Access Token Reference

```text
body('Parse_JSON_Zoho_integration')?['access_token']
```

### API Domain Reference

```text
body('Parse_JSON_Zoho_integration')?['api_domain']
```

---

## 4. Zoho Creator API – Insert Record

After extracting document details using OCR and AI classification, the structured data is sent to Zoho Creator.

### Endpoint Format

```text
{api_domain}/creator/v2.1/data/{account}/{app}/{form}
```

### Example Endpoint

```text
@{body('Parse_JSON_Zoho_integration')?['api_domain']}
 /creator/v2.1/data/company/test/form/Doc_type_record
```

---

## 5. HTTP Request Configuration

### Method

```
POST
```

### Headers

```text
Authorization : Zoho-oauthtoken @{outputs('Compose_Zoho_integration')}
Content-Type  : application/json
```

---

## 6. Request Body (ACDE – Accountant’s Declaration Example)

```json
{
  "data": {
    "Borrower_names": "@{body('Parse_JSON_ACDE')['Fields']['Borrower name(s)']}",
    "Interest_Buffer": "@{body('Parse_JSON_ACDE')['Fields']['Interest buffer']}",
    "Loan_amount": "@{body('Parse_JSON_ACDE')['Fields']['Loan amount']}",
    "Deal_Name": "@{variables('DealName')}",
    "Deal_ID": "@{variables('ID')}",
  }
}
```

---

## 7. Key Design Notes

* OAuth access tokens are generated dynamically per run
* API domain is read from OAuth response (supports multi-region Zoho accounts)
* Deal Name and Deal ID ensure correct record linkage
* `coalesce()` prevents null failures for optional numeric fields
* Same pattern can be reused for other document types (ASLI, VALU, LOST, etc.)

---

## 8. Security Considerations

* Refresh token stored securely
* Access token never hardcoded
* No credentials exposed in repository
* Sample IDs used for portfolio demonstration only

---

## Summary

This integration enables:

* Secure Zoho authentication using OAuth2
* Dynamic API endpoint resolution
* Automated insertion of AI-extracted document data
* Clean linkage between documents and deal records

This approach supports scalable, enterprise-grade document automation.

```
