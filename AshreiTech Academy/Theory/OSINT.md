
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
dig <Victum IP>
```

- A record: Previous IPv4 addresses.
- AAAA record: Previous IPv6 addresses.
- MX record: Previous mail servers.
- NS record: Previous nameservers.
- CNAME record: Previous domain aliases.
- TXT record: Previous domain verification and policy records.

 > [!warning] *Note:* If you found any 3rd party mail server, you would not found server ip.


 ### Wayback Machine (Web Archive)
The Wayback Machine is a free web archiving service operated by the Internet Archive.
It allows you to view older versions of websites and investigate how websites looked in the past.

- Previous versions of websites.
- Old website pages and content.
- Changes in company information.
- Previously published contact information.
- Old URLs and website structures.
- Removed or modified public documents.
- Historical website design and technologies.

### GitHub / GitLab / GitHub Dorking
GitHub Dorking is an OSINT technique that uses advanced search queries on GitHub to find publicly available information inside repositories, source code, configuration files, and documentation.