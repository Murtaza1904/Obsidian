### Server-Side Request Forgery
It is a web application attack that allows an attacker to manipulate a server into making unintended request to internal or external resources.

Core Requirement
- Where there you found URL parameter in request

Legal URL: https://test.com

Attacker URL: https://localhost/admin

Common parameters:
url=
uri=
link=

We can scan the subnet of the internal network by checking all the 254 subnet from 1 to 254
192.168.1.1 - 192.168.1.254

Similarly do scan all ports from 1 to 10000
https://localhost:8080

### Blind SSRF
- Out of band detection
	Using burp collaborator to check if server make any request. Minor change