Subdomain enumeration is the process of discovering subdomains associated with a domain.

Domain is a website identity of a website. It is used to access primary resource

Domain: `example.com`
Subdomain: `mail.example.com`

Subdomain is a part of domain name that is used to identify a specific service, section or resource
under a main domain.

www.example.com and example.com are not same. www is a subdomain

crt.sh
It is a web based tool to find subdomains. It was introduced back in 2015 so google ca validate website SSL certificate. (It will not list website which doesn't have SSL certificate)

CLI base tools for subdomain finder
- subfinder
- sublister
- amass

Subdomain brute forcing
- gobuster
- ffuf
```
ffuf -u FUZZ.<Domain name> -w <brute force file>
```
- wfuzz (Server multiple websites) (Virtual host)
