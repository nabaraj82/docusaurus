# Generate Secret AES Key

```jsx title="Example Code Snippet"
public static SecretKey generateSecretKey() throws NoSuchAlgorithmException { 

    String randomString = generateRandomString(32); 

    byte[] randomBytes = Base64.getDecoder().decode(randomString); 

    return new SecretKeySpec(randomBytes, "AES"); 

} 
```