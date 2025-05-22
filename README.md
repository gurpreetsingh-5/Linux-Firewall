# Linux-Firewall

```
rpm -qa | grep firewalld #check firewall
dnf install firewalld # if not presnt
systemctl start/enable firewalld
systemctl stop/disable firewalld
systemctl status firewalld
systemctl restart firewalld	
firewall-cmd  --list-all                 # check the rules of firewalld
firewall-cmd  --grt-services             # listing of all the services firewalld is aware of
firewall-cmd  --reload                   # to reload the config of firewalld
firewall-cmd  --get-zones                # firewall has multiple zones
firewall-cmd  --get-active-zones         # to see the list of active zones
firewall-cmd  --zone=public –list-all     # to get firewall rules for a specific zone

```

```

```
