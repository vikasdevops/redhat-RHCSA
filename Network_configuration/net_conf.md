## Displaying IP addresses
```sh
$ ip addr show eth0     ## eth0 is device of Ethernet
$ ip -s link show eth0  ## -s is statics ip commanand
$ ip route              ## routing information
$ ping 172.25.21.0.254
```
## ports
```sh
$ ss -ta                ## socket statics
```
## nmacli configuring
```sh
$ nmcli con show        ## Displaying  connection
$ nmcli con show -- active
```
## connection with nmcli
```sh
$ nmcli con add con-name "statics" ifname eth0  
$ nmcli con add con-name "statics" ifname eth0 autoconnect no type ethernet ipv4 172.23.9.10/24 gw4 172.25.0.254     ## add ipv4 and gateway addresses
  
