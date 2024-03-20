# Kernel Installation
To see what kernel version you have on your system, use the following command:

  $ uname -r

    You can install the Linux kernel in different ways, you can download the source package and compile from source or you can install it using package management tools.

    $ sudo apt install linux-generic-lts-vivid
    and then just reboot into the kernel you installed. Simple right? Kind of, you'll need to also install other linux packages such as the linux-headers, linux-image-generic, etc). 
    You can also specify the version number, so the above command can look like, sudo apt install 3.19.0-43-generic

    Alternatively, if you just want the updated kernel version, just use dist-upgrade, it performs upgrades to all package on your system:

    $ sudo apt dist-upgrade
    
    Well it actually adds a couple of files to your system, these files are usually added to the /boot directory.

    You will see multiple files for different kernel versions:

    vmlinuz - this is the actual linux kernel
    initrd - as we've discussed before, the initrd is used as a temporary file system, used before loading the kernel
    System.map - symbolic lookup table
    config - kernel configuration settings, if you are compiling your own kernel, you can set which modules can be loaded
    If your /boot directory runs out of space, you can always delete old versions of these files or just use a package manager,


     The kernel in itself is a monolithic piece of software, when we want to add support for a new type of keyboard,
     we don't write this code directly into the kernel code. 
     Just as we wouldn't meld a bike rack to our car (well maybe some people would do that). 
     Kernel modules are pieces of code that can be loaded and unloaded into the kernel on demand. 
     They allow us to extend the functionality of the kernel without actually
     adding to the core kernel code. We can also add modules and not have to reboot the system (in most cases).



     View a list of currently loaded modules

    $ lsmod
    Load a module

    $ sudo modprobe bluetooth
    Modprobe loads tries the module from /lib/modules/(kernel version)/kernel/drivers. 
    Kernel modules may also have dependencies, modprobe loads our module dependencies if they are not already loaded.

## Remove a module

    $ sudo modprobe -r bluetooth
## Load on bootup

    You can also load modules during system boot, instead of temporarily loading them with modprobe (which will be unloaded when you reboot). 
    Just modify the /etc/modprobe.d directory and add a configuration file in it like so:

    pete@icebox:~$ /etc/modprobe.d/peanutbutter.conf


    options peanut_butter type=almond


    A bit of a outlandish example, but if you had a module named peanut_butter and you wanted to add a kernel parameter for type=almond, 
    you can have it load on startup using this configuration file. 
    Also note that kernel modules have their own kernel parameters so you'll want to read about the module specifically to find out more.

## Do not load on bootup

    You can also make sure a module does not load on bootup by adding a configuration file like so:

    pete@icebox:~$ /etc/modprobe.d/peanutbutter.conf


    blacklist peanut_butter
