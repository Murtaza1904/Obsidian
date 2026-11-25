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

### Mitigation
- Add http only flag
	It prevents browser to copy cookie on JavaScript request
	*Note: We can't put http only flag on local storage*
- Input validation
	Apply white list input validation to only allow selected characters
	*Report: Missing input validation*
- Content security policy
	It is header return by server that mention list of allowed origins of JavaScript
- Output encoding
	It is a technique which convert untrusted data into safe format