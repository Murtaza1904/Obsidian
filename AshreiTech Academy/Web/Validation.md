
Two types of validation: 
```
Client side, Server side
```

## Client Side (Browser)
- Client side validation are on frontend. They can be easily bypass using burp suit.
- Can be done using html attributes or javascript.
- You can easily see the client side validation using browser inspect element or page source.
- Every thing that initiate from client side can be seen from burp suit.

```
Client side -> burp suit -> Server side
```

## Burp Suit
- Use to bypass validation after client side.


>Note: We need to test every input field for attack.

>Testing perform in web application is only perform in input fields

Always create a folder, and inside it store the burp suit result.

Create a certificate from burp suit in .cer extension and then import that certificate in the browser certificates. 