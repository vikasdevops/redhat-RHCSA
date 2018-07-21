## Using authconfig-gtk
```sh
$ sudo yum -y install authconfig-gtk sssd krb5-workstation
```
- On the identity and Authentication tab, select LDAP from the user Account Database drop-down. Fill out the LDAP serach Base DN and LDAP Server fields.
- Testing a Configuation
```sh
$ getent passwd ldapuser0
```
----------------------------------------------------------------------------
