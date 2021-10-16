# NMAP Cheat Sheet

* NMAP brute forces DNS hostnames guessing subdomains</br>
```
nmap -Pn --script=dns-brute <DOMAIN_NAME>

Example: nmap -Pn --script=dns-brute domain.com
```

* NMAP whois query</br>
```
nmap --script whois* <DOMAIN_NAME> 

Example: nmap --script whois* domain.com
```

* NMAP detect cross site scripting CSS vulnerabilities</br>
```
nmap -p80 --script http-unsafe-output-escaping <DOMAIN_NAME>

Example: nmap -p80 --script http-unsafe-output-escaping domain.com 
```

* NMAP check for SQL injections</br>
```
nmap -p80 --script http-sql-injection <DOMAIN_NAME> 

Example: nmap -p80 --script http-sql-injection domain.com
```

* NMAP scan for vulnability</br>
```
sudo nmap --script vuln <TARGET_IP> 

Example: sudo nmap --script vuln 192.168.100.1
```

* NMAP use as decoy</br>
``` 
sudo nmap -sS -D <DECOY IP_ADDRESS> <TARGET_IP> 

Example: sudo nmap -sS -D 172.168.100.1 192.168.100.1 
```

* NMAP use stealthy to scan network with live IP address with open port
``` 
sudo nmap -sS -p <PORT 1>,<PORT 2> <TARGET_IP/24> 

Example: sudo nmap -sS -p 80, 443 192.168.100.0/24> 
```

* NMAP scan live IP address on the network
``` 
nmap -sP <IP_ADDRESS>/24 

Example: nmap -sP 192.168.100.0/24 
```

</br>References:
* [NMAP Cheat Sheet No. 1](https://www.stationx.net/nmap-cheat-sheet/)</br>
