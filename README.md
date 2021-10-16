# Linux (Kali/Ubuntu) Command Cheat Sheet

* How to unzip file in Ubuntu Linux
```
unzip filename.zip
```

* How to show Java version in Linux
```
java -version
```

* How install Apache2 in Ubuntu Linux
```
sudo apt update
sudo apt install apache2
```

* How start Apache2 in Ubuntu Linux
```
sudo /etc/init.d/apache2 start 
```

* How stop Apache2 in Ubuntu Linux
``` 
sudo /etc/init.d/apache2 stop 
```

* How to show Ubuntu Linux version
```
lsb_release -a
```

* How to show Kali Linux version
```
cat /etc/*release*
```

* How to create folder shortcut in Ubuntu Linux
1. Open the folder to make a shortcut
2. Right click and open the terminal
3. Type the command below
```
ln -s $PWD ~/Desktop/
```

* How to share folder between Ubuntu Linux and Windows 10 Pro 64bit
</br></br>
Ubuntu Linux Environment
1. Open the folder to share with Windows 10 Pro
2. Right click and open the terminal
3. Type the command below
```
sudo mount -t cifs -o username=test //192.168.100.71/a$ /home/test/Desktop/SharedFolder

Where:
192.168.100.71 - is the IP address of Windows 10 Pro
a$             - shared folder from Windows 10 Pro, 
SharedFolder   - shared folder from Linux

Note: Make sure 'KaliShare' folder in windows 10 Pro environment is accessible to the network.
```

* How to share folder between Kali Linux and Windows 10 Pro 64bit
</br></br>
Kali Linux Environment
1. Open the folder to share with Windows 10 Pro
2. Right click and open the terminal
3. Type the command below
```
mount.cifs //eric-dell/KaliShare /root/Desktop/a -o user=kali

Where:
KaliShare - shared folder from Windows 10 Pro
a         - shared folder from Linux

Note: Make sure 'KaliShare' folder in windows 10 Pro environment is accessible to the network.
```

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
