# Linux Logical Volume Manager (LVM)

LVM provides flexible disk management in Linux. It allows administrators to resize storage, combine multiple disks, and manage logical volumes dynamically.

LVM components:

Physical Volume (PV)  
Volume Group (VG)  
Logical Volume (LV)

---

## View Block Devices

lsblk

Shows disks and partitions available in the system.

---

## Create Physical Volume

Initialize disk for LVM:

sudo pvcreate /dev/sdb

Check physical volumes:

pvs

Detailed view:

pvdisplay

---

## Create Volume Group

Create a volume group:

sudo vgcreate vg_data /dev/sdb

Check volume groups:

vgs

Detailed information:

vgdisplay

---

## Create Logical Volume

Create logical volume:

sudo lvcreate -L 5G -n lv_data vg_data

Example:

Create 5GB logical volume.

---

## View Logical Volumes

lvs

Detailed view:

lvdisplay

---

## Format Logical Volume

Create filesystem:

sudo mkfs.ext4 /dev/vg_data/lv_data

---

## Mount Logical Volume

Create mount point:

sudo mkdir /data

Mount volume:

sudo mount /dev/vg_data/lv_data /data

---

## Persistent Mount

Add entry in:

/etc/fstab

Example:

/dev/vg_data/lv_data /data ext4 defaults 0 0

---

## Extend Logical Volume

Extend LV size:

sudo lvextend -L +2G /dev/vg_data/lv_data

Resize filesystem:

sudo resize2fs /dev/vg_data/lv_data

---

## Reduce Logical Volume

Reduce filesystem first:

sudo resize2fs /dev/vg_data/lv_data 3G

Then reduce LV:

sudo lvreduce -L 3G /dev/vg_data/lv_data

---

## Extend Volume Group

Add another disk:

sudo vgextend vg_data /dev/sdc

---

## Remove Logical Volume

sudo lvremove /dev/vg_data/lv_data

---

## Remove Volume Group

sudo vgremove vg_data

---

## Remove Physical Volume

sudo pvremove /dev/sdb

---

## LVM Troubleshooting

Check PV:

pvs

Check VG:

vgs

Check LV:

lvs

View details:

pvdisplay
vgdisplay
lvdisplay

