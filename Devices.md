## Device Characterization
    Devices are characterized using two numbers, major device number and minor device number. 
    You can see these numbers in the above ls example, they are separated by a comma. 
    For example, let's say a device had the device numbers: 8, 0:

    The major device number represents the device driver that is used, in this case 8, which is often the major number for sd block devices. 
    The minor number tells the kernel which unique device it is in this driver class, in this case 0 is used to represent the first device (a).
