# Encrypt Payload with RSA

```jsx title="Example Code Snippet"
public static String encryptWithAES(String plainText, SecretKey secretKey) 

throws Exception { 

    Cipher cipher = Cipher.getInstance("AES/ECB/PKCS5Padding"); 

    cipher.init(Cipher.ENCRYPT_MODE, secretKey); 

    byte[] xx = cipher.doFinal(plainText.getBytes()); 

    return Base64.getEncoder().encodeToString(xx); 

} 
```