# Overview

This API initializes a payment session with CellPay. 

The client must send an encrypted payload, an encrypted AES key, and a digital signature to ensure security and data integrity. 

## Base URL:
```bash
{base-url}/sdk/paymentRequest 
```

**Request / Response:** JSON 

**Header:** Token 

## Request Parameters
:::info Request Parameters
| Field        | Type   | Required | Description                                                        |
|--------------|--------|----------|--------------------------------------------------------------------|
| productCode  | String | Yes      | Product code for transaction type.                                 |
| uniqueToken  | String | Yes      | Unique token, max 20 characters.                                   |
| amount       | String | Yes      | Transaction amount ≤ 99999999.99.                                  |
| memberId     | String | Yes      | Provided by CellPay.                                               |
| redirectUrl  | String | Yes      | Redirect destination after transaction, max 100 characters.       |
| description  | String | Yes      | Transaction description, max 50 characters.                        |
:::

