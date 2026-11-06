
```
smbclient //<Victum IP> -N
```

```
smbclient -L //<Victum IP> -N
```

```
smbclient //<Victum IP>/tmp -N
```

```
put  <your file complete path> <filename to set on upload>
```

```
get <filename>
```

* get will download the file at the location you open the terminal
- -N for null session.
- -L for listing directories

```
smbclient //<Victum IP>/<Directory_name> -U <Username>
```
