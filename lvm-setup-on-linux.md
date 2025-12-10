# Mounting a New Disk to /data With LVM
1. Stop the vm in vmware
2. Add new hardware > harddisk > scsi > create new virtual disk
3. Turn on vm
4. Verify New Disk

```
lsblk
```
Example output:
```
sda    8:0    0   40G  0 disk
└─sda1 8:1    0   40G  0 part /
sdb    8:16   0   20G  0 disk <<< should be added as sdx
```
5. Create a physical volume
```
sudo pvcreate /dev/sdb
```

6. Create a new volume group (or extend existing one with vgextend)
```
sudo vgcreate data-vg /dev/sdb
```
7. Create a logical volume (e.g., 20G)
```
sudo lvcreate -l 100%FREE -n data-lv data-vg
```
8. Format the logical volume
```
sudo mkfs.ext4 /dev/data-vg/data-lv
```
9. Mount it to /data
```
sudo mount /dev/data-vg/data-lv /data
```
10. Add to /etc/fstab for persistence
```
echo "/dev/data-vg/data-lv /data ext4 defaults 0 2" | sudo tee -a /etc/fstab
```
11. Verify
```
lsblk
```


# Mounting a New Disk to /data Without LVM
1. stop the vm in vmware
2. add new hardware > harddisk > scsi > create new virtual disk
3. turn on vm
4.  Verify New Disk

```
lsblk
```
Example output:
```
sda    8:0    0   40G  0 disk
└─sda1 8:1    0   40G  0 part /
sdb    8:16   0   20G  0 disk <<< should be added as sdx
```
5. Create Partition on /dev/sdb
```
sudo fdisk /dev/sdb
```
- n new partition
- everythong else should be default
- w write



6. Format the Partition
```
sudo mkfs.ext4 /dev/sdb1
```
7. Create the Mount Directory
```
sudo mkdir -p /data
```
8. Mount the Disk Temporarily
```
sudo mount /dev/sdb1 /data
```
To verify:
```
df -h | grep /data
```
9. Mount Disk Permanently (Edit /etc/fstab)
Instead of using UUID, you can directly use /dev/sdb1 if you're sure the device name won't change.

Edit /etc/fstab:
```
sudo nano /etc/fstab
```
Add this line at the bottom:
```
/dev/sdb1  /data  ext4  defaults  0  2
```
Save and exit.

# Extending / With LVM
1. stop the vm in vmware
2. add new hardware > harddisk > scsi > create new virtual disk
3. turn on vm
4.  Verify New Disk

```
lsblk
```
Example output:
```
sda    8:0    0   40G  0 disk
└─sda1 8:1    0   40G  0 part /
sdb    8:16   0   20G  0 disk <<< should be added as sdx
```
5. Create a physical volume
```
sudo pvcreate /dev/sdb
```

6. Extend  volume group
```
sudo  vgextend  ubuntu-vg  /dev/sdb
```
7.  Extend logical volume
```
lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
```
8. Resize file system
```
resize2fs /dev/ubuntu-vg/ubuntu-lv
```
