# Encrypted Request Structure

**URL:**
```base
{base-url}/sdk/paymentRequest
```

**Method:** POST 

**Request / Response:** JSON 

**Header:** Token 

```jsx title="Sample Request"
{
     "signature": "Base64EncodedSignature", 
    "secret_key": "Base64EncodedSecretKey", 
    "data": "Base64EncodedEncryptedPayload", 
    "client_id": "username" //for eg. 98XXXXXXXX 
}
```
:::note
client_id is your assigned CellPay merchant username. 
Each request must include a unique uniqueToken in the encrypted payload to prevent duplicate transactions. 
All fields (signature, secret_key, data) are Base64-encoded strings. 
:::