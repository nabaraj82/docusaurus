---
id: creating-payment-request-dto
title: Creating a Payment Request DTO
---


## Overview

This section provides sample Java code to help developers implement encryption, signing, and payload preparation for the CellPay SDK integration.

All payloads must follow the encryption, signing, and key-exchange principles described in the Security Architecture section.

## Example

This code demonstrates how to prepare an encrypted and signed payment request before sending it to the `/sdk/paymentRequest` API.

```jsx title="Example Code Snippet"
private PaymentBookingDTO createDummyPaymentDTO() throws Exception {
        PaymentRequest paymentRequest = new PaymentRequest();
        paymentRequest.setAmount("2000");
        paymentRequest.setDescription("Payment for Merchant");
        paymentRequest.setRedirectUrl("http://merchanturl.com");
        paymentRequest.setUniqueToken("675756"); //must be unique
        paymentRequest.setMemberId("memberId"); //Provided by CELLPAY
        paymentRequest.setProductCode("P006");
        PaymentBookingDTO paymentBookingDTO = new PaymentBookingDTO();
         String signature = Cryptography.signUsingPrivateKey(clientPrivateKey,
            objectMapper.writeValueAsString(paymentRequest));
        paymentBookingDTO.setSignature(signature);
        SecretKey secretKey = Cryptography.generateSecretKey();
        String encryptedSecretKey =
            Cryptography.encryptSecretKeyWithRSA(secretKey, publicKey);
        paymentBookingDTO.setSecret_key(encryptedSecretKey);
        String encryptedData =
            Cryptography.encryptWithAES(objectMapper.writeValueAsString(paymentRequest),
                secretKey);
        paymentBookingDTO.setData(encryptedData);
        paymentBookingDTO.setClient_id("9812378565
            "); // client_id is your assigned CellPay merchant username.
return paymentBookingDTO;
        }
```
