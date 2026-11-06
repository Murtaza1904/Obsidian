## Definition

**Nuclei** is a fast, template-based vulnerability scanner by ProjectDiscovery. It sends requests defined in YAML templates (community-maintained) to detect CVEs, misconfigurations, exposed panels, default credentials, and more across web apps, networks, DNS, and cloud. Use it only on systems you are authorized to test.

> [!info] Install: 
> `sudo apt install nuclei` 
> or 
> `go install github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest`  
> 
> Update templates: `nuclei -ut`

## Flags

|Category|Flag|Description|
|---|---|---|
|Target|`-u <url/IP>`|Single target|
|Target|`-l <file>`|List of targets from file|
|Templates|`-t <path>`|Specific template or directory|
|Templates|`-w <workflow>`|Run a workflow|
|Templates|`-ut`|Update templates|
|Templates|`-tl`|List available templates|
|Filtering|`-s <severity>`|Filter by severity: info, low, medium, high, critical|
|Filtering|`-tags <tag>`|Run templates by tag (cve, rce, xss, wordpress)|
|Filtering|`-id <id>`|Run template by ID|
|Filtering|`-etags <tag>`|Exclude tags|
|Filtering|`-es <severity>`|Exclude severities|
|Output|`-o <file>`|Save results to file|
|Output|`-j` / `-jsonl`|JSON output|
|Output|`-silent`|Show only findings|
|Output|`-v`|Verbose|
|Output|`-nc`|No color|
|Performance|`-c <n>`|Concurrent templates (default 25)|
|Performance|`-rl <n>`|Rate limit (requests/second)|
|Performance|`-timeout <sec>`|Request timeout|
|Performance|`-retries <n>`|Retry count|
|Other|`-H "Header: value"`|Custom header|
|Other|`-proxy <url>`|Use proxy (e.g. Burp)|
|Other|`-stats`|Show scan progress|
|Other|`-version`|Show version|

## Command Structure

```
nuclei -u <target> [-t templates] [-s severity] [-tags tags] [-o output]
```

## Examples

**Basic scan:**

```
nuclei -u 192.168.1.10
```

**High/critical only, saved to file:**

```
nuclei -u http://192.168.1.10 -s high,critical -o results.txt
```

**Target list with CVE templates:**

```
nuclei -l targets.txt -tags cve -rl 50
```
