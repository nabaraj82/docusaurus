# SDK Payment Flow Overview

The CellPay Web SDK provides a secure, step-by-step payment workflow that integrates directly into a merchant’s web or backend system. This architecture ensures smooth, authenticated, and traceable transactions between the merchant application, the user, and the CellPay system. 

## Step 1: Initiating the Payment Request 

**Handled by:** Merchant Application 

The merchant’s backend sends a payment initiation request to CellPay via the /sdk/paymentRequest API. 

This request includes: 

- Encrypted transaction details (amount, reference ID redirect URL, etc.) 
- Encrypted AES key 
- Digital signature 

Once received, CellPay validates the request and starts a secure session for the user. 

## Step 2: User Login Prompt 

**Handled by:** CellPay SDK (Frontend) 

The user is redirected to CellPay’s **secure login page**, where they are prompted to enter their **CellPay username and password**. This ensures the user explicitly authorizes the payment from their account. 

Purpose: 

- Authenticate the user identity. 
- Prevent unauthorized payment attempts.

## Step 3: User Authentication 

**Handled by:** CellPay Backend  

The CellPay authentication server validates the user’s credentials. 

- On successful login, the user is authenticated and the session proceeds. 
- On failure, an appropriate error or retry prompt is displayed. 

Technical Validation: 

- Username and password verification via secure token exchange. 
- Session creation for the authenticated user. 

## Step 4: Payment Method Selection 

**Handled by:** CellPay Backend   

The selected payment method is validated in real time to ensure: 

- The wallet or bank account is active. 
- Sufficient balance or available limit exists. 
- The account has no restrictions or flags. 

If valid, the process moves forward to the confirmation step; otherwise, the user is notified to select an alternate method.

## Step 6: Payment Confirmation 

**Handled by:** User + CellPay Backend 

Before finalizing the transaction, the user must review payment details (amount, merchant name, and purpose) and re-enter their password to confirm authorization. 

This step adds a second layer of verification (Two-Factor Authentication - Password Re-entry).

Purpose: 

To prevent accidental or unauthorized transactions. 

## Step 7: OTP Verification (Conditional) 

**Handled by:** CellPay Backend & User 

For transactions exceeding **NPR 5,000**, an **OTP (One-Time Password)** is sent to the user’s registered mobile number.
The user must enter this OTP to complete the payment process. 
For transactions below **NPR 5,000**, this step is automatically bypassed

**Flow Summary:**

1. CellPay generates and sends OTP to the user’s device.
2. User submits OTP for verification.
3. Backend validates OTP → proceeds if correct.

## Step 8: Final Payment Validation and Redirection 

**Handled by:**  CellPay Backend & Merchant System 

After successful authentication, CellPay performs final validation, processes the transaction, and updates its ledger. 

Once complete: 
- The user is redirected to the merchant’s return URL provided in the initial request. 
- The redirection includes key parameters such as: 
    - transactionId 
    - status (success/failure) 
    - uniqueToken 
    - message or response code 

This step concludes the payment flow from the user’s perspective.

## Step 9: Access Token Retrieval 

**Handled by:**  Merchant Backend 

After payment completion, the merchant application retrieves **an access token** from CellPay using the `/sdk/login` endpoint. 

The access token is used for secure backend communication and subsequent transaction verification.

**Purpose:**
To authenticate the merchant system before querying transaction status or details.

## Step 10: Payment Status Inquiry 

**Handled by:**  Merchant Backend

Using the **unique transaction ID** and **access token**, the merchant system calls the `/sdk/transactions/{uniqueId}/status` API to verify the final status of the payment. 

The response includes: 
- Transaction amount 
- Payment type (wallet/bank) 
- Transaction date/time 
- Reference ID and status 

This ensures that the merchant can programmatically confirm and record the final state of the transaction within their own system. 
