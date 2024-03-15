First create the mount point, in our case mkdir /mydrive

    $ sudo mount -t ext4 /dev/sdb2 /mydrive
    Simple as that! Now when we go to /mydrive we can see our filesystem contents, the -t specifies the type of filesystem, then we have the device location, then the mount point.

    To unmount a device from a mount point:

      $ sudo umount /mydrive 

        or 

    $ sudo umount /dev/sdb2

    Remember that the kernel names devices in the order it finds them. 
    What if our device name changes for some reason after we mount it? Well fortunately, you can use a device's universally unique ID (UUID) instead of a name.

    To view the UUIDS on your system for block devices:


    pete@icebox:~$ sudo blkid

    When we want to automatically mount filesystems at startup we can add them to a file called /etc/fstab (pronounced "eff es tab" not "eff stab") short for filesystem table. This file contains a permanent list of filesystems that are mounted.


    pete@icebox:~$ cat /etc/fstab

    UUID=130b882f-7d79-436d-a096-1e594c92bb76 /               ext4    relatime,errors=remount-ro 0       1

    UUID=78d203a0-7c18-49bd-9e07-54f44cdb5726 /home           xfs     relatime        0       2

    UUID=22c3d34b-467e-467c-b44d-f03803c2c526 none            swap    sw              0       0

    Each line represents one filesystem, the fields are:

    UUID - Device identifier
    Mount point - Directory the filesystem is mounted to
    Filesystem type
    Options - other mount options, see manpage for more details
    Dump - used by the dump utility to decide when to make a backup, you should just default to 0
    Pass - Used by fsck to decide what order filesystems should be checked, if the value is 0, it will not be checked
