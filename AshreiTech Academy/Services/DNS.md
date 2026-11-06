port: 53

## Domain Name System

Their are always backup DNS server (secondary server) in the organizations other than primary DNS server.

DNS zone transfer means that replicating all changes to secondary DNS server from primary DNS server.

### DNS zone transfer attack:
An attacker request zone transfer request to primary DNS server that I am a backup DNS server, give me all the data for backup. If no verification is setup than primary DNS server gives data to any secondary DNS server (attacker).

DIG Tool
```
dig @<Victum IP> <Domain name> AXFR
```

AXFR service helps in data replication

```
dig NS <Domain name>
```

NS: name server

```
dig AXFR @<Name server> <Domain name>
```
