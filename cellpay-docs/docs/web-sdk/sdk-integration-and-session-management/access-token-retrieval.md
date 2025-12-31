# Access Token Retrival (Login)

**URL:** 
```bash
{base-url}/sdk/login 
```

**Method:** POST

**Request / Response**: JSON 

:::info Authentication Fields
| Field    | Type | Required | Description                              |
|----------|------|----------|------------------------------------------|
| username | Text | Yes      | Username provided by CellPay.            |
| password | Text | Yes      | Password provided by CellPay (6 digits). |
:::


```jsx title="Sample Request"
{ 
    "username": " username", //for eg. 98XXXXXXXX 
    "password": "XXXXXX" //for eg. 123456 (provided by cellpay) 
} 
```
```jsx title="Sample Response"
{ 
    "status": true, 
    "sessionExpired": false, 
    "accessClient": "eyJhbGciOiJIUzI1NiJ9..." 
} 
```