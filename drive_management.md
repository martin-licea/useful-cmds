# Drive Management
Idea taken from [keithmorris/drive-format-ubuntu.md](https://gist.github.com/keithmorris/b2aeec1ea947d4176a14c1c6a58bfc36)
## List Drives
```
sudo fdisk -l
```

## Format Drive
```
sudo mkfs -t ext4 /dev/<drive_name>
```

## Install ZFS
ref: https://ubuntu.com/tutorials/setup-zfs-storage-pool#3-creating-a-zfs-pool

```
sudo apt install zfsutils-linux
whereis zfs
```

## Create RAID 1 (Mirrored Pool)
```
sudo zpool create data_store mirror /dev/sdb /dev/sdd -f
```

## View Zpools
```
sudo zpool status
```