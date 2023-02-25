# Passive Information Gathering
#### IP addresses:
````bash
host google.com
````
#### Directories hidden from search engines:
````bash
robots.txt
sitemap.xml
````
#### Web Technologies being used:
````bash
whatweb google.com
````
# Extensions Firefox
````bash
BuiltWith
Wappalizer
````
#### Whois Enumeration:
[Whois](https://who.is/)
````bash
# Linux
whois google.co
````
#### Website Footprinting:
[Netcraft](https://www.netcraft.com/)

#### DNS Recon
[dnsdumpster](dnsdumpster.com)
````bash
dnsrecon -d google.com
````
#### WAF With wafw00f (Web application firewall)
[dnsdumpster](dnsdumpster.com)
````bash
wafw00f google.com
````
#### Subdomain Enumeration With Sublist3r:
````bash
sublist3r -d google.com
````
#### Google Dorks:
````bash
site
intitle
inurl
Filetype
ext
````
#### Email Harvesting With theHarvester:
````bash
theHarvester -d google.com -b bing,yahoo
````
