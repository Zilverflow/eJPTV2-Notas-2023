#### Nmap Scripts (No Credentials):
````bash
# Version of SMB
nmap -p 445 --script smb-os-discovery 10.0.2.15

# Identify SMB Protocol Dialects
nmap -p445 --script smb-protocols 10.0.2.15

# Find SMB security level information
nmap -p445 --script smb-security-mode 10.0.2.15

# Enum Shares
nmap -p445 --script smb-enum-shares 10.0.2.15

# Enum Users
nmap -p445 --script smb-enum-users.nse 10.0.2.15
````
#### Nmap Scripts (With Credentials):
````bash
# Enum Active Session
nmap -p445 --script smb-enum-sessions --script-args smbusername=administrator,smbpassword=password 10.0.2.15

# Enum Shares
nmap -p445 --script smb-enum-shares --script-args smbusername=administrator,smbpassword=password 10.0.2.15

# Enum Users
nmap -p445 --script smb-enum-users --script-args smbusername=administrator,smbpassword=password 10.0.2.15

# Server stats
nmap -p445 --script smb-server-stats --script-args smbusername=administrator,smbpassword=password 10.0.2.15

# Enum Domains
nmap -p445 --script smb-enum-domains --script-args

# Enum Groups
nmap -p445 --script smb-enum-groups --script-args

# Enum Services
nmap -p445 --script smb-enum-services --script-args

# Enum Shares & listing the content with ls
nmap -p445 --script smb-enum-shares,smb-ls --script-args
````
#### SMBMap
````bash
# Enum shares
smbmap -u guest -p "" -d . -H 10.0.2.15

# Listing
smbmap -H 10.0.2.15 -u Administrator -p 'password' -L

# Listing 'C$'
smbmap -H 10.0.2.15 -u Administrator -p 'password' -r 'C$'

# Upload file
smbmap -H 10.0.2.15 -u Administrator -p 'password' --upload '/root/shell''C$\shell'

# Download File
smbmap -H 10.0.2.15 -u Administrator -p 'password' --download 'C$\Users\Administrator\flag.txt'
````
#### smbclient
````bash
# Listing & Null session
smbclient -L 10.0.2.15 -N

````
#### Enum4linux
````bash
# Version
enum4linux -o 10.0.2.15

# SID Unix users
enum4linux -r -u "admin" -p "password1" 10.0.2.15

# Configured for printing ?
enum4linux -i 10.0.2.15
````
#### Enumerating Users SMB (Diferent ways)
````bash
# nmap
nmap -p445 --script smb-enum-users 10.0.2.15

# Metasploit
use auxiliary/scanner/smb/smb_enumusers

# rpcclient
rpcclient -U "" -N 10.0.2.15
enumdomusers

# enum4linux
enum4linux -U 10.0.2.15
````
#### Enumerating shares SMB (Diferent ways)
````bash
# Nmap
nmap --script smb-enum-shares -p445 10.0.2.15

# Metasploit
use auxiliary/scanner/smb/smb_enumshares

# Enum4linux
enum4linux -S 10.0.2.15

# smbclient
smbclient -L 10.0.2.15 -N
````
#### Enumerating domain groups (Diferent ways)
````bash
# Enum4linux
enum4linux -G 10.0.2.15

# rpcclient
rpcclient -U "" -N 10.0.2.15
enumdomgroups
````
