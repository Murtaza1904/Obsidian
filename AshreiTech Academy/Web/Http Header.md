
## Http Request Header
- Host: Specify the domain name of the server
- User-Agent: Client initiating the request from which software (Browser)
	- User-Agent store the results in server logs, can use one liner reserve shell.
	- SQL injection
	- Blind XSS
- Accept: Specifies which response content types the client can understand. (Example: application/json)
- Authorization: Contains authentication credentials used to access protected resources.
	- Basic
	- Bearer
	- Digest
- Cookie: Sends stored cookies to the server. (Example: sessionid: abc123)
- Content-Type: Specifies the format of the data being sent in the request body. (Example: application/json)
- Referrer: Indicates the URL of the page that initiated the request. (Previous URL)
- Referrer-Policy: Referrer header rules (no-referrer, origin, strict-origin-when-cross-origin)