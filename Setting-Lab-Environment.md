# Reference - Linux Command
**27. How to sort text from files in Linux**
```
sort 1.txt | uniq -u | anew results_Sort.txt
```

**26. How do I fix "$'\r': command not found" errors running Bash scripts in WSL?**

Install 
```
sudo apt-get install dos2unix
```
then
```
dos2unix your_file.sh
```

**25.How to show Java version in Linux**
```
java -version
```

**24. How install Apache2 in Ubuntu Linux**
```
sudo apt update
sudo apt install apache2
```

**23. How start Apache2 in Ubuntu Linux**
```
sudo /etc/init.d/apache2 start 
```

**22. How stop Apache2 in Ubuntu Linux**
``` 
sudo /etc/init.d/apache2 stop 
```

**21. How to show Ubuntu Linux version**
```
lsb_release -a
```

**20. How to show Kali Linux version**
```
cat /etc/*release*
```

**19. How to print the current directory**
```
pwd
```

**18. How to display all the users and their path**
```
cat /etc/passw
```

**17. How to list down all directories in the current directory**
```
ls
```

**16. How to unzip file**

 ```
 unzip filename.zip
 ```

**15. How to convert dos file to linux**

 ```
 sudo apt-get install dos2unix
 ```

**14. Set Golang PATH**
```
Open terminal
vi ~/.bashrc
Shift + G 

export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$HOME/.local/bin:$PATH
```

**13. Update Snap-Store**

option 1:
```
sudo snap remove snap-store
sudo snap install snap-store
```
option 2:
```
sudo killall snap && sudo snap refresh
```
**12. Unistall Firefox**
```
sudo snap remove firefox
```
or
```
sudo apt-get purge firefox
```

**11. Unistall ThunderBird**
```
sudo snap remove ThunderBird
```
or
```
sudo apt-get purge ThunderBird
```

**10. Update Ubuntu**
```
sudo apt update && sudo apt upgrade
```
**9. Install Git**
```
sudo apt update
sudo apt upgrade -y
sudo apt install git
git --version
```
**8. Install Python environment and activate**

option 1:
```
python3 -m venv PyEnv
sudo apt install python3.10-venv
```
option 2:
```
source PyEnv/bin/activate
```
**7. Make a desktop hortcut**
```
ln -s $PWD ~/Desktop/
```
**6. Install Python**
```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.9
python3.9 --version
```
**5. Install python virtualenv**
```
pip3 install virtualenv
```
**4. Remove virtualenv**
```
sudo apt-get remove virtualenv  
sudo apt-get remove --auto-remove virtualenv
```
**3. Copy Github repository**
```
git clone https://github.com/s0md3v/Arjun.git
```
**2. Install python requirements**
```
pip3 install -r requirements.txt
```
**1. Remove duplicate and sort data inside the text file**
```
sort input_file | uniq > output_file
```

# Reference - Others 
1. [Foxy Proxy issue on Firefox with Burp Suite](https://portswigger.net/burp/documentation/desktop/external-browser-config/certificate/ca-cert-firefox)
2. Running Burp Suite for the first time command 
```
java -jar burploader.jar
sudo apt-get install openjdk-11-jdk
```
3. To lunch Burp Suite Professional
```
/usr/lib/jvm/java-11-openjdk-amd64/bin/java --illegal-access=permit -Dfile.encoding=utf-8 -javaagent:burploader.jar -noverify -jar burpsuite_pro_v2021.8.jar
```

# Reference - Linux (Kali/Ubuntu) Command 

</br>**How to Install GO in Kali Linux**
1. Download the latest Go installation file [https://go.dev/doc/install](https://go.dev/doc/install)
2. Open the terminal and enter the following commands:
```
tar -C /usr/local -xzf go1.17.5.linux-amd64.tar.gz
echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.profile
echo "export GOPATH=~/.go" >> ~/.profile 
source ~/.profile  
go version     
```

</br>**How to one click folder or file in Kali Linux**
1. Go to <kbd>File Manager Settings</kbd>
2. Under <kbd>File Manager Preference</kbd>, under <kbd>Behavior</kbd>, select <kbd>Single click to activate items</kbd>
3. Go to <kbd>Desktop Settings...</kbd>, select <kbd>Icons</kbd> tab
4. Check <kbd>Single click to activate items</kbd>

</br>**How to share folder between Ubuntu Linux and Windows 10 Pro 64bit**
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

</br>**How to share folder between Ubuntu and Windows 10 Pro 64bit**
</br></br>
Ubuntu Linux Environment
1. Make sure samba server is already installed
2. Open a folder
3. Navigate to 'Other Locations'
4. On the 'Connect Server' type
```
smb://<Windows PC IP>/<Windows Shared Folder Name>
```

</br>**How to share folder between Kali Linux and Windows 10 Pro 64bit**
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

# Reference - Setting Laboratory References

</br>**How to expand/increase Ubuntu VM hard disk on VMware Player 6** 
1. Shutdown Ubuntu OS on the VMware.
2. On VMware Player 6, go to "Edir virtual machine settings".
3. Select 'Hard Disk', click 'Expand' button an enter the desired size.
4. Run the Ubuntu OS again.
5. On the Ubuntu desktop, click 'Show Applications' and select 'System Monitor', for checkin
6. Open the terminal and type
```
sudo -s
```
7. Enter the appropriate password
8. Install 'gparted' by typing the following command
```
apt-get install gparted
```
9. Go to 'Show Applications' and select 'gparted'
10. Do the necessary adjustment


</br>**How to - set keyboard shorcut to display all running process in Ubuntu**</br>
1. Go to 'Settings'
2. Select 'Keyboad Shorcut'
3. Scroll down to 'Custom Shortcut'
4. Click the '+'
5. Enter the preferred 'Name' and keyboard shortcut
6. On the 'Command' type
```
gnome-system-monitor
```

</br>**How to - Exit mouse and keyboard on VMware Player 10**</br>
Press <kbd> Ctrl </kbd> + <kbd> Alt </kbd>

</br>**How to - Chrome Install on Kali Linux**</br>
``` 
apt update
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
apt install ./google-chrome-stable_current_amd64.deb
google-chrome --no-sandbox 
 ```

</br>**How to - Chrome Uninstall on Kali Linux**</br>
``` 
dpkg --list | grep google
sudo apt --purge remove google-chrome-stable
dpkg --list | grep google
```

</br>**How to - Linux (Kali and Ubuntu) update and upgrade**
``` 
sudo apt update && sudo apt upgrade 
```

</br>**How to - Kali Operating System - default login credentials**

```
Username: kali
Password: kali
```

</br> **How to Installation of Virtual Machine** </br>
Download links:
* [Kali Linux - Operating System (Option 1)](https://www.kali.org/get-kali/#kali-virtual-machines)</br>
* [Ubuntu - Operating System (Option 2)](https://ubuntu.com/download/desktop)</br>
* [VMware Player - Virtual Machine (Option 1)](https://www.vmware.com/asean/products/workstation-player/workstation-player-evaluation.html)</br>
* [Virtual Box - Virtual Machine (Option 2)](https://www.virtualbox.org/wiki/Downloads)</br>
