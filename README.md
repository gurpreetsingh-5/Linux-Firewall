# Linux-Firewall
#### *Basic CMD*
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

#### *To add or remove a service temporary*

```
firewall-cmd --add-service=<name_of_service>
firewall-cmd --remove-service=<name_of_service>
firewall-cmd --reload # after reload add service remove autometically
```

#### *To add or remove a service parmanent*

```
firewall-cmd --add-service=<name_of_service> --parmanent
firewall-cmd --remove-service=<name_of_service> --parmanent
systemctl restart firewalld.service	
```

#### *To add or remove a port*

```
firewall-cmd --add-port=20201/tcp
firewall-cmd --remove-port=20201/tcp
```

#### *To block or unblock incoming traffic from an IP*
```
firewall-cmd --add-rich-rule=’rule family=”ipv4” source address=”192.168.0.0” reject’
firewall-cmd --remove-rich-rule=’rule family=”ipv4” source address=”192.168.0.0” reject’
```

#### *to block or unblock outgonig traffic from an IP or URL*

```
sudo dnf install bind-utils -y
host -t a www.fb.com
firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -d <ip> -j DROP
sudo firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -d <ip> -j DROP --permanent # for parmanent
ping facebook.com

sudo firewall-cmd --direct --remove-rule ipv4 filter OUTPUT 0 -d <ip> -j DROP
ping facebook.com

```

#### *to block or unblock ICMP incoming traffic*

```
firewall-cmd --add-icmp-block-inversion

firewall-cmd --remove-icmp-block-inversion
```
