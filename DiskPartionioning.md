# Disk partionning
    Let's do some practical stuff with filesytems by working through the process on a USB drive. If you don't have one, no worries, you can still follow along these next couple of lessons.

    First we'll need to partition our disk. There are many tools available to do this:

    fdisk - basic command-line partitioning tool, it does not support GPT
    parted - this is a command line tool that supports both MBR and GPT partitioning
    gparted - this is the GUI version of parted
    gdisk - fdisk, but it does not support MBR only GPT
    
    Let's use parted to do our partitioning. Let's say I connect the USB device and we see the device name is /dev/sdb2.

    Launch parted

    $ sudo parted
    
    You'll be entered in the parted tool, here you can run commands to partition your device.

    Select the device

    select /dev/sdb2
    
    To select the device you'll be working with, select it by its device name.

    View current partition table
    (parted) print  
