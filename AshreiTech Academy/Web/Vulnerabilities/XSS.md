### Cross-Site Scripting
XXS is a client side injection attack where malicious scripts are injected into a trusted websites and executed in a victim browser

Using XSS, attackers can steal session ID.

*Note: Always test XSS on all input fields*

```
"><script>alert('XSS')</script>
```

XSS vulnerability is test where input reflect on the web page.

### Types
- Reflected XSS / Non persistent
	Malicious JavaScript is included in a request and reflected in the server's response.
- Stored XSS / Persistent
	The malicious script is permanently store on the server and serve to other users
- Dom-Based XSS
	Client-side JavaScript processes untrusted input unsafely, causing script execution in the browser.