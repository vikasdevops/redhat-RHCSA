## Mounting File system
- Format file system with the ext4 file system
```sh    
$ sudo mkfs -t ext4 /dev/sdb3   
mke2fs 1.42.9 (28-Dec-2013)    
Filesystem label=   
OS type: Linux  
Block size=1024 (log=0)   
Fragment size=1024 (log=0)  
Stride=0 blocks, Stripe width=0 blocks  
102400 inodes, 409600 blocks   
20480 blocks (5.00%) reserved for the super user  
First data block=1    
Maximum filesystem blocks=34078720   
50 block groups        
8192 blocks per group, 8192 fragments per group   
2048 inodes per group    
Superblock backups stored on blocks:    
	8193, 24577, 40961, 57345, 73729, 204801, 221185, 401409          
Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (8192 blocks): done   
Writing superblocks and filesystem accounting information: done  
```
- Create directory mount point
```sh
$ mkdir /achive  
$ blkid /dev/sdb3  
/dev/sdb3: UUID="6a008b0c-eac4-40a3-85fe-2f651c8b94ca" TYPE="ext4"
```
```sh
$ vi /etc/fstab
/dev/sdb3 /achive ext4 defaults 0 0
```
```sh
$ mount -a
```
- verify mount
```sh
$ mount | grep -w /achive   
/dev/sdb3 on /achive type ext4 (rw,relatime,seclabel,data=ordered)
```
