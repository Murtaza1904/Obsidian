Subdomain enumeration is the process of discovering subdomains associated with a domain.

Domain: `example.com`
Subdomain: `mail.example.com`

crt.sh
It is a web based tool to find subdomains. It was introduced back in 2014 so google ca validate website SSL certificate.

Subdomain brute forcing
- gobuster
- ffuf
```
ffuf -u FUZZ.<Domain name> -w <brute force file>
```
- wfuzz (Server multiple websites) (Virtual host)

CLI base tools for subdomain finder
- subfinder
- sublister
- amass
