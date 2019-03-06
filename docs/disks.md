# Linux Disk usages

## `fdisk` command

That command will show list of devices that're avaible on your system
```shell
$ fdisk -l
```

## `mount` command  
To mount device need to specify device name and mount folder
```shell
$ mount /dev/sdb1 /media/my-device
```
In this command we can specify type of filesystem
```shell
$ mount -t ext4 /dev/sdb1 /media/my-device
```

## Add second HDD
### Step#1
If it's new hard drive we need to create partition on it
```shell
$ fdisk /dev/sdb
```
Here's then list of command that support `fdisk`:

* **m** – print help
* **p** – print the partition table
* **n** – create a new partition
* **d** – delete a partition
* **q** – quit without saving changes
* **w** – write the new partition table and exit

###Step#2

Format new disk with `mkfs.ext4` command
```shell
$ mkfs.ext4 /dev/sdb1
```

###Step#3
Create new mount point and do a mount
```shell
$ mkdir /disk2
$ mount -t ext4 /dev/sdb1 /disk2
```

If you what that not only root user can use that mount, you need add permissions
```shell
$ chmod 777 /disk2
```
###Step#4
Update `/etc/fstab` file
If you what mount disk automaticaly on boot you need to add that line to your `/etc/fstab` config:  
`/dev/sdb1 /disk2 ext4 defaults,errors=remount-ro,user,rw 0 1`


