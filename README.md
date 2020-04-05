# infocoin-nginx-installer
Information about installing highload nginx upstream with detail log

# INSTALL

```bash
apt remove apache cloud*
apt install nginx-extras

mkdir -p /d02
echo 'tmpfs   /d02         tmpfs   nodev,nosuid,size=10G,noauto          0  0' >> /etc/fstab


apt install zfsutils-linux

zpool create z01 /dev/sdb1
zfs set atime=off z01
zfs set compression=lz4 z01
zfs set dedup=off z01
zfs set snapdir=visible z01
zfs set primarycache=all z01
zfs set aclinherit=passthrough z01
zfs inherit acltype z01
zfs get -r acltype z01
zpool export z01
zpool import z01


zfs set mountpoint=/d01 z01/d01


```