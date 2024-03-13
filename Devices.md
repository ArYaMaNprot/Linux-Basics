## Device Characterization
    Devices are characterized using two numbers, major device number and minor device number. 
    You can see these numbers in the above ls example, they are separated by a comma. 
    For example, let's say a device had the device numbers: 8, 0:

    The major device number represents the device driver that is used, in this case 8, which is often the major number for sd block devices. 
    The minor number tells the kernel which unique device it is in this driver class, in this case 0 is used to represent the first device (a).
---

### Pseudo Devices

    As we discussed earlier, pseudo devices aren't really physically connected to your system, most common pseudo devices are character devices:

    /dev/zero - accepts and discards all input, produces a continuous stream of NULL (zero value) bytes
    /dev/null - accepts and discards all input, produces no output
    /dev/random - produces random numbers
### sysfs
        Sysfs was created long ago to better manage devices on our system that the /dev directory failed to do.
        Both directories /sys and /dev seem to be very similar and they are in some regards, but they do have major differences. 
        Basically, the /dev directory is simple, it allows other programs to access devices themselves, 
        while the /sys filesystem is used to view information and manage the device.
### udev
        The udev system dynamically creates and removes device files for us depending on whether or not they are connected. 
        There is a udevd daemon that is running on the system and it listens for messages from the kernel about devices connected to the system. 
        Udevd will parse that information and it will match the data with the rules that are specified in

        You can also view the udev database and sysfs using the udevadm command. 
        This tool is very useful, but sometimes can get very convoluted, a simple command to view information for a device would be:

        $ udevadm info --query=all --name=/dev/sda
### Listing USB Devices
        $ lsusb 

### Listing PCI Devices
        $ lspci 

### Listing SCII devices
        $  lsscsi 
        
### The dd tool is super useful for converting and copying data. It reads input from a file or data stream and writes it to a file or data stream.

    The dd tool is super useful for converting and copying data. It reads input from a file or data stream and writes it to a file or data stream.

    Consider the following command:

    $ dd if=/home/pete/backup.img of=/dev/sdb bs=1024 
    This command is copying the contents of backup.img to /dev/sdb. It will copy the data in blocks of 1024 bytes until there is no more data to be copied.

    if=file - Input file, read from a file instead of standard input
    of=file - Output file, write to a file instead of standard output
    bs=bytes - Block size, it reads and writes this many bytes of data at a time. You can use different size metrics 
    by denoting the size with a k for kilobyte, m for megabyte, etc, so 1024 bytes is 1k
    count=number - Number of blocks to copy.
    You will see some dd commands that use the count option, usually with dd if you want to copy a file that is 1 megabyte, 
    you'll usually want to see that file as 1 megabyte when it's done being copied. Let's say you run the following command:

    $ dd if=/home/pete/backup.img of=/dev/sdb bs=1M count=2
    Our backup.img file is 10M, however, we are saying in this command to copy over 1M 2 times, 
    so only 2M is being copied, leaving our copied data incomplete. Count can come in handy in many situations, 
    but if you are just copying over data, you can pretty much omit count and even bs for that matter. 
    If you really want to optimize your data transfers, then you'll want to start using those options.

    dd is extremely powerful, you can use it to make backups of anything, including whole disk drives, 
    restoring disks images, and more. Be careful, that powerful tool can come at a price if you aren't sure what you are doing.
        
