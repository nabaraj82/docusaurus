# Transaction Status Inquiry

**URL:**

```base
{base-url}/sdk/transactions/75675/status
```

**Method:** GET

**Request / Response:** JSON

## Sample Response

```jsx title="For Success"
 {
    "id": 891,
    "txn_amount": "1500.50",
    "transactionDate": "2025-11-13",
    "cellpayTransactionId": "CEL1763023469590",
    "paymentType": "Mobile Wallet",
    "productCode": "PROD001",
    "uniqueId": "ABC123TOKEgxxlk3",
    "description": "Payment for order #123",
    "bookingId": "15e962bf-0d60-45d3-8fb2-1b3ca9",
    "transactionStatus": "PAID",
    "redirectUrl": "http://localhost:9090/transaction/receipt"
}
```

```jsx title="For Booked"
 { 
    "id": 889, 
    "txn_amount": "1500.50", 
    "transactionDate": "2025-11-13", 
    "cellpayTransactionId": null, 
    "paymentType": "Mobile Wallet", 
    "productCode": "PROD001", 
    "uniqueId": "ABC123TOKEgxxlk", 
    "description": "Payment for order #123", 
    "bookingId": "eb345a2a-e4e9-48e7-abc4-95f376", 
    "transactionStatus": "BOOKED", 
    "redirectUrl": "http://localhost:9090/transaction/receipt" 
} 
```

```jsx title="For Failed"
{ 
    "id": 882, 
    "txn_amount": "1500.50", 
    "transactionDate": "2025-11-13", 
    "cellpayTransactionId": null, 
    "paymentType": "Mobile Wallet", 
    "productCode": "PROD001", 
    "uniqueId": "ABC123TOKEq", 
    "description": "Payment for order #123", 
    "bookingId": "0bbe5a05-0f67-47b0-9226-657af6", 
    "transactionStatus": "FAILED", 
    "redirectUrl": "http://localhost:9090/transaction/receipt" 
} 
```
