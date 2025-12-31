# Authentication Mechanism

Before using any CellPay API endpoints, authentication is required via **Basic Authentication** using a username and password. These credentials are provided by the CellPay team for both production and development environments. 

On the first login attempt, a JSON Web Token (JWT) is generated. This token must be included in all subsequent API requests for authentication purposes. 

**Access Token Generation**

**URL:** 
```bash
{base-url}/sdk/login 
```

**Method:** POST

**Headers:**
- `Content-Type: application/json` 
- `Authorization: Basic {Base64Encoded (username: password)}` 

:::note
- Username: Access information provided by the Cellpay Team. 
- Password: Access information provided by the Cellpay Team.
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