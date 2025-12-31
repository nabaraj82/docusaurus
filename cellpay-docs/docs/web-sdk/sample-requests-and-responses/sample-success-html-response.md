# Sample Success HTML Response

```jsx title="Displays a login form for user authentication"
<!DOCTYPE html> 
<html lang="en"> 
<head> 
    <meta charset="UTF-8"> 
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> 
    <title>Document</title> 
    <link rel="stylesheet" href="/css/style.css"> 
    <link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'> 
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script> 
</head> 
<body> 
    <div class="login_container"> 
        <div class="login_body"> 
            <a class="cellpay_logo" href="#"> 
                <img src="https://app.cellpay.com.np/img/cellpay_logo.svg" alt="cellpay_logo" /> 
            </a> 
            <hr> 
            <div class="login_form"> 
                <form id="login-form" action="/cellpay/sdk/paymentOptions" method="POST"> 
                    <div class="form_group"> 
                        <label>Username</label> 
                        <div class="input_with_icon"> 
                            <input type="text" id="username" name="username" class="form_control" /> 
                            <i class='bx bxs-user input_icon' style="color: black"></i> 
                        </div> 
                    </div> 
                    <div class="form_group"> 
                        <label>Password</label> 
                        <div class="input_with_icon"> 
                            <input type="password" id="password" name="password" class="form_control" /> 
                            <i class='bx bxs-lock-alt input_icon' style="color: black"></i> 
                        </div> 
                    </div> 
                    <input type="hidden" id="paymentRequestId" name="paymentRequestId" value="9D152266633C5C9CDB024ADC3BB5326E"/> 
                    <div class="form_group"> 
                        <div class="input_with_icon"> 
                            <input type="submit" class="signin_button"/> 
                        </div> 
                    </div> 
                </form> 
            </div> 
        </div> 
    </div> 
</body> 
</html> 
```