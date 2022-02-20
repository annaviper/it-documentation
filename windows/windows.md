# Active directory
Secure online authentication store.  

Azure Active Directory supports the following authentication methods:
- SAML (Security Assertion Markup Language)
- OAUTH 2.0
- OpenID Connect

## Group Policy Object
Adds additional controls to user accounts and computers.
To apply GPO:
```commandline
gpupdate /force
```

# Windows\System32 Folders
The System32 folder holds the important files that are critical for the operating system.  
The system  environment variable for the Windows directory is `%windir%`

# User Accounts, Profiles, and Permissions
- Start Menu and type Other User. A shortcut to System Settings > Other users
- Local User and Group Management: right click on Start menu > run > lusrmgr.msc

# User Account Control (UAC)
Note: UAC (by default) doesn't apply for the built-in local administrator account. 

A user doesn't need to run with high (elevated) privileges on the system to run tasks that don't require such privileges, such as surfing the Internet, working on a Word document, etc. When a user with an account type of administrator logs into a system, the current session doesn't run with elevated permissions. When an operation requiring higher-level privileges needs to execute, the user will be prompted to confirm if they permit the operation to run (shield symbol).

#  System Configuration
The System Configuration utility (MSConfig) is for advanced troubleshooting, and its main purpose is to help diagnose startup issues. 

# Computer Management `compmgmt`
3 primary sections: 
- System Tools: task scheduler, event viewer (audit trail), ...
- Storage
- Services and Applications.
- 
# System Information `msinfo32`
Technical specifications
- Hardware Resources
- Components
- Software Environment

# Resource Monitor `resmon`

# Command Prompt
```
hostname - computer
whoami - user
ipconfig - network address settings for computer
command /? - help
cls - clear
netstat - protocol statistics and current TCP/IP network connections
net - manage network resources. /? doesnt work, need to use net help or net help command
```

# Registry Editor `regedit`
Windows registry database stores many important operating system settings. Built-in and inserted hardware also stores 
information in the registry when the driver is installed; this driver is called up every time the system is booted up.  

A feature of Powershell is that you can browse the registries. You can do that by typing:   
```
cd <REG DB>" (Example: cd HKLM:\)
```
Windows also has a builtin tool named "reg" which can be used from the command line to add, remove, query, import, export, etc registry keys.  

![](https://i.imgur.com/dqckLsA.png)
# Folders in C:  

| Folder |   	|  
|---	|---	|
| PerfLogs | system issues and other reports regarding performance |
| Program Files | location where programs install	|
| Program Files (x86) |  |
| Users | Created users. It also stores users generated data (Ex: Saving a file on your Desktop) |
| Windows | Contains the code to run the operating system and some utility tools	|

## icacls \<folder>  
Tool you can use to check the files or folder permissions.

![icacls](assets/icacls.jpg)

![setowner](https://i.imgur.com/mFlrbGE.png)




