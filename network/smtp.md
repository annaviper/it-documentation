# Simple Mail Transfer Protocol
Three basic functions:
- It verifies `who` is sending emails through the SMTP server.
- It `sends` the outgoing mail
- If the outgoing mail can't be delivered it sends the message back to the sender

# POP and IMAP (Email protocols)
POP's more simplistic approach of downloading the inbox from the mail server, to the client.  
IMAP will synchronise the current inbox, with new mail on the server, downloading anything new. This means that changes 
to the inbox made on one computer, over IMAP, will persist if you then synchronise the inbox from another computer.

![SMTP](https://github.com/TheRealPoloMints/Blog/blob/master/Security%20Challenge%20Walkthroughs/Networks%202/untitled.png?raw=true)

SMTP handshake over port 25. 

# Enumeration
Scan a range of IP addresses and determine the version of any mail servers it encounters.  
Options:
- `smtp_version` from MetaSploit
- `smtp-user-enum`

| Command	|   	|  
|---	|---	|
| VRFY  | confirm the names of valid users |
| EXPN | reveal actual address of user's aliases and lists of e-mail (mailing lists)	|

# Resources
[Cheatsheet](https://nullsec.us/top-1-000-tcp-and-udp-ports-nmap-default/)
