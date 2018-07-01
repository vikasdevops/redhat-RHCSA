## outcomes
- Create a devops directory where a new files are automatically owned by the group team
- Experiments with various umask setting.
- Adjust defaults permissions for specific users.
- confirm your adjustment is correct.

## lab activity
```sh
 $ umask
0002
 ```
* Create a new directory /tmp/devops and a new file /tmp/devops/defaults to see how the default umask affects permissions.
```sh
$ mkdir /tmp/devops
$ ls -ld /tmp/devops
drwxrwxr-x. 2 devops devops 6 Jul  1 09:42 /tmp/devops
$ touch /tmp/devops/defaults
$ ls -l /tmp/devops/defaults
-rw-rw-r--. 1 devops devops 0 Jul  1 09:44 /tmp/devops/defaults
```
- Change the group ownership of /tmp/devops to team
and record the new ownership and permissions.
```sh
$ sudo groupadd team
$ tail -4 /etc/group
service:x:5001:
tom:x:1001:
mysql:x:27:
team:x:5002:
```
```sh
$ sudo chown :team /tmp/devops
$ ls -ld /tmp/devops/
drwxrwxr-x. 2 devops team 21 Jul  1 09:44 /tmp/devops/
```
- Crete a new file in tmp/devops and record the ownership and permissions.
```sh
$ touch /tmp/devops/ansible
$ ls -l /tmp/devops/ansible
-rw-rw-r--. 1 devops devops 0 Jul  1 10:04 /tmp/devops/ansible
```
- Ensure the permissions of tmp/devops cause files created in the created in that directory to inherit the group ownership of team.
```sh
$ sudo chmod g+s /tmp/devops/
$ ls -ld /tmp/devops/
drwxrwsr-x. 2 devops team 35 Jul  1 10:21 /tmp/devops/
$ touch /tmp/devops/ansible1
$ ls -l /tmp/devops//ansible1
-rw-rw-r--. 1 devops team 0 Jul  1 11:38 /tmp/devops//ansible1
```
- Change the umask for devops such that new files are created with read-only access for the group and no access for other users.Create a new file and record the ownership and  permissions
```sh
$ umask 027
$ touch /tmp/devops/ansible2
$ ls -l /tmp/devops/ansible2
-rw-r-----. 1 devops team 0 Jul  1 11:45 /tmp/devops/ansible2
```
- Open a new Bash shell as devops and view the umas.
```sh
$ umask
0002
```
- Change the default umask for devops to prohibt all access for users not in their group.
```sh  
$ sudo echo "umask 007" >> ~/.bashrc  
$ sudo cat ~/.bashrc
```  
>.# .bashrc  
>.# User specific aliases and functions
>  
>alias rm='rm -i'   
>alias cp='cp -i'  
>alias mv='mv -i'
>
>.# Source global definitions  
if [ -f /etc/bashrc ]; then   
 . /etc/bashrc   
fi   
umask 007


- Log out back into devops and confirm that the umask changes you made are persistent.

```sh
$ umask
0007
```
