## Syslog Fils
- The facility which are available are documents by the rsyslog.conf
- Configured by the file /etc/rsyslog.conf and by *.conf files in /etc/rsyslog.d
## Log files
```sh
$ tail -f /var/log/secure
```
## Finding event with journalctl
```sh
$ sudo journalctl
```
- Show the last 10 log entries
```sh
journalctl -n 5
```
- Got recorded today
```
journalctl --since today
```
- Entries from 10th February 2018  20:30:00 to 14 February 2018 12:00:00:
```sh
$ sudo journalctl --since "2018-02-10 20:30:00" --until "2018-02-14 12:00:00"
```
-  Warning messages
```sh
$ sudo journalctl -p Warning
```
## Configuring and monitoring chronyd
- Configured in NTP servers
- Configuring file in /etc/chronyd.conf
```sh
$ sudo vi /etc/chronyd.conf
server devops.net.com iburst
```
```sh
$ sudo systemctl resert chronyd
$ chronyc sources -v
```
 
