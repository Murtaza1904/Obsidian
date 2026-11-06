## File Transfer Protocol
found in 1970 for file transfer (downloading and uploading)

port: 21, 22

Default credentials:
- anonymous anonymous
- ftp ftp

```
ftp <username>@<Victum_IP>
```

FTP default password is vulnerable when we have an access to sensitive files.

FTP doesn't provide initial access but it can provide sensitive files.

- Always to banner grapping (version checking) for ftp protocol using nc <IP> <port> and nmap <IP> -sV
- If default password is not working then brute force password using hydra or metasploit module (ftp_login)

- After getting access to ftp, we can see all sensitive files, sometimes we get credentials in any file

Whenever logged into ftp, run passive command so you can download the files from ftp
passive needs to be off
mget * command to download all files
get filename command to download single file

```
passive off
```