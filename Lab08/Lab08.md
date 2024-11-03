## Lab 08

- Name: Corinna Green
- Email: green.442@wright.edu

## Part 1

1. Command: `lsblk /dev/xvda`
```
NAME     MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
xvda     202:0    0   16G  0 disk
├─xvda1  202:1    0 15.9G  0 part /
├─xvda14 202:14   0    4M  0 part
└─xvda15 202:15   0  106M  0 part /boot/efi
```
2. Command: `sudo parted /dev/xvda print`
```
Model: Xen Virtual Block Device (xvd)
Disk /dev/xvda: 17.2GB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags:

Number  Start   End     Size    File system  Name  Flags
14      1049kB  5243kB  4194kB                     bios_grub
15      5243kB  116MB   111MB   fat32              boot, esp
 1      116MB   17.2GB  17.1GB  ext4
```
3. For the `xvda` partition table:
    - Does it use MBR or GPT? GPT
    - How many partitions are on the block device? 3
    - What is the largest partition? partition 14
4. Command: `sudo blkid /dev/xvda*`
```
/dev/xvda: PTUUID="f8e0f7e2-b7e6-4476-ae26-4e5d438041c5" PTTYPE="gpt"
/dev/xvda1: LABEL="cloudimg-rootfs" UUID="b78b2f9f-3a08-427a-ad4e-4a04f235761c" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="5685b7d3-4911-4237-9405-e73d2d78ca3e"
/dev/xvda14: PARTUUID="ca8e99c4-f383-4d1e-8cda-a1023a3a49f4"
/dev/xvda15: LABEL_FATBOOT="UEFI" LABEL="UEFI" UUID="4B1C-F903" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="1dcb7fe9-f679-4d8b-afbe-2f4f444c7095"
```
5. For the primary partition:
    - What partition is the root filesystem on? /dev/root
    - What is the partition label? cloudimg-rootfs
    - What type of filesystem is on the partition? ext4
6. Command:`df`
```
Filesystem     1K-blocks    Used Available Use% Mounted on
/dev/root       16069568 4304560  11748624  27% /
tmpfs             490204       0    490204   0% /dev/shm
tmpfs             196084     856    195228   1% /run
tmpfs               5120       0      5120   0% /run/lock
/dev/xvda15       106858    6165    100693   6% /boot/efi
tmpfs              98040       4     98036   1% /run/user/1000
```
7. For the root filesystem:
    - What is the total size? 16,069,568 KB
    - How much space is used? 4,304,560 KB
    - Where is it mounted to? /
8. Command: `cat /etc/fstab`
```
LABEL=cloudimg-rootfs   /        ext4   discard,errors=remount-ro       0 1
LABEL=UEFI      /boot/efi       vfat    umask=0077      0 1
```
9. Fields & purpose of fields in entry that mount the root filesystem: Each field in `/etc/fstab` tells us where the filesystem is mounted and provides information about its mountpoint, the options, type, etc. Each entry in fstab includes 6 fields, each giving information about the filesystem. Fields are important in that they manage filesystems.


## Part 2

1. `gdisk` main menu options
   - `p`: prints partition table
   - `o`: deletes all partitions and creates a new protective MBR/ new GUID
   - `n`: creates new partition
   - `i`: provides information about your partition
   - `w`: writes changes to disk and exits
2. Steps to create a partition table and partition on `xvbd`: 
	1. Type command `sudo gdisk /dev/xvdb`
	2. If the disk does not already have a partition table, you can type o to create one
	3. To create a new partition, type n
	4. From n, specify partition number, first sector, last sector, and partition type (you can click enter for default on all)
	5. To review changes, enter p
	6. Enter w to write changes and exit 
3. Partition table on `/dev/xvdb`
```
Command (? for help): p
Disk /dev/xvdb: 8388608 sectors, 4.0 GiB
Sector size (logical/physical): 512/512 bytes
Disk identifier (GUID): F2FFF544-DD66-4F15-BD3C-0B13C23D9947
Partition table holds up to 128 entries
Main partition table begins at sector 2 and ends at sector 33
First usable sector is 34, last usable sector is 8388574
Partitions will be aligned on 2048-sector boundaries
Total free space is 2014 sectors (1007.0 KiB)

Number  Start (sector)    End (sector)  Size       Code  Name
   1            2048         8388574   4.0 GiB     8300  Linux filesystem
```
4. Answer these questions:
   
   a. What device name does the partition use?
      - Answer: xvdb1
        
   b. What size is the partition in GB?
      - Answer: 4.0 GB
        
   c. What filesystem type will be used on the partition?
      - Answer: Linux filesystem

## Part 3

1. Commands used: `sudo mkfs.ext4 /dev/xvdb1`
2. Commands used: `sudo blkid`
```
`mke2fs 1.46.5 (30-Dec-2021)
Creating filesystem with 1048315 4k blocks and 262144 inodes
Filesystem UUID: 8dec3e9f-4c51-4377-b0a7-b8fb37771c14
Superblock backups stored on blocks:
        32768, 98304, 163840, 229376, 294912, 819200, 884736

Allocating group tables: done
Writing inode tables: done
Creating journal (16384 blocks): done
Writing superblocks and filesystem accounting information: done`

`/dev/xvda1: LABEL="cloudimg-rootfs" UUID="b78b2f9f-3a08-427a-ad4e-4a04f235761c" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="5685b7d3-4911-4237-9405-e73d2d78ca3e"
/dev/xvda15: LABEL_FATBOOT="UEFI" LABEL="UEFI" UUID="4B1C-F903" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="1dcb7fe9-f679-4d8b-afbe-2f4f444c7095"
/dev/loop1: TYPE="squashfs"
/dev/loop8: TYPE="squashfs"
/dev/loop6: TYPE="squashfs"
/dev/loop4: TYPE="squashfs"
/dev/loop2: TYPE="squashfs"
/dev/loop0: TYPE="squashfs"
/dev/loop9: TYPE="squashfs"
/dev/loop7: TYPE="squashfs"
/dev/loop5: TYPE="squashfs"
/dev/loop3: TYPE="squashfs"
/dev/loop10: TYPE="squashfs"
/dev/xvda14: PARTUUID="ca8e99c4-f383-4d1e-8cda-a1023a3a49f4"
/dev/xvdb1: UUID="8dec3e9f-4c51-4377-b0a7-b8fb37771c14" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="Linux filesystem" PARTUUID="7f320f69-f5e5-4caa-9116-97f064b21f61"`
```
3. Commands used: `sudo mkdir /mnt/newworld`
4. Commands used: `sudo mount /dev/xvdb1 /mnt/newworld`
5. Contents of `/mnt/newworld`:
```
list here
`lost+found exampledir examplefile.txt`
```
6. Commands used: `sudo umount /mnt/newworld`
7. When can I interact with files on the filesystem on the partition in `xvdb`?
   - Answer: Only when the partition is mounted.
   
## Part 4

1. Commands used:
2. Line you added to `/etc/fstab`:
3. How did you confirm that the mount point changed? (Commands used or explain process):
4. **If you restored `/etc/fstab`**, write here why you did not feel comfortable leaving your changes in place


## Part 5

1. Commands used:
2. What does the `strings` command do?
   - Answer:
3. Write a short explanation of what you saw in `strings` output:
4. Commands used:
5. Is the secret you deleted still showing up in the `strings` output?

### Report: How to Permanently Delete a File

**Write your report here**

## Extra Credit Answers:

1. Commands used: 
2. Explanation:
3. Commands used: 
4. Commands used: 

