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

### Security Headers
- HSTS
- x-frame-options
- content security policy
- x-content-type-options
- strict-transport-security
- referrer-policy

### Misconfigurations
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
- Information disclosure / Banner grabbing (Info reveal)
- Verbose error message / Improper error handling
- debug mode enabled (Reveal info)
	- file paths
	- DB credentials
	- source code
	- SQL queries
	- OS version
	- RCE (Remote code execution)
	- Server IP
- Improper exception handling

### Login page testing
- Username enumeration (input fields tells that username is incorrect)
	- Try both valid and invalid username during username enumeration
	- Also check it on forgot password page
- SQL injection
- captcha bypass
- Missing rate limiting (Do it in last of the testing)

### Post Login
- Phone number enumeration (On profile update page)
- Missing http flag
- Missing secure flag

Check page source in browser to see any reveal information

### Captcha
To prevent bots
- Login page
- Web scrapping

Types of captcha
- text base captcha
- image base captcha
- checkbox captcha
- invisible captcha

Captcha failure
- Captcha response not validating on server side
	- Remove captcha parameter
	- Change name of captcha parameter
- Captcha reuse (one time use)
- Empty captcha value accepted (null value/ zero value)
- HTTP method change (POST to GET)
- Expire captcha reuse

*Note: Test rate limiting after captcha bypass* 
### Rate Limiting
- Login page (To prevent brute forcing)
- Register page (To prevent multiple users creation)
- Forgot password page (To prevent multiple emails sending)
- OTP
- File upload
### SQL Injection
It is a vulnerability where attacker manipulates queries interacting through the backend 
It held due to backend weakness as backend inject the user input directly in query

*Note: Test SQL injection perform where ever found input fields in the web*

SQL is a language to communicate with database 
DBMS is a software used for database (MS SQL, MYSQL, Postgres, Oracle)
	Each DBMS can have different payload injection

Types of SQL Injection
- Union base SQL injection
- Error base SQL injection
- Blind base SQL injection
	- Time base SQL injection (Inject time base delay in query)
	- Boolean base SQL injection (Minor content alteration)

```
SELECT *
FROM users
WHERE username = 'test'
AND password = '123'
```

```
' OR '1' = '1' --
```

Two parts of the query:
- Data literal (strings,number)
- Query Logic (query)

After SQL injection login bypass, it will login with the very first user return by database

SQL injection login Authentication bypass is due to backend code logic issue.

Report: User authentication bypass using SQL injection

#### Union Base SQL Injection:
When results show on web page like product list page, we need to test the union base SQL injection
- Add `'` quote to inject
- Add `' OR 1 = 1`  and `' OR 1 = 2` Boolean injection

When found union base SQL injection, find number of columns exists in table
- Determine the number of columns of current query
```
UNION SELECT NULL --
```

```
 ' ORDER BY 20 --
```

- Determine the datatype of the column
```
' UNION SELECT NULL, 'a', NULL, NULL
```

*Note: Payload is always inject in the string data literal*

Finding Database Version
MS SQL/ MYSQL
```
' UNION SELECT NULL, @@version --
```

#### Error base SQL injection
It is a technique if SQL injection vulnerability exists or not.
It errors shows any info related to SQL query or version or response