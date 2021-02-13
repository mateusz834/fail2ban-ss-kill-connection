# fail2ban-ss-kill-connection
# Usage

Copy:
```
cp ./ss-kill-custom.conf /etc/fail2ban/action.d/
cp ./ss-kill-subnet-custom.conf /etc/fail2ban/action.d/
```

Adjust jail.local file <br>
/etc/fail2ban/jail.local
```
[ftp]
(...)
action = (your normal action)
         ss-kill-custom[port="22,5000:51000]
         
[ftp-subnet]
(...)
action = (your normal action)
         ss-kill-custom[port="22,5000:51000,mask4="24",mask6="64"]


```
