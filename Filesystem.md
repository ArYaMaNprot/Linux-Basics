
## Filesystem
    There are many different filesystem implementations available. 
    Some are faster than others, some support larger capacity storage and others only work on smaller capacity storage. 
    Different filesystems have different ways of organizing their data and we'll go into detail about what types of filesystems there are. 
    Since there are so many different implementations available, applications need a way to deal with the different operations. 
    So there is something called the Virtual File System (VFS) abstraction layer. It is a layer between applications and the different filesystem types, 
    so no matter what filesystem you have, your applications will be able to work with it.

    You can have many filesystem on your disks, depending on how they are partitioned and we will go through that in a coming lesson.

## Journaling

    Journaling comes by default on most filesystem types, but just in case it doesn't, you should know what it does. 
    Let's say you're copying a large file and all of a sudden you lose power. Well if you are on a non-journaled filesystem, 
    the file would end up corrupted and your filesystem would be inconsistent and then when you boot back up, 
    your system would perform a filesystem check to make sure everything is ok. However, the repairs could take awhile depending on how large your filesystem was.

    Now if you were on a journaled system, before your machine even begins to copy the file, 
    it will write what you're going to be doing in a log file (journal). 
    Now when you actually copy the file, once it completes, the journal marks that task as complete. 
    The filesystem is always in a consistent state because of this, so it will know exactly where you left off if your machine shutdown suddenly. 
    This also decreases the boot time because instead of checking the entire filesystem it just looks at your journal.

    Common Desktop Filesystem Types

    ext4 - This is the most current version of the native Linux filesystems. It is compatible with the older ext2 and ext3 versions. 
    It supports disk volumes up to 1 exabyte and file sizes up to 16 terabytes and much more. It is the standard choice for Linux filesystems.
    Btrfs - "Better or Butter FS" it is a new filesystem for Linux that comes with snapshots, 
    incremental backups, performance increase and much more. It is widely available, but not quite stable and compatible yet.
    XFS - High performance journaling file system, great for a system with large files such as a media server.
    NTFS and FAT - Windows filesystems
