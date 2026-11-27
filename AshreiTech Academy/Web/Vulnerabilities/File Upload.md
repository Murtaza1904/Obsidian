### Definition
A file upload vulnerability occurs when a web application allow users to upload files without properly validating their type, content, size or name allowing attacker to upload the malicious files and get processed by the server.

### Parameter
- Filename
	It is a user control parameter
- Content type / Mime
	image/jpeg, image/png
- File content
	It is not readable as it is in binary format

### Achieve
File upload can provide RCE (Reverse Code Execution) / Web shell / Reverse shell

### Core Requirement
We need to know the uploaded file path in order to execute it

### Other Concepts
**Reverse shell:** The target computer reaches out and connects back to your computer so you can type commands on it.

**Web shell:** A small script on a website that lets you run commands on the website's server through a normal web page or web link.

### Bypasses
- Client side validation removed in server response
- Same parameters value in burp after browser
- Server side validation
	- Change file extension like php2 etc (Black list validation)
	- Change file double extension like shell.php.jpeg, shell.jpeg.php (White list validation)
	- Add null bytes in extension like shell.php\00.jpeg
	- Case sensitive extension like Php, pHp, PHP
	- Trailing character like shell.php\n.jpeg
	- **polyglot file upload attack** is when an attacker uploads a single file disguised to look like a safe file (such as an image) while secretly containing hidden code (such as PHP or JavaScript) inside it.