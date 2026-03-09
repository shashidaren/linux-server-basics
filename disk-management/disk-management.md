# Linux Disk Management

Disk management is essential for monitoring storage usage, mounting filesystems, and troubleshooting disk space issues.

---

## List Block Devices

Show disks and partitions:

lsblk

Displays:

- disks
- partitions
- mount points
- sizes

---

## Check Disk Usage

Show filesystem usage:

df -h

Example output shows:

- filesystem
- total size
- used space
- available space
- mount point

---

## Check Directory Size

Check size of directory:

du -sh directory

Example:

du -sh /var/log

---

## Find Large Files

Find large files in a directory:

du -ah /var | sort -rh | head -20

---

## View Disk Partitions

Show partition information:

fdisk -l

---

## Mount a Filesystem

Mount a disk:

sudo mount /dev/sdb1 /mnt/data

Example:

sudo mount /dev/sdb1 /mnt

---

## Unmount a Filesystem

sudo umount /mnt/data

---

## Check Mounted Filesystems

mount

or

lsblk

---

## Persistent Mount (fstab)

Mount disks automatically at boot using:

/etc/fstab

Example entry:

/dev/sdb1 /data ext4 defaults 0 0

---

## Check Disk Type

blkid

Shows filesystem types such as:

ext4  
xfs  

---

## Create Filesystem

Create ext4 filesystem:

sudo mkfs.ext4 /dev/sdb1

Create xfs filesystem:

sudo mkfs.xfs /dev/sdb1

---

## Check Disk Inodes

df -i

Shows inode usage which can also cause disk issues.

---

## Troubleshooting Disk Full

Check disk usage:

df -h

Check large directories:

du -sh /*

Check large log files:

du -sh /var/log/*

