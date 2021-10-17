# NMAP Cheat Sheet 

**NMAP brute forces DNS hostnames guessing subdomains</br>**
```
nmap -Pn --script=dns-brute <DOMAIN_NAME>

Example: nmap -Pn --script=dns-brute domain.com
```

</br>**NMAP whois query</br>**
```
nmap --script whois* <DOMAIN_NAME> 

Example: nmap --script whois* domain.com
```

</br>**NMAP detect cross site scripting CSS vulnerabilities**
```
nmap -p80 --script http-unsafe-output-escaping <DOMAIN_NAME>

Example: nmap -p80 --script http-unsafe-output-escaping domain.com 
```

</br>**NMAP check for SQL injections**
```
nmap -p80 --script http-sql-injection <DOMAIN_NAME> 

Example: nmap -p80 --script http-sql-injection domain.com
```

</br>**NMAP scan for vulnability**
```
sudo nmap --script vuln <TARGET_IP> 

Example: sudo nmap --script vuln 192.168.100.1
```

</br>**NMAP use as decoy**
``` 
sudo nmap -sS -D <DECOY IP_ADDRESS> <TARGET_IP> 

Example: sudo nmap -sS -D 172.168.100.1 192.168.100.1 
```

</br>**NMAP use stealthy to scan network with live IP address with open port**
``` 
sudo nmap -sS -p <PORT 1>,<PORT 2> <TARGET_IP/24> 

Example: sudo nmap -sS -p 80, 443 192.168.100.0/24> 
```

</br>**NMAP scan live IP address on the network**
``` 
nmap -sP <IP_ADDRESS>/24 

Example: nmap -sP 192.168.100.0/24 
```

</br>References:
* [NMAP Cheat Sheet No. 1](https://www.stationx.net/nmap-cheat-sheet/)</br>
