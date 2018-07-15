# Outcomes:
- The psacct service is enabled and running on the system, and the rsyslog service is disabled and no longer running on the system.
# Lab Activity:
- start the psacct service
```sh
$ sudo systemctl status psacct
$ sudo systemctl start psacct
```
- start at system boot
```sh
$ sudo systemctl enable psacct
$ sudo systemctl status psacct
```
- Stop rsyslog service
```sh
$ sudo systemctl stop rsyslog
$ sudo systemctl status rsyslog
```
- rsyslog service so that it does not start at system boot
```
$ sudo systemctl disable rsyslog
$ sudo systemctl status rsyslog
```
________________________________________
