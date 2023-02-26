#### WEB information
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
#### Web server enumeration (Metasploit)
````bash
# header
auxiliary/scanner/http/http_header

# Robots.xtx
auxiliary/scanner/http/robots_txt

# Brute dir
auxiliary/scanner/http/brute_dirs

# Dir scanner
auxiliary/scanner/http/dir_scanner

# Dir listing
auxiliary/scanner/http/dir_listing

# Files dir
auxiliary/scanner/http/files_dir

# HTTP put
auxiliary/scanner/http/http_put

# HTTP login
auxiliary/scanner/http/http_login

# Enum users
auxiliary/scanner/http/apache_userdir_enum
````