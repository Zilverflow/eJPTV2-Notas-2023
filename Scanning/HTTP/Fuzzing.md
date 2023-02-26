#### dirb
````bash
dirb http://10.0.2.15
````
#### wfuzz
````bash
wfuzz -c -w /usr/share/wordlists/dirb/common.txt --hc=404  https://10.0.2.15/FUZZ
````
#### gobuster
````bash
gobuster dir -u http://10.0.2.15 -w /usr/share/wordlists/dirb/common.txt

# Ignore status 404,403
gobuster dir -u http://10.0.2.15 -w /usr/share/wordlists/dirb/common.txt -b 403,404

# Files
gobuster dir -u http://10.0.2.15 -w /usr/share/wordlists/dirb/common.txt -b 403,404 -x .php,.xml,.txt -r
````
#### Metasploit
````bash
use auxiliary/scanner/http/brute_dirs
set RHOSTS 10.0.2.15
exploit
````
