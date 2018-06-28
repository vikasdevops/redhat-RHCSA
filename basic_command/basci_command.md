## Directory navigation
- pwd    **Get the full path of the current working directory**
- cd -   **Navigate to the last directory you were working in.**
- cd ~   **Navigate to the current user's home directory.**
- cd ..  **Go to the parent directory of current directory (mind the space between cd and ..)**
## Listing files inside a directory
- ls -l   **List the files and directories in the current directory in long (table) format (It is recommended to
use -l with ls for better readability).**
- ls -a   **List all the files including the hidden ones (File names starting with a . are hidden files in Linux).**
- ls -It  **List the files sorted by last modified time with most recently modified files showing at the top
(remember -l option provides the long format which has better readability).**
## File/directory create, copy and remove
- cp - p  **Will copy the file from source to destination. -p stands for preservation. It
preserves the original attributes of file while copying like file owner, timestamp,
group, permissions etc.**
 - mv file1 file2  **In Linux there is no rename command as such. Hence mv moves/renames the
file1 to file2.**
- rm -i filename  **Asks you before every file removal for confirmation. IF YOU ARE A NEW USER
TO LINUX COMMAND LINE, YOU SHOULD ALWAYS USE rm -i. You can specify
multiple files.**
- mkdir dir-name  **Create a directory dir-name.**
- touch filename  **Create a file filename, if it doesn't exist, otherwise change the timestamp of the
file to current time.**
- chmod <specification> filename  **Change the file permissions. Specifications = u user, g group, o other, + add
permission, - remove, r read, w write,x execute.**
- chgrp -R grp_owner dir-name     **Change primary group ownership of directory dir-name to group grp_owner
recursively. To change group ownership of a directory and everything within
that directory, use this command.**
## Searching for files by patterns in name/contents
- A common and task of someone using the Linux Command Line (shell) is to search for files/directories with a
certain name or containing certain text. There are 2 commands you should familiarise yourself with in order to
accomplish this:
**Find files by name**
```sh
$ find /var/www -name '*.css'
```
**This will print out the full path/filename to all files under /var/www that end in .css. Example output**

```sh
/var/www/html/text-cursor.css
/var/www/html/style.css
```
## Find files containing text
```sh
grep font /var/www/html/style.css
```
- This will print all lines containing the pattern font in the specified file. Example output:
```sh
font-weight: bold;
font-family: monospace;
```
## File/Directory details
```sh
$ ls -l
```
- Would output something like
```sh
-rw-r--r-- 1 user users 70 Jul 22 13:36 someFile.txt
drwxrwxrwx 2 user users 4096 Jul 21 07:18 test
```
- To change rights you can use the chmod ### fileName command if you have sudo rights. r is represented by a
value of 4, w is represented by 2, and x is represented by a 1. So if only you want to be able to modify the contents
to the test directory
```sh
Owner rwx = 4+2+1 = 7
Group r-x = 4+0+1 = 5
Other r-x = 4+0+1 = 5
```
- So the whole command is
```sh
chmod 755 test
```
- Now doing a ls -l would show something like
```sh
drwxr-xr-x 2 user users 4096 Jul 21 07:20 test
```
**Hidden**
```sh
$ ls -a
```
- Might list
```sh
.profile
someFile.txt
test
```
## Detect what debian-based distribution you are working in
``sh
$ lab_release -a
No LSB modules are available.
Distributor ID: Debian
Description:    Debian GNU/Linux testing (stretch)
Release:        testing
Codename:       stretch
```
## Detect what RHEL / CentOS / Fedora distribution you are working in
```sh
cat /etc/redhat-release
```
## Check Disk Space
```sh
$ du -sh *
580K Documents
209M Downloads
4,0K Music
720K Pictures
4,01K Public
4,01K Templates
4,01K Videos
```
## Compress a folder
- This creates a simple archive of a folder :
```sh
tar -cf ./my-archive.tar ./my-folder/
```
- extract a folder from an archive in the current location :
```sh
tar -xf archive-name.tar
```
