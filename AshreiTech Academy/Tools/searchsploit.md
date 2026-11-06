## What is searchsploit?

`searchsploit` is a command-line search tool for the **Exploit-DB** archive, bundled with Kali Linux (and installable elsewhere). It lets you query a local, offline copy of the Exploit-DB database for exploits, shellcode, and papers by keyword — no internet connection required once the database is synced.

## Flags

|Flag|Purpose|
|---|---|
|`-u`|Update the local Exploit-DB database|
|`-t`|Search title only (default search mode)|
|`-w`|Show the original Exploit-DB web URL instead of local file path|
|`-p <EDB-ID>`|Show full path and mirror info for a specific exploit ID|
|`-x <EDB-ID>`|Examine/view the exploit source code|
|`-m <EDB-ID>`|Mirror (copy) the exploit to current directory|
|`-j`|Output results in JSON format|
|`--id`|Show EDB-ID and CVE numbers in results|
|`--cve <CVE-ID>`|Search by CVE number|
|`--colour` / `--nocolour`|Toggle colored output|
|`-v`|Verbose output|

## Command structure

```bash
searchsploit [flags] <search terms>
```

- Multiple search terms are AND'd together by default.
- Terms are matched against exploit titles (and paths, depending on flags).

## Example

```bash
searchsploit apache 1.3
```

Searches for exploits with "apache" and "1.3" in the title — returns legacy Apache 1.3.x vulnerabilities (e.g., mod_rewrite issues, chunked encoding overflow).

Follow-up to inspect a result:

```bash
searchsploit -x 12345      # view exploit code
searchsploit -m 12345      # copy exploit locally
```
