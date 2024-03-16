
 Well swap is what we used to allocate virtual memory to our system. 
 If you are low on memory, the system uses this partition to "swap" pieces of memory of idle processes to the disk, so you're not bogged for memory.

Using a partition for swap space

    Let's say we wanted to set our partition of /dev/sdb2 to be used for swap space.

    First make sure we don't have anything on the partition
    Run: mkswap /dev/sdb2 to initialize swap areas
    Run: swapon /dev/sdb2 this will enable the swap device
    If you want the swap partition to persist on bootup, you need to add an entry to the /etc/fstab file. sw is the filesystem type that you'll use.
    To remove swap: swapoff /dev/sdb2
