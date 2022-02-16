# Workflow
1. `nmap` port scan to check open ports
2. `metasploit` enumeration to check SMTP: `smtp_version` and `smtp_enum`
3. now we have a SSH port open, a user account name, type of SMTP server and OS.
4. Use this information to try and [`bruteforce`](brute_force.py) the password of the SSH login for our user using Hydra.