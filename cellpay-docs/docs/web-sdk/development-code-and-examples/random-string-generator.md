# Random String Generator

```jsx title="Example Code Snippet"
private static String generateRandomString(int length) { 

    String chars = 

        "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789"; 

    StringBuilder sb = new StringBuilder(); 

    SecureRandom random = new SecureRandom(); 

    for (int i = 0; i < length; i++) { 

        int index = random.nextInt(chars.length()); 

        sb.append(chars.charAt(index)); 

    } 

    return sb.toString(); 

} 
```