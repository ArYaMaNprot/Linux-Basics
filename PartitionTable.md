# Partition Table

    Every disk will have a partition table, this table tells the system how the disk is partitioned. 
    This table tells you where partitions begin and end, which partitions are bootable, what sectors of the disk are allocated to what partition, etc. 
    There are two main partition table schemes used, Master Boot Record (MBR) and GUID Partition Table (GPT).

## MBR

    Traditional partition table, was used as the standard
    Can have primary, extended, and logical partitions
    MBR has a limit of four primary partitions
    Additional partitions can be made by making a primary partition into an extended partition (there can only be one extended partition on a disk). Then inside the extended partition you add logical partitions. The logical partitions are used just like any other partition. Silly I know.
    Supports disks up to 2 terabytes
 ## GPT

    GUID Partition Table (GPT) is becoming the new standard for disk partitioning
    Has only one type of partition and you can make many of them
    Each partition has a globally unique ID (GUID)
    Used mostly in conjunction with UEFI based booting (we'll get into details in another course)
## Filesystem Structure

    We know from our previous lesson that a filesystem is an organized collection of files and directories. 
    In its simplest form, it is comprised of a database to manage files and the actual files themselves, however we're going to go into a little more detail.

    Boot block - This is located in the first few sectors of the filesystem, and it's not really used the by the filesystem. Rather, 
    it contains information used to boot the operating system. Only one boot block is needed by the operating system. 
    If you have multiple partitions, they will have boot blocks, but many of them are unused.
    
    Super block - This is a single block that comes after the boot block, and it contains information about the filesystem, 
    such as the size of the inode table, size of the logical blocks and the size of the filesystem.      

    Inode table - Think of this as the database that manages our files (we have a whole lesson on inodes, so don't worry). 
    Each file or directory has a unique entry in the inode table and it has various information about the file.
    
    Data blocks - This is the actual data for the files and directories.
