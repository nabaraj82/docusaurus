# Status Code

The CellPay API follows standard HTTP status code conventions to indicate the success or failure of API requests. Alongside HTTP status codes, CellPay may also return internal error codes for more specific validation or business logic errors. This helps developers identify, troubleshoot, and handle errors appropriately in their applications. 

| **Error Status Code** | **Description** |
|----------------------|-----------------|
| `ES201`              | Missing payload |
| `ES110`              | Signature missing |
| `ES105`              | Invalid token signature |
| `ES104`              | Invalid payload signature |
| `ES403`              | Transaction not found |
| `ES101`              | Client detail invalid |
| `ES107`              | Client not registered |
| `ES999`              | Need to communicate with CellPay team |
