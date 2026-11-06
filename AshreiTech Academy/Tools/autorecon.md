
Always run autorecon tool after running nmap. 

It scan faster than nmap for udp open ports

use the sudo so that you will also get the udp port

```
sudo apt install autorecon -y
```

```
sudo autorecon <IP>
```

This tool only shows the open ports