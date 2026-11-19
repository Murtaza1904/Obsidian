
Open-Source Intelligence
## Types
1) Passive
2) Active
### Passive (Indirect)
> *Note:* No packet send to target. 
- 🔎 People search: Finding publicly available information about someone.
- 🌐 Social media research: Analyzing public Instagram, Facebook, LinkedIn, and X profiles.
- 🛡️ Cybersecurity: Identifying exposed information and security risks.
- 🏢 Business intelligence: Researching companies, competitors, and organizations.
- 📰 Investigations: Verifying news, images, locations, and online claims.

### Active (Direct)
>*Note:* Packet sending start.
- Use tools like nmap for finding open ports and its versions
- Finding subdomains


### Google Dorking
Google Dorking is an OSINT technique that uses advanced Google search operators to find specific information indexed by Google.

| Operator       | Purpose                          |
| -------------- | -------------------------------- |
| `site:`        | Search within a specific website |
| `filetype:`    | Find specific file types         |
| `intitle:`     | Search words in page titles      |
| `inurl:`       | Search words in URLs             |
| `intext:`      | Search words in page content     |
| `exact phrase` | Search an exact phrase           |
| `-`            | Exclude a word                   |
| `OR`           | Search for either term           |

### Shodan / Censys / FOFA
It is a search engine for Internet-Connected devices.
It uses crawlers to find IP address. Open ports found using similar packet request sent as of nmap (props).
- IP address
- Open ports
- Service information
- Software versions
- Organization
- Country and approximate location
- Service banners

### DNS / Historical DNS
Historical DNS is an OSINT technique used to discover the previous IP addresses and DNS records associated with a domain name.

```
dig <Domain name>
```

- A record: Previous IPv4 addresses.
- AAAA record: Previous IPv6 addresses.
- MX record: Previous mail servers. (Only useful when its own mail server is using)
- NS record: Previous nameservers.
- CNAME record: Previous domain aliases.
- TXT record: Previous domain verification and policy records.

 > [!warning] *Note:* If you found any 3rd party mail server, you would not found server ip.

Or hit that IP on browser and if it returns website than it's a valid IP
### Wayback Machine (Web Archive)
The Wayback Machine is a free web archiving service operated by the Internet Archive.
It allows you to view older versions of websites and investigate how websites looked in the past.

- Previous versions of websites (Snapshorts).
- Old website pages and content.
- Changes in company information.
- Previously published contact information.
- Old URLs and website structures.
- Removed or modified public documents.
- Historical website design and technologies.
- Config files

### GitHub / GitLab / GitHub Dorking
GitHub Dorking is an OSINT technique that uses advanced search queries on GitHub to find publicly available information inside repositories, source code, configuration files, and documentation.

> [!info] If server IP found, report it as vulnerability.
### JavaScript File Enumeration
JavaScript file enumeration is an OSINT and web reconnaissance technique used to discover publicly accessible JavaScript (`.js`) files associated with a website or domain.
- API endpoint references.
- Publicly documented API routes.
- Application configuration.
- Authentication flow implementation.
- Third-party integrations.
- Exposed development information.
- Deprecated libraries and dependencies.

### Metadata Extraction
In OSINT, metadata is information embedded in or associated with files, documents, images, videos, websites, and JavaScript resources.

`Linux Tool: ExifTool`
```
exiftool -u -a <Filename>
```

- File names and version numbers.
- Source map references.
- Build timestamps, when available.
- Source directory paths.
- Framework and library versions.
- Comments and development information.

### Whois
WHOIS is an OSINT technique used to retrieve publicly available domain registration information. 

> Is also tells if WAF is present.

whois command to check using IP to verify it's a server IP
```
whois <Victum IP> | grep "Organization name, Net name"
```

```
whois <Domain name>
```

| Field                   | Description                         |
| ----------------------- | ----------------------------------- |
| Domain Name             | Registered domain                   |
| Registrar               | Domain registration company         |
| Registrant              | Registered domain holder, if public |
| Creation Date           | Domain registration date            |
| Expiry Date             | Domain expiration date              |
| Updated Date            | Last registration record update     |
| Name Servers            | Authoritative DNS servers           |
| Registrant Organization | Organization, if disclosed          |
| Country                 | Registrant country, if disclosed    |
| DNSSEC                  | DNS security status                 |

ping command to find IP
```
ping <Domain name>
```

host command to find IP
```
host <Domain name>
```

Netcraft is a website that give info of the website.

Wappalyzer is a browser extension that tells website tech stack.

Whatweb is a CLI based tool that tells website tech stack.
```
whatweb <Domain name>
```

nmap is also used to find versions of website
```
nmap -sv <IP>
```

burp suit
burp suit repeater http response can also tells website versions.

JavaScript
JavaScript file can also expose website versions.

Directory Listing
Can be used to find tack stack of the website.


*Report vulnerability: Information disclosure / Banner grabbing*

Webwoof tool
It is a Linux CLI tool to find id WAF is present.
```
webwoof <Domain name>
```

Robots.txt
This file contains crawlers ignoring end points

Directory Listing
Need to find hidden directories of the website.

Tools of Directory Listing
- ffuf
```
ffuf -u <Domain name>/fuzz -w <brute force file>
```
- gobuster
```
gobuster dir -u <Domain name> -w <brute force file>
```
- Feroxbuster
```
feroxbuster -u <Domain name> -x php
```

*Report vulnerability: Enable directory listing*

Whenever found open directory listing, download the files my clicking on the filename.
Try to upload file using put method if found directory listing.

IF found WAF, ask the client if testing perform with WAF or without WAF as WAF is blocking payloads.