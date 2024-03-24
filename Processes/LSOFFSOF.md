Let's say you plugged in a USB drive and starting working on some files, once you were done, you go and unmount the 
USB device and you're getting an error "Device or Resource Busy". How would you find out which files in the
USB drive are still in use? There are actually two tools you can use for this

## lsof

    Remember files aren't just text files, images, etc, they are everything on the system, disks, pipes, network sockets, devices, etc. 
    To see what is in use by a process, you can use the lsof command (short for "list open files") this will 
    show you a list of all the open files and their associated process.

## fuser

    Another way to track a process is the fuser command (short for "file user"), 
    this will show you information about the process that is using the file or the file user.
