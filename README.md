# Linux (Kali/Ubuntu) Command Cheat Sheet
* How to share folder between Kali Linux and Windows 10 Pro 64bit
Kali Linux Environment
1. Open the folder to share with Windows 10 Pro
2. Right click and open the terminal
3. Type the command below
```
mount.cifs //eric-dell/KaliShare /root/Desktop/a -o user=kali
```
Notes: Make sure 'KaliShare' folder in windows 10 Pro environment is accessible to the network.

* How to print the current directory
```
pwd
```

* How to display all the users and their path
```
cat /etc/passw
```

* How to list down all directories in the current directory
```
ls
```

# Metasploit Cheat Sheet
* Metasploitable login credentials</br>
```
Username: msfadmin
Password: msfadmin
```

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

# Setting Laboratory References
</br>**6. How to - Exit mouse and keyboard on VMware Player 10**</br>
press Ctrl + Alt

</br>**5. How to - Chrome Install on Kali Linux**</br>
``` 
apt update
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
apt install ./google-chrome-stable_current_amd64.deb
google-chrome --no-sandbox 
 ```

</br>**4. How to - Chrome Uninstall on Kali Linux**</br>
``` 
dpkg --list | grep google
sudo apt --purge remove google-chrome-stable
dpkg --list | grep google
```


</br>**3. How to - Linux (Kali and Ubuntu) update and upgrade**</br>
``` sudo apt update && sudo apt upgrade ```


</br>**2. Kali Operating System - default login credentials**</br>
```
Username: kali
Password: kali
```

</br>**1. Installation of Virtual Machine** </br>
Download links:
* [Kali Linux - Operating System (Option 1)](https://www.kali.org/get-kali/#kali-virtual-machines)</br>
* [Ubuntu - Operating System (Option 2)](https://ubuntu.com/download/desktop)</br>
* [VMware Player - Virtual Machine (Option 1)](https://www.vmware.com/asean/products/workstation-player/workstation-player-evaluation.html)</br>
* [Virtual Box - Virtual Machine (Option 2)](https://www.virtualbox.org/wiki/Downloads)</br>
