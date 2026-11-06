port: 22

ssh provide initial access to machine.

It perform encryptions (encrypted tunnel). If you inspect network packets using wireshark, you will be encrypted requests

Their are two types of authentication of ssh:
- using credentials (username, password)
-  id_rsa file (public key, private key)

After getting id_rsa file, change permission to 600

```
chmod 600 id_rsa
```

You can brute force the authentication using hydra and metasploit module (ssh_login)

if nothing works, then go with version checking of ssh and find its version vulnerability.


### SSH Login command:
```
sudo ssh username@<Victum IP>
```

To remove the old id_rsa file for default authentication
```
ssh-keygen -f "/home/kali/.ssh/known_hosts" -R "<Attacker IP>"
```