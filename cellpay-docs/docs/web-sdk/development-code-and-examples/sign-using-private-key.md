# Sign Using Private Key 

```jsx title="Example Code Snippet"
public static String signUsingPrivateKey(PrivateKey privateKey, String textToSign) throws SignatureException, InvalidKeyException, 

    InvalidKeySpecException, NoSuchAlgorithmException { 

        Signature privateSignature = Signature.getInstance("SHA256withRSA"); 

        privateSignature.initSign(privateKey); 

        privateSignature.update(textToSign.getBytes(StandardCharsets.UTF_8)); 

        byte[] signature = privateSignature.sign(); 

        return Base64.getEncoder().encodeToString(signature); 

    } 
```