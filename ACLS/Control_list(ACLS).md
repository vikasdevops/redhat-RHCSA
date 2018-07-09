## Viewing ACL permissions
```sh
$ ls -l file_name
```
- View ACLS
```sh
$ getfacl file_name
```
## Changeing ACL File permissions
```sh  
$ setfacl -m u:name:rX file        ## u=user , -m=modify   
$ setfacl -m g:name:rw file        ## g=group  
```
## Note:
- chmod has no effect on any group permissions for files with ACLS settings, but it updates the ACL mask.
```sh
$ setfacl -m o::- file             ## other user to  NO permissions
```
- multiple entries
```sh
$ setfacl -m u::rwx,g:sodor:rX,o::- file
```
- Recursive ACL modifications
```sh
$ setfacl -R -m u:name:rX directory
```   
