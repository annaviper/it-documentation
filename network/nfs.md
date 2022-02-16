# Network File System
Allows a system to share directories and files with others over a network.

## Enumeration
Establishes an active connection to the target hosts to discover potential attack vectors in the system, and the same 
 can be used for further exploitation of the system.

### nfs-common
```bash
sudo apt install nfs-common
```
List the NFS shares:
```bash
/usr/sbin/showmount -e [IP]
```
Create a directory on your machine to mount the share to:
```
mkdir /tmp/mount
```
1. Create mount point: the folder can be anywhere on the system.
2. `mount` to connect the NFS share to the mount point
```bash
sudo mount -t nfs IP:share /tmp/mount/ -nolock
```
|   Flag	|   	|  
|---	|---	|
| -t nfs | type of device to mount |
| IP:share | ip of NFS serve and name of the share to mount	|
| -nolock | not to use NLM locking	|

# Exploitation
    NFS Access ->
 
         Gain Low Privilege Shell ->
 
             Upload Bash Executable to the NFS share ->
 
                 Set SUID Permissions Through NFS Due To Misconfigured Root Squash ->
 
                     Login through SSH ->
 
                         Execute SUID Bit Bash Executable ->
 
                             ROOT ACCESS1. 

- copy bash from Downloads to NFS `https://github.com/TheRealPoloMints/Blog/blob/master/Security%20Challenge%20Walkthroughs/Networks%202/bash`
- The copied bash shell must be owned by a root user, you can set this using "sudo chown root bash"
- add the SUID bit permission to the bash executable we just copied to the share using "sudo chmod +s bash" other options +x +r
  (s s. s(setuid) means 'set user ID upon execution'.)
- 