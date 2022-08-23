#磁盘工具

最近在编译ceph 时需要扩容vm 的磁盘，导致需要扩容centos 的磁盘用到下列工具

## fdisk
fdisk /dev/sdb 可以对块设备进行重新分区扩容，缩容。
具体操作可看帮助文档

## resize2fs
resize2fs /dev/sdb1  可以对分区的文件系统进行扩容，在用fdisk 对分区进行扩容后，还需要对上边的文件系统进行扩容，不然文件系统还是识别到老的容量

##  testdisk
本次扩容虚拟机磁盘碰到，分区superblock 丢失，分区大小变为1K 的情况。可以试用testdisk 重新扫描分区，重写文件系统superblock.

##  fsck
文件系统错乱的情况下，也可以尝试试用fsck 进行修复。
