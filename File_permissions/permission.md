
## To check permissions
```sh
$ ls -l <filename>
$ ls -ld <directoryname>
```
### syntax:
chmod  file|directory

sum r=4,w=2,and x=1.
```sh

$ chmod 750 sample
 7 owner 5 group 0 other
$ chmod -R g+rwX sample    ## -R recursively
```
## changing file / directory user or group ownership
 -------------------------------------------------
syntax:
  chown : <nameoner> file
```sh
$ chown : admin sample
```
## special permission
 ------------------------------------------------
 concept: [file]
- u+s(suid)  ## file executes as the user that owns
- g+s(sgid)  ## file executes as the group that owns
- o+t(sticky) ## no effect
 Eg:
 ```sh
 $ chmod g+s sample
 ```
 shortcut:
 setuid=4;setgid=2;stickey=1

 Eg:
 ```sh
 $ chmod 2770 sample
```
