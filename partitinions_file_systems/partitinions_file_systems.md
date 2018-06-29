## Specify the disk device partition on.
```sh
$ fdisk /dev/vdb         ## vdb is virtual disk
```
```sh
$ fdisk /dev/sdb*        ## show all partition, sdb is hard disk  
brw-rw----. 1 root disk 8, 16 Jun 29 12:22 /dev/sdb
brw-rw----. 1 root disk 8, 17 Jun 29 12:22 /dev/sdb1
brw-rw----. 1 root disk 8, 18 Jun 29 12:22 /dev/sdb2
brw-rw----. 1 root disk 8, 20 Jun 29 12:22 /dev/sdb4
brw-rw----. 1 root disk 8, 21 Jun 29 12:22 /dev/sdb5
brw-rw----. 1 root disk 8, 22 Jun 29 12:22 /dev/sdb6
brw-rw----. 1 root disk 8, 23 Jun 29 12:22 /dev/sdb7
brw-rw----. 1 root disk 8, 24 Jun 29 12:22 /dev/sdb8
```
## Specify the disk device to create the partition on.
```sh
$ fdisk /dev/sdb
Welcome to fdisk (util-linux 2.23.2).

Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.


Command (m for help):
```
- Enter n to request a new patition

```sh
Command (m for help): n
Partition type:
  p   primary (2 primary, 1 extended, 1 free)
  l   logical (numbered from 5)
  Select (default p): p
  Selected partition 3
  First sector (1845248-20971519, default 1845248):
  Using default value 1845248
  Last sector, +sectors or +size{K,M,G} (1845248-2664447, default 2664447): +400MB                                                       
  Using default value 2664447
  Partition 3 of type Linux and of size 400 MiB is set
```
 - Define Partition type Enter t
 ```sh
 Command (m for help): t
Partition number (1-8, default 8): 3
Hex code (type L to list all codes): L

 0  Empty           24  NEC DOS         81  Minix / old Lin bf  Solaris        
 1  FAT12           27  Hidden NTFS Win 82  Linux swap / So c1  DRDOS/sec (FAT-
 2  XENIX root      39  Plan 9          83  Linux           c4  DRDOS/sec (FAT-
 3  XENIX usr       3c  PartitionMagic  84  OS/2 hidden C:  c6  DRDOS/sec (FAT-
 4  FAT16 <32M      40  Venix 80286     85  Linux extended  c7  Syrinx         
 5  Extended        41  PPC PReP Boot   86  NTFS volume set da  Non-FS data    
 6  FAT16           42  SFS             87  NTFS volume set db  CP/M / CTOS / .
 7  HPFS/NTFS/exFAT 4d  QNX4.x          88  Linux plaintext de  Dell Utility   
 8  AIX             4e  QNX4.x 2nd part 8e  Linux LVM       df  BootIt         
 9  AIX bootable    4f  QNX4.x 3rd part 93  Amoeba          e1  DOS access     
 a  OS/2 Boot Manag 50  OnTrack DM      94  Amoeba BBT      e3  DOS R/O        
 b  W95 FAT32       51  OnTrack DM6 Aux 9f  BSD/OS          e4  SpeedStor      
 c  W95 FAT32 (LBA) 52  CP/M            a0  IBM Thinkpad hi eb  BeOS fs        
 e  W95 FAT16 (LBA) 53  OnTrack DM6 Aux a5  FreeBSD         ee  GPT            
 f  W95 Ext'd (LBA) 54  OnTrackDM6      a6  OpenBSD         ef  EFI (FAT-12/16/
10  OPUS            55  EZ-Drive        a7  NeXTSTEP        f0  Linux/PA-RISC b
11  Hidden FAT12    56  Golden Bow      a8  Darwin UFS      f1  SpeedStor      
12  Compaq diagnost 5c  Priam Edisk     a9  NetBSD          f4  SpeedStor      
14  Hidden FAT16 <3 61  SpeedStor       ab  Darwin boot     f2  DOS secondary  
16  Hidden FAT16    63  GNU HURD or Sys af  HFS / HFS+      fb  VMware VMFS    
17  Hidden HPFS/NTF 64  Novell Netware  b7  BSDI fs         fc  VMware VMKCORE
18  AST SmartSleep  65  Novell Netware  b8  BSDI swap       fd  Linux raid auto
1b  Hidden W95 FAT3 70  DiskSecure Mult bb  Boot Wizard hid fe  LANstep        
1c  Hidden W95 FAT3 75  PC/IX           be  Solaris boot    ff  BBT            
1e  Hidden W95 FAT1 80  Old Minix      
```

```sh
Hex code (type L to list all codes): 83
Changed type of partition 'Linux' to 'Linux'

```
- save partition by w command
```sh
Command (m for help): w
The partition table has been altered!

Calling ioctl() to re-read partition table.

WARNING: Re-reading the partition table failed with error 16: Device or resource busy.
The kernel still uses the old table. The new table will be used at
the next reboot or after you run partprobe(8) or kpartx(8)
Syncing disks.
```
- Initiate a kernel re-read of the new partion
```sh
$ partprobe /dev/sdb
```

- To check partition enter p :
```sh
$ fdisk /dev/sdb
Welcome to fdisk (util-linux 2.23.2).

Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.


Command (m for help): p

```
```sh
Disk /dev/sdb: 10.7 GB, 10737418240 bytes, 20971520 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0x21d110bb

   Device Boot      Start         End      Blocks   Id  System
/dev/sdb1            2048     1640447      819200   83  Linux
/dev/sdb2         1640448     1845247      102400   82  Linux swap / Solaris
/dev/sdb3         1845248     2664447      409600   83  Linux
/dev/sdb4         2664448    20971519     9153536    5  Extended
/dev/sdb5         2666496     3690495      512000   83  Linux
/dev/sdb6         3692544     4102143      204800   82  Linux swap / Solaris
/dev/sdb7         4104192     5128191      512000   83  Linux
/dev/sdb8         5130240     7227391     1048576   82  Linux swap / Solaris

```

- /dev/sdb3 created
