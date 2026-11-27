
1) Sensitive data pass in get method
2) GET POST confusion
3) Server IP expose if WAF is present
4) wrong http status code
5) Directory listing expose
6) Unencrypted communication (without https)
7) Missing HSTS header (SSL not unforced)
8) SSL / TLS (Newer version of SSL, 1.0 and 1.1 obsolete version) version
	- SSL scan CLI tool
9) Missing security headers
	- securityheaders.com Tool
	- shcheck CLI tool
10) vulnerable and outdated component (outdated version)
11) vulnerable JavaScript
	- retire.js (browser extension)
12) Information disclosure / Banner grabbing (Info reveal)
13) Verbose error message / Improper error handling
14) debug mode enabled (Reveal info)
	- file paths
	- DB credentials
	- source code
	- SQL queries
	- OS version
	- RCE (Remote code execution)
	- Server IP
15) Improper exception handling



Check page source in browser to see any reveal information


Session being stored in local storage (Cookies are safe, local storage are not safe)
Cookie generates CSRF vulnerability

Password Policy Enforcement