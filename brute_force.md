# Hydra

Hydra is a very fast online password cracking tool, which can perform rapid dictionary attacks against more than 50 
Protocols, including Telnet, RDP, SSH, FTP, HTTP, HTTPS, SMB, several databases and much more. Hydra comes by default 
on both Parrot and Kali, however if you need it, you can find the GitHub [here](https://github.com/vanhauser-thc/thc-hydra).

Hydra uses dictionary attacks primarily, both Kali Linux and Parrot OS have many different wordlists in the 
`/usr/share/wordlists` directory. Likewise I recommend checking out `SecLists` for a wider array of other wordlists that 
are extremely useful for all sorts of purposes, other than just password cracking. E.g. subdomain enumeration.

Example:
```bash
hydra -t 4 -l USERNAME -P /usr/share/wordlists/rockyou.txt -vV MACHINE_IP PROTOCOL
```
|   Flag	|   	|  
|---	|---	|
|  -t 4 |Number of parallel connections per target |
|   -l [user]	| Points to the user who's account you're trying to compromise |
|   -P [path to dictionary]	| Points to the file containing the list of possible passwords |
|   -vV 	| Sets verbose mode to very verbose, shows the login+pass combination for each attempt |
|   ftp / protocol  	| Sets the protocol |

