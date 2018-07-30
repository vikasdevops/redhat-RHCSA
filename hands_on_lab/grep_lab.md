## Outcome
- Find files and directory of yum in etc directory.
- Find files and directory which match form c and t.
- Create the directory ansible, Inside it make file dev_p
**write this text on the file**: devops is the user of machine    
ansible tool for ansible devops is automation tool  
ansible is better configure tool
- Find the word in file devops.


## Labs
```sh
$  ls -l | grep yum
drwxr-xr-x.  6 root root     4096 Dec 22  2017 yum
-rw-r--r--.  1 root root      813 Apr 15  2014 yum.conf
drwxr-xr-x.  2 root root       22 Feb 14 23:23 yum.repos.d
```

>$ ls -l | grep c.*t  
drwxr-xr-x.  3 root root       97 De**c 22  2017 abrt**  
-rw-r--r--.  1 root root       16 De**c 22  2017 adjt**ime   
-rw-------.  1 root root      541 Jan   27  2014 ana**cront**ab   
drwxr-xr-x.  2 root root       31 De**c 22  2017 at**-spi2   
drwxr-xr-x.  2 root root       17 De**c 23  2017 rwt**ab.d

:more

>$ cat dev_p | grep devops   
**devops** is the user of machine   
**devops** is automation tool
