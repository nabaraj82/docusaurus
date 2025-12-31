# SDK Payment Processing Architecture

```mermaid
sequenceDiagram
    participant Wallet as Wallet App / Website
    participant ClientApp as Client App
    participant Backend as Client Backend
    participant SDK as Wallet SDK

    Wallet->>ClientApp: User requests payment
    ClientApp->>Backend: Request access token
    Backend->>SDK: Send client_id & client_secret
    SDK-->>Backend: Access token

    Backend->>SDK: Request payment
    SDK->>SDK: Verify data

    ClientApp-->>Wallet: Redirect to login page
    Wallet->>SDK: Send username & password
    SDK->>SDK: Verify data

    ClientApp-->>Wallet: Redirect to select payment method
    Wallet->>SDK: Send payment method
    SDK->>SDK: Verify data

    ClientApp-->>Wallet: Redirect to confirm payment
    Wallet->>SDK: Send password
    SDK->>SDK: Verify data

    ClientApp-->>Wallet: Redirect to OTP page (if required)
    Wallet->>SDK: Send OTP
    SDK->>SDK: Verify data

    SDK-->>Backend: Redirect to provided URL
```

The CellPay Web SDK provides a secure, step-by-step payment workflow that integrates directly into a merchant’s web or backend system. This architecture ensures smooth, authenticated, and traceable transactions between the merchant application, the user, and the CellPay system. 
