
port: 445

It uses authentication and authorization.

It is a file sharing protocol.

It works over the network.

Shared is a folder that is share to the group of people.

need to check if connection is establishing without authentication

### SMB null session
It allows shared folder without authentication. Blank username and password.

### Enum4linux
enum4linux (Tool) used to check if connection without authentication is possible
```
enum4linux -a <Victum IP>
```
 
 Results:
  share enumeration has users useful without $
  with $ in the end of the name is a default shared folders
  - SIDS, IP's

### Nmap:
```
nmap --script smb-enum-shares -p 445 <Victum IP> -n
```

This nmap script will tell the permissions of the shared folders.


### smbclient

List with null session:
```
smbclient -L //<Victum IP> -N
```

-N is for null sessions
smbclient only tells shared folders info.

If we get an access to smb directory where web applications are hosted, we can upload the reverse shell file there. 

After successfully file uploaded, we then need to execute the file by visiting the <website url>/<filename>

We can also use LFI vulnerability to execute that file.

Write access is only helpful for web applications otherwise we are unable to execute that malicious file. It will then give the backdoor