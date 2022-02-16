[Cheatsheet](https://www.stationx.net/nmap-cheat-sheet/)

# Port scanning
`-A` Enables OS detection, version detection, script scanning, and traceroute  
`-p-` Scan all ports  
`-v` or `-vv` Verbose
```bash
nmap -A -p- ip_address
```
```bash
nmap -A -p- ip_address | grep open
```