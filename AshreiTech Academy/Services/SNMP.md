
port: 161 UDP

It is an agent that tells the machine info

It was initially introduced for device health checkup.

It has an authentication using community string.

Community string is a password, it can be public password or private password.

### Brute Force Password
** Must perform password brute forcing

Tool : one sixty one tool for brute force

```
nmap -sU -p 161 <Victum IP> --script snmp-brute 
```

```
snmpwalk -v 1 -c <Password> <Victum IP>
```

```
snmpwalk -v 1 -c <Password> <Victum IP> NET-SNMP-EXTEND-MIB::nsExtendOutputFull

```


```
sudo apt install snmp snmp-mibs-downloader -y 
```
It has three versions
- v 1
- v 2c
- v 3 (Not useful)

First step:
try public string with all versions (v1, v2 c , v3)
then try private string with all versions (v1, v2 c , v3)

Second step:
brute force on all versions (v1, v2 c , v3)