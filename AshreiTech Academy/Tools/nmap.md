## What is Nmap?
Nmap (Network Mapper) is a network scanner used to find **live hosts**, **open ports**, and the **services** running on them.

## How It Works
- Nmap uses TCP connection attempts to decide whether a port is reachable.
- **TCP Connect scan (`-sT`)** completes the full 3-way handshake.
- **SYN scan (`-sS`, default with root)** sends SYN, receives SYN/ACK, then sends RST. It never completes the handshake, so it is called a "half-open" scan. Results are the same as `-sT`, just faster and stealthier.

> [!info] 3-Way Handshake
> `SYN` → `SYN/ACK` → `ACK`

## Port States
| State        | Meaning                                                                                                                                                          |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Open**     | Service replied (SYN/ACK), handshake can complete                                                                                                                |
| **Closed**   | Host replied with RST. Reachable, but nothing is listening                                                                                                       |
| **Filtered** | No reply or an error. A firewall is likely blocking packets, so Nmap can't confirm the state. A **filtered** result is a strong hint that a firewall is present. |


> [!warning] Open port ≠ Vulnerability
> An open port is only an entry point. The **service behind it** (version, configuration, credentials) is what may be vulnerable.

## Common Ports & Default Credentials
| Service | Port(s) | Default / Common Credentials |
|---|---|---|
| FTP | 20, 21 | `anonymous` / `anonymous` or `ftp` / `ftp` |
| SSH | 22 | No universal default; check device docs (e.g. `root` / `toor` on some test VMs) |
| Telnet | 23 | `admin` / `admin`, often blank password on routers/IoT |
| SMTP | 25 | No login by default; open relay is the risk to check |
| DNS | 53 | N/A |
| HTTP | 80 | `admin` / `admin` on many web admin panels |
| POP3 | 110 | Matches the mail account credentials |
| IMAP4 | 143 | Matches the mail account credentials |
| HTTPS | 443 | Same as HTTP, encrypted |
| SMB | 139, 445 | Often allows null/anonymous sessions |
| RDP | 3389 | `administrator` / blank on misconfigured hosts |
| WinRM | 5985, 5986 | Uses Windows account credentials |

> [!warning]
> These are common defaults seen in misconfigured or legacy systems — not guaranteed for every target. Always verify against the specific service/vendor documentation. Only test credentials on systems you're authorized to assess.

## Nmap Commands

| Flag         | Purpose               | Notes                                                                                     |
| ------------ | --------------------- | ----------------------------------------------------------------------------------------- |
| `-sn`        | Host discovery        | Finds live hosts, no port scan                                                            |
| `-sT`        | TCP connect scan      | Completes the full 3-way handshake                                                        |
| `-sS`        | TCP SYN scan          | Half-open scan, needs root                                                                |
| `-sU`        | UDP scan              | Slower than TCP scans                                                                     |
| `-sV`        | Version detection     | Also used for **banner grabbing** — reads the service banner to identify software/version |
| `-O`         | OS detection          | Needs root                                                                                |
| `-p-`        | Scan all ports        | All 65535 ports                                                                           |
| `-p 1-100`   | Scan a port range     | Also works for single/listed ports: `-p 22,80,443`                                        |
| `-Pn`        | Skip host discovery   | Treats host as up even if it ignores ping. Doesn't bypass a firewall                      |
| `-n`         | No DNS resolution     | Skips reverse DNS lookups, faster and quieter                                             |
| `-v` / `-vv` | Verbose mode          | Shows scan progress live; `-vv` is even more detailed                                     |
| `-A`         | Aggressive scan       | Combines `-sV`, `-O`, script scanning (`-sC`), and traceroute in one command              |
| `-oN <file>` | Normal output         | Saves results to a file                                                                   |
| --help       | Lists command options | Show all the options                                                                      |
| man          | Opens the manual page | Show the manual page if available                                                         |

## Nmap Scripting Engine (NSE)

> [!tip] Rule of thumb
> Whenever you find a service running (FTP, HTTP, SMB, etc.), try running Nmap scripts against it.

### Finding Scripts
```bash
# Count all available scripts
ls /usr/share/nmap/scripts | wc -l

# Search for scripts by service name
ls /usr/share/nmap/scripts | grep -E "http|smb"
```

### Running Scripts
```bash
# Run one specific script
nmap <IP> --script smb-os-discovery -p 139

# Run all scripts matching a pattern, save to file
nmap <IP> -p 139 --script "smb*" -oN file.txt
nmap 172.20.10.10 -p139 --script "smb*" -oN smb_full_enum.txt

# Web enumeration
nmap 172.20.10.10 --script http-enum -p80

# Vulnerability scan
nmap <IP> --script vuln
```

| Option | Purpose |
|---|---|
| `--script <name>` | Run a specific script |
| `--script "smb*"` | Wildcard: run every script starting with `smb` |
| `--script vuln` | Run all scripts in the **vuln** category |
| `-oN <file>` | Save output in normal format |

### Script Categories
| Category | What it does |
|---|---|
| `default` | Safe, general-purpose scripts (also run with `-sC`) |
| `discovery` | Gathers extra info about the target |
| `vuln` | Checks for known vulnerabilities |
| `auth` | Checks authentication, like anonymous logins |
| `brute` | Brute-forces credentials |
| `exploit` | Actively tries to exploit vulnerabilities |

> [!warning]
> `vuln`, `brute`, and `exploit` categories are intrusive and noisy. Only run them on systems you own or have written permission to test.
