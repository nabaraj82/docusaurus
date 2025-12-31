# Encrypt Secret Key with RSA

```jsx title="Example Code Snippet"
public static String encryptSecretKeyWithRSA(SecretKey secretKey, PublicKey publicKey) throws Exception { 

    Cipher cipher = Cipher.getInstance("RSA/ECB/PKCS1Padding"); 

    cipher.init(Cipher.ENCRYPT_MODE, publicKey); 

    byte[] encryptedKey = cipher.doFinal(secretKey.getEncoded()); 

    return Base64.getEncoder().encodeToString(encryptedKey); 

} 
```