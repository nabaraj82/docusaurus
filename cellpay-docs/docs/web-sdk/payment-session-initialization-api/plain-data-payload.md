# Plain Data Payload (Before Encryption)

```jsx title="Sample Request"
{ 
    "amount": "4000.00", 
    "description": "Payment for Merchant", 
    "redirectUrl": "https://merchant.cellpay.com", 
    "uniqueToken": "765868", 
    "memberId": "memberId",//will be provided by CELLPAY  
    "productCode": "P003" 
} 
```

:::note
The uniqueToken must be unique for every payment request sent to CellPay; otherwise, the transaction will not be initiated.
:::