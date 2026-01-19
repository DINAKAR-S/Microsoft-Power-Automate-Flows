# Zoho Creator Integration

## OAuth Token Retrieval
Access token is generated using a refresh token.

Endpoint:
https://accounts.zoho.com.au/oauth/v2/token

Parameters:
- refresh_token
- client_id
- client_secret
- grant_type=refresh_token

---

## Token Parsing
The access token is retrieved using:

body('Parse_JSON_Zoho_integration')?['access_token']

---

## Data Insertion
Data is posted to Zoho Creator using REST API:

POST:
{api_domain}/creator/v2.1/data/{account}/{app}/{form}

Headers:
- Authorization: Zoho-oauthtoken {access_token}
- Content-Type: application/json

---

## Record Linking
Deal Name and Deal ID are passed to ensure relational integrity.
