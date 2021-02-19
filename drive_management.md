# Drive Management
Idea taken from [keithmorris/drive-format-ubuntu.md](https://gist.github.com/keithmorris/b2aeec1ea947d4176a14c1c6a58bfc36)
## List Drives
```
fdisk -l
```

## Format Drive
```
mkfs -t ext4 /dev/<drive_name>
```

## Install ZFS
ref: https://ubuntu.com/tutorials/setup-zfs-storage-pool#3-creating-a-zfs-pool

```
apt install zfsutils-linux
whereis zfs
```

## Create RAID 1 (Mirrored Pool)
```
zpool create data_store mirror /dev/sdb /dev/sdd -f
```

## View Zpools
```
zpool status
```

## Destroy Pool
```
zpool destroy data_store
```

## View btrfs 
```
btrfs fi show
```

## single drive btrfs
```
mkfs.btrfs /dev/sdb
```

## RAID1 on btrfs
```
mkfs.btrfs -d raid1 /dev/sdb /dev/sdd -f
```

## Mount  btrfs
```
vi /etc/fstab
UUID=e7e5c123-fg76-5gxx-a87d-gt5fed9r768e /data           btrfs   defaults      0  0
```

## rename btrfs label
```
```

## list volume groups
```
vgs
```

## create logical volume
```
lvcreate -L 1G -n test_vol test_grp
```
