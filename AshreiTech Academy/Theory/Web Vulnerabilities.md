- Incorrect HTTP method (GET, POST...)
- Wrong HTTP status code
- SQL injection
- Blind XSS (Cross Side Scripting)
- Session hijacking (JWT: JSON Web Token)
- Session fixation (The website does not generate a new session ID after login)
- WAF bypass (Direct server IP access) (Server IP expose)
- Referrer header expose previous URL
- Banner grabbing (Web technologies version expose)
- Directory Listing expose
- Metadata information disclosure
- HTTPS is not setup (Request without encryption)
- Misconfiguration (Default, weak password, plaintext password, config file disclosure)
- Missing Security Patches
- Local File Inclusion (LFI) and Remote File Inclusion (RFI) (File upload without proper sanitization)



- sensitive data pass in get method
- get post confusion
- server IP expose if WAF is present
- wrong http status code
- directory listing expose


- unencrypted communication (without https)
- missing HSTS header (SSL not unforced)
- SSL / TLS (Newer version of SSL, 1.0 and 1.1 obsolete version) version
	- SSL scan CLI tool
- Missing security headers
	- securityheaders.com Tool
	- shcheck CLI tool
- vulnerable and outdated component (outdated version)
- vulnerable JavaScript
	- retire.js (browser extension)
- Information disclosure / Banner grabbing
- Verbose error message / Improper error handling
- debug mode enabled (Reveal info)
	- file paths
	- DB credentials
	- source code
	- SQL queries
	- OS version
- incorrect exception handling

### Security Headers
- HSTS
- x-frame-options
- content security policy
- x-content-type-options
- strict-transport-security
- referrer-policy