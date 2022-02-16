## MetaSploit
![metasploit](https://i.imgur.com/iYuiWvP.png)
Start
```
msfconsole -q
```
Check connection to database
```
db_status
```
Find a module
```
search module_name

use module_name
```
Once in the module, we can use:
```
info

options

setg RHOSTS ip_address

run
```