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
        
