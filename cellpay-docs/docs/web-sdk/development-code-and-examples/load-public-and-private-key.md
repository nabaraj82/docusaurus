# Load Public and Private Keys from Local Storage

```jsx title="Example Code Snippet"
public static PublicKey loadPublicKey(String location) throws Exception { 
    String key = readKeyFile(location); 
    String cleanKey = key 
            .replace("-----BEGIN PUBLIC KEY-----", "") 
            .replace("-----END PUBLIC KEY-----", "") 
            .replaceAll("\\s+", ""); 
    byte[] decoded = Base64.getDecoder().decode(cleanKey); 
    X509EncodedKeySpec spec = new X509EncodedKeySpec(decoded); 
    return KeyFactory.getInstance("RSA").generatePublic(spec); 
} 
//Load Private Key 
public static PrivateKey loadPrivateKey(String location) throws Exception { 
    String key = readKeyFile(location); 
    String cleanKey = key 
            .replace("-----BEGIN PRIVATE KEY-----", "") 
            .replace("-----END PRIVATE KEY-----", "") 
            .replaceAll("\\s+", ""); 
    byte[] decoded = Base64.getDecoder().decode(cleanKey); 
    PKCS8EncodedKeySpec spec = new PKCS8EncodedKeySpec(decoded); 
 
    return KeyFactory.getInstance("RSA").generatePrivate(spec); 
} 
```