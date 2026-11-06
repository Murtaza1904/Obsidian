## Definition
Nikto is an open-source **web server vulnerability scanner** pre-installed on Kali Linux. It checks web servers for:
- Dangerous/default files and scripts
- Outdated server software and versions
- Misconfigurations (e.g. directory indexing, risky HTTP methods)
- Missing security headers

> [!warning]
> It is noisy and easily detected. Only scan systems you own or have written permission to test.

## Common Flags
| Flag | Purpose |
|------|---------|
| `-h` | Target host (IP, hostname, or URL) |
| `-p` | Port(s) to scan (e.g. `80,443,8080`) |
| `-ssl` | Force SSL/TLS mode |
| `-nossl` | Disable SSL |
| `-o` | Save output to a file |
| `-Format` | Output format: `txt`, `csv`, `htm`, `xml`, `json` |
| `-Tuning` | Limit test types (e.g. `1` = interesting files, `2` = misconfigs, `9` = SQL injection) |
| `-evasion` | IDS evasion techniques |
| `-useproxy` | Scan through a proxy |
| `-timeout` | Request timeout in seconds |
| `-maxtime` | Max scan duration |
| `-Display` | Control what is shown (`1` = redirects, `V` = verbose) |
| `-update` | Update plugins and databases |
| `-Version` | Show Nikto version |
| `-list-plugins` | List available plugins |

## Command Structure
```bash
nikto -h <target> [-p <port>] [-ssl] [-Tuning <x>] [-o <file> -Format <fmt>]
```

## Example
```bash
nikto -h http://192.168.1.10 -p 80,443 -o nikto_scan.html -Format htm
```
Scans ports 80 and 443 on `192.168.1.10` and saves an HTML report.

Quick scan:
```bash
nikto -h 192.168.1.10
```