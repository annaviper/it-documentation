At a high-level, VPN works by routing our connecting device's internet connection through the target VPN's private 
server instead of our internet service provider (ISP). When connected to a VPN, data originates from the VPN server 
rather than our computer and will appear to originate from a public IP address other than our own.

![vpn](https://academy.hackthebox.com/storage/modules/77/GettingStarted.png)
HTB:
```
sudo openvpn user.ovpn
```
Networks accessible via the VPN. accessible via the VPN:
```
netstat -rn
```