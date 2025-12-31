# Payment Request Raw Request

```jsx title="Example Code Snippet"
@Setter 

@Getter 

@AllArgsConstructor 

@NoArgsConstructor 

public class PaymentRequest { 

    private String productCode; 

    @NotNull(message = "Redirect url is required") 

    @NotBlank(message = "Redirect URL cannot be blank") 

    @Size(max = 100, message = "Redirect url must be at most 100 characters long") 

    private String redirectUrl; 

    @NotNull(message = "Unique token is required") 

    @NotBlank(message = "Unique token cannot be blank") 

    @Size(max = 20, message = "Unique token must be at most 20 characters long") 

    private String uniqueToken; 

    @NotNull(message = "Amount is required") 

    @Digits(integer = 8, fraction = 2, message = "Transaction amount must be a number with up to 8 digits before the decimal and 2 digits after the decimal") 

    @DecimalMin(value = "0.0", inclusive = false, message = "Transaction amount must be greater than 0") 

    @DecimalMax(value = "99999999.99", message = "Transaction amount must be less than or equal to 99999999.99") 

    private String amount; 

    @NotNull(message = "Description is required") 

    @NotBlank(message = "Description cannot be blank") 

    @Size(max = 50, message = "Description must be at most 50 characters long") 

    private String description; 

    @NotNull(message = "member id required") 

    @NotBlank(message = "Member id cannot be blank") 

    @Size(max = 10, message = "Member id must be at most 10 characters long") 

    private String memberId; 

}    
```