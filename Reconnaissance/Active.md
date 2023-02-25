# Active Information Gathering
#### Host Discovery:
````bash
# Nmap
sudo nmap -sn 192.168.2.0/24

# netdiscover
sudo netdiscover -i eth0 -r 192.168.2.0/24
````
#### Port Scanning With Nmap:
````bash
nmap -Pn -F 10.0.2.10

# Parameters
- -F = most used
- -Pn = quitar el ping
- -p- = All ports
- -sU = UDP
- -v = Verbose
- -sV = Service and version
- -O = OS
- -sC = basic script
- -T5 = (from 0 to 5 - 5 is more fast)
- -oN = export to nmap.
- -oX archivo.xml= export to xml
````
