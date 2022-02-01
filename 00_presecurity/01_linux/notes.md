# SSH
ssh username@ipaddress

# Intro
| Symbol      | Description | Notes |
| ----------- | ----------- | ---------- |
| cd      | change directory       |
| pwd      | print working directory       |
| ls      | listing       | -a for all, 
| | | -l columns
| | | -lh permissions
| cat   | output contents        |
| man      | manual        |

# Files
| Symbol      | Description | Notes |
| ----------- | ----------- | ---------- |
| find  | 
| grep | what where  | 
| wc - |count # of entries  | 
| wc -l  | 

| Symbol      | Description | Notes |
| ----------- | ----------- | ---------- |
| touch      | create file       |
| mkdir   | create folder        |
| cp      | copy        |
| mv   | move/rename        |
| rm      | remove        | -R for directory
| file   | determine the type of a file        |

# common directories
| Symbol      | Description |
| ----------- | ----------- |
| /etc      | commonplace location to store system files that are used by your operating system |
| /var   | stores data that is frequently accessed or written by |
| /root      | home for the "root" system user |
| /tmp   | useful in pentesting: any user can write to /tmp by default |

# operators
| Symbol      | Description |
| ----------- | ----------- |
| &      | run commands in the background of your terminal       |
| &&   | combine multiple commands together in one line of your terminal        |
| >      | redirector. overwrites        |
| >>   | redirector + append        |

# permissions
| Symbol      | Description | Notes |
| ----------- | ----------- | ------- |
| su      | switch user | -l username login

# Utilities
## Downloading Files
Download files from the web via HTTP  
```
wget https://assets.tryhackme.com/additional/myfile.txt
```

## Transferring Files From Your Host - SCP (SSH)
Secure copy between systems.  
  
- from our machine to a remote machine (source and destination)  
```
scp source_file.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```
- from remote machine  
```
scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt name_to_store_file_in_our_sytem.txt
```

## Serving Files From Your Host - WEB
Python module `HTTPServer`: turns your computer into a quick and easy web server that you can use to serve your own files, where they can then be downloaded by another computing using commands such as `curl` and `wget`.
- Start a web server
```
python3 -m  http.server
```
- Download a file
```
wget http://127.0.0.1:8000/file_path
```

# Processes 101
| Symbol      | Description | Example |
| ----------- | ----------- | ------- |
| ps | provide a list of the running processes as our user's session | 
| ps aux | processes run by other users and those that don't run from a session | 
| top | statistics instead of a one-time view | 
| kill | statistics instead of a one-time view | kill pid_number
SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand  
SIGKILL - Kill the process - doesn't do any cleanup after the fact  
SIGSTOP - Stop/suspend a process  

## Getting Processes/Services to Start on Boot
```
systemctl [option] [service]
```
Option: 
- Start
- Stop
- Enable - start on the boot-up of the system
- Disable  
  
Example:
```
systemctl start apache2
```
To background a process:
`Ctrl + Z` or `command &`.  
To foreground a process: `fg`

# Automation
min hour day month day/week cmd  
Example: copy Documents every 12 hours
```
0 *12 * * * cp -R /home/cmnatic/Documents /var/backups/
```
Crontabs can be edited by using `crontab -e`, where you can select an editor (such as Nano) to edit your crontab.

# Package management
Example: add Sublime to Ubuntu.  
1. Let's download the GPG key and use apt-key to trust it:  
```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```
2. Add Sublime Text 3's repository to our apt sources list.  
- 2.1. Let's create a file named `sublime-text.list` in `/etc/apt/sources.list.d` and enter the repository information.  
![img](https://assets.tryhackme.com/additional/linux-fundamentals/part3/sources1.png)

- 2.2. Use Nano to add & save the Sublime Text 3 repository into this newly created file:
![img](https://assets.tryhackme.com/additional/linux-fundamentals/part3/sources2.png)
- 2.3. Update apt to recognise this new entry: `apt update`.
- 2.4. Install the software that we have trusted and added to apt: `apt install sublime-text`  
 
To remove a package:  
`add-apt-repository --remove ppa:PPA_Name/ppa`  
or  
by manually deleting the file that we previously fulfilled.  
Once removed, we can just use `apt remove [software-name-here]` i.e. `apt remove sublime-text`

# Logs
Located in the `/var/log directory`