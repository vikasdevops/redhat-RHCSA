## yum manager
**configuration file: /etc/yum.repos.d**
### create /etc/yum.repos.d  directory
- create file any name but extension should be .repo  
- file create errata.repo
- add entry
[updates]
name=Red Hat updates
baseurl=http://con/example.com/rhel7.0/x86_64/errata
enable=1
gpgcheck=0

## yum install packages and configuration
```sh
$ yum install httpd
$ yum list kernel
$ yum remove httpd
$ yum group list
```
## viewing history
- logged in /var/log/yum.log
```sh
$ tail -5 /var/log/yum.log
$ yum history
$ yum repolist all
```
