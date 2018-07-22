# Firewalld Zones
- - trusted
- - home
- - internal
- - work
- - public
- - external
- - dmz
- - block
- - drop
##### manual page
- firewalld.zones(5)manual page.
## Configure firewalld settings
- graphic firewall.config tool
- command line firewall-cmd
## firewall-cmd
```sh
$ sudo firewall-cmd --set-default-zone=dmz
$ sudo firewall-cmd --permanent --zone=internal --add-source=192.9.0/24
$ sudo firewall-cmd --permanent --zone=internal --add-service=mysql
$ sudo firewall-cmd --reload
```
