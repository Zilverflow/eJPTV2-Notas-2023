#### WEB
````bash
# Whatweb
whatweb 10.0.2.15

# http
http 10.0.2.15
````
#### Version 
````bash
# nmap
nmap -sV -p80 -script banner 10.0.2.15

# Metasploit
msfconsole
use auxiliary/scanner/http/http_version
set RHOSTS 10.0.2.15
exploit
````
#### What web 
````bash
# Curl
curl http://10.0.2.15/

# browsh
browsh --startup-url 10.0.2.15

# lynx
lynx http://10.0.2.15
````
