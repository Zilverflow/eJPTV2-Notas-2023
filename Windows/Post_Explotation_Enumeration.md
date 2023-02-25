# Host Discovery - Enumeration

#### System information:
````bash
# Manual
hostname
systeminfo

# Meterpreter
sysinfo
````
#### Users & Groups:
````bash
# Manual
whoami
whoami /priv
net users
net user administrator
net localgroup
net localgroup administrators

# Meterpreter
getuid
getprivs
use post/windows/gather/enum_logged_on_users
`````
#### Network Information:
````bash
ipconfig
ipconfig /all
route print
arp -a
netstat -ano
````
#### Firewall state:
````bash
netsh advfirewall show allprofiles
````
#### Processes & Services:
````bash
ps 
net start
wmic service list brief
tasklist /SVC
schtasks /query /fo LIST
schtasks /query /fo LIST /v
````
#### Automating Enumeration
````bash
# Metasploit
post/windows/gather/win_privs
post/windows/gather/enum_logged_on_users
post/windows/gather/checkvm
post/windows/gather/enum_applications
post/windows/gather/enum_computers
post/windows/gather/enum_patches

````



