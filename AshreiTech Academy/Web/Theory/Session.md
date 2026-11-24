### Session Management
It is a way for server to remember who you are instead of asking credentials on each request.
It generates a session id after login and then browser store it and send to each request.
Session id is an authentication proof.
#### Types of Sessions
- Stateful
	A stateful system remembers previous interactions or requests and maintains information about the user's session.
- Stateless
	A stateless system does not remember previous requests. Every request is treated independently. (Example: HTTP)

#### Types of Server
- Stateful
	A stateful server is a server that maintains information about a client's previous requests or interactions. (Example: Session)
- Stateless
	A stateless server is a server that does not maintain client session information between requests. (Example: JWT)

Session store in two places
- Cookie
- Web storage (Local storage/ Session storage)

Session being stored in local storage (Cookies are safe, local storage are not safe)
Cookie generates CSRF vulnerability
#### Types of cookie
- Pre login cookie
	A pre-login cookie is a cookie created before the user logs in. It helps the website remember information about the visitor before authentication.
- Post login cookie
	A post-login cookie is a cookie created after the user successfully logs in. It commonly contains a Session ID or an authentication-related token.

*Note: Always decode the session id to find any sensitive information*
*Note: Session ID is more sensitive than login credentials*
### Vulnerabilities
- Predictable session id
	Any pattern found in the session ids
- Session fixation
	Pre login and post login session id is same
- Missing session expiry
	Session is not expiring even no activity for 10 minutes
- Session not invalidated on logout
	Session is not expiring even after logout
- Session reuse across users
- Session not invalidating on password change
	Session is not expiring from all devices after password change
- Password change without old password
	Ask for current password when changing password
	*Note: If not asking for current password, then CSRF vulnerability generates*
	- Empty current password checking
	- Check wrong current password
	- Remove current password parameter from payload
	- Method change from POST to GET and POST to PUT
	- Change someone else password (username, IDOR)