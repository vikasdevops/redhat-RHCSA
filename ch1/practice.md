# some practice question of REDHAT RHCSA
++++++++++++++++++++++++++++++++++++++++++++++++

## How to copy in redhat command :
-----------------------------------------------
- **copy /etc/fstab to /var/tmp name admin, the user1 could read, write and modify it , while user2 without any permission**
```sh
 $ cp/etc/fstab /var/tmp/fstab    
 $ setfacl -m u:suer1:rwx /var/tmp/fstab      ## -m is used for modify
 $ setfacl -m u:user2:--- /var/tmp/fstab      ## setfacl is used permission, --- no permission
 $ ls -l

 ```
## How to add user
```sh
  $ useradd prince                           ## useradd command to add user
  $ ls -l/home
  ```
## set passwd in user
  ``sh
  $ passwd prince

 ** want to see passwd **
 -------------------------------------------------
```sh
 tail -2 /etc/passwd
```

## How to add group
 --------------------------------------------------
```sh
  $ groupadd artists

  $ tail -5 /etc/group
```
