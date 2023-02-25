# Enumeration
#### Version SSH
````bash
# nmap
nmap -sV -p 22 10.0.2.15

# netcat
nc 10.0.2.15 22
````
#### Nmap
````bash
# encryption_algorithms
nmap -p 22 --script ssh2-enum-algos 10.0.2.15

# ssh-rsa host key
nmap -p 22 --script ssh-hostkey --script-args ssh_hostkey=full 10.0.2.15

# authentication method for user admin
nmap -p 22 --script ssh-auth-methods --script-args="ssh.user=admin" 10.0.2.15

# Fetch the flag from /home/kali/FLAG (Cat with nmap)
nmap -p 22 --script=ssh-run --script-args="ssh-run.cmd=cat /home/kali/FLAG, ssh-run.username=admin,ssh-run.password=" 10.0.2.15
````