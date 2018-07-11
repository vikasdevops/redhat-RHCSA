# Outcome
- Add the group and user permissions by the ACLS.
- sodor group have a same access permissions as the devops group on the ansible directory, except john who has no access.
- Add as defaults ACLS to support future.
## Lab activity
```sh
$ setfacl -Rm g:sodor:rwX /shares/devops  
 ```
 - Denying the user john from sodor group any access
 ```sh
 $ setfacl -Rm u:john:- /shares/devops
 ```
 - Add as defaults ACLS to support future file and directory
 ```sh
 $ setfacl -m d:g:sodor:rwx /shares/devops
 ```
 - Add as defaults ACLs to john.Denying all access to the devops directory.
 ```sh
 $ setfacl -m d:u:john:- /shares/devops
 ```
  ________________________________________________________________________________
