# Outcome
- Archive files and Directories with tar.
- Create a gzip tar archive /root/etcbackup.tar.gz of the /etc directory.
- Create a bzip2 tar archive /root/logbackup.tar.bz2 of the /var/log
 directory.
 - Create Archive directory and gzip it directory, compare original size with the compressed tar archive.
## Lab activity
```sh
$ tar cf archive.tar ansible
```
```sh
$ tar tf archive.tar
ansible/
ansible/a.txt
ansible/hot/
ansible/us.txt
ansible/vi/
ansible/root/
ansible/am
ansible/a2.txt
ansible/a3.txt
ansible/a4.txt
ansible/a1.txt
```
```sh
$ tar czf /root/etcbackup.tar.gz /etc
```
```sh
$ tar cjf /root/logbackup.tar.bz2 /var/log
```
```sh
$ tar cvf devops.tar devops
devops/
devops/a.txt
devops/hot/
devops/us.txt
devops/vi/
devops/root/
devops/am
devops/a2.txt
devops/a3.txt
devops/a4.txt
devops/a1.txt
```
```sh
$ du -sh devops.tar
12K	devops.tar
```
```sh
 $ gzip devops.tar
```
```sh
$ du -sh devops.tar.gz
4.0K	devops.tar.gz
```
```sh
$ ls -l devops.tar.gz
-rw-rw-r--. 1 root root 411 Jul 11 10:07 devops.tar.gz
```
