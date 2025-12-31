# Summary of SDK Workflow

## Summery Table

| S.No. | Stage                     | Handled By          | Description                                             |
|------:|---------------------------|---------------------|---------------------------------------------------------|
| 1     | Initiate Payment Request  | Merchant Backend    | Send encrypted payment data to CellPay.                 |
| 2     | User Login Prompt         | CellPay UI          | Redirect user to login securely.                        |
| 3     | User Authentication      | CellPay Backend     | Validate credentials and initiate session.              |
| 4     | Payment Method Selection | CellPay UI          | User selects wallet or linked bank.                     |
| 5     | Payment Method Validation| CellPay Backend     | Validate chosen account and balance.                    |
| 6     | Payment Confirmation     | User + Backend      | Confirm details and re-enter password.                  |
| 7     | OTP Verification         | CellPay Backend     | Required for transactions above NPR 5000.               |
| 8     | Final Validation & Redirect | CellPay Backend   | Complete transaction and redirect user.                |
| 9     | Access Token Retrieval   | Merchant Backend    | Obtain token for post-payment queries.                  |
| 10    | Status Inquiry           | Merchant Backend    | Verify final transaction result.                        |
