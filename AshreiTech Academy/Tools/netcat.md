# Netcat (nc)

Summary Netcat is a default Linux networking utility — the "Swiss Army knife" of TCP/IP. Used for banner grabbing, port connectivity checks, file transfer, and setting up listeners/reverse or bind shells.

> [!info] `nc.exe` → Windows binary, commonly dropped on a target to get an **interactive shell** back to an attacker-controlled listener

In industry, you use netcat listener most of the time.
> [!warning] A single `nc` listener **only accepts one connection at a time**

## Core Use Cases

### 1. Banner / Version Grabbing

Connect to a service to see what it returns (service banner, version string):

```bash
nc <ip> <port>
```

- Useful for manually confirming what `nmap -sV` suggests
- Works well on text-based protocols (FTP, SMTP, HTTP, Telnet, SSH pre-banner)

### 2. Listener (Catching Shells)

Start a listener to receive an incoming connection (e.g., reverse shell):

```bash
nc -lvnp <port>
```

|Flag|Meaning|
|---|---|
|`-l`|listen mode|
|`-v`|verbose|
|`-n`|no DNS resolution (faster, avoids leaks)|
|`-p`|specify local port|

> [!tip] Listener handles **one connection only**. If it dies or you need a second shell, restart it on a new port or use a tool like `ncat -k`, `socat`, or a multi-handler (Metasploit).

## Quick Command Reference

```bash
nc <ip> <port>          # connect out / banner grab
nc -lvnp <port>         # start listener
```

## Interactive Terminal

```
Ctrl + z
```

```
stty raw -echo; fg
```

```
export TERM=xterm
```

```
export SHELL=bash
```
