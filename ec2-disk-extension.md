# Extend the file system after resizing an Amazon EBS volume

### AWS Console → EC2 → Elastic Block Store → Volumes

1. Select the volume attached to your EC2 instance.
2. Click *Actions* → **Modify volume**.
3. Change Size from **8 GiB** to **16 GiB**.
4. Click **Modify** → confirm.


## View current size

```sh
lsblk
```

### Extend the partition

For a typical Amazon Linux/Ubuntu EC2 instance using NVMe:

```sh
sudo growpart /dev/nvme0n1 1
```

### Extend the filesystem

First determine the filesystem:

```sh
df -Th /
```

```sh
sudo xfs_growfs /
```
```sh
sudo resize2fs /dev/nvme0n1p1
```

### Verify 

```sh
lsblk
df -Th
```
