## Cross-Site Request Forgery
It is a web based attack where attackers performs actions on behave of the user where he tricks a user into performing actions on a website where they are already authenticated without their knowledge or concern but using their authenticated cookie stored in the browser.
#### Core Requirement
- Required a session cookie on the victim browser
- Attacker should know on which platform does the victim is currently logged in
- Attacker creates malicious website
- This attack is perform where the state changes / HTTP requests other than GET request
- Attacker needs to be a part of that platform to capture a request
#### Scenarios
- Email change
- Password change
- Money transfer
- Settings update
- Post or comment
#### Mitigations
- CSRF Tokens
	It is a unique, secret and unpredictable to protect against unauthorized cross site request
	It is for one time use only
	Passes on: Hidden field, cookie, request body, headers

#### CSRF Bypasses
- CSRF reuse
- remove CSRF parameter
- CSRF empty parameter value
- Incorrect CSRF value
- CSRF token not bound with user session