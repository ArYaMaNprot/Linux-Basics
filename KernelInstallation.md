# Kernel Installation
To see what kernel version you have on your system, use the following command:

  $ uname -r

    You can install the Linux kernel in different ways, you can download the source package and compile from source or you can install it using package management tools.

    $ sudo apt install linux-generic-lts-vivid
    and then just reboot into the kernel you installed. Simple right? Kind of, you'll need to also install other linux packages such as the linux-headers, linux-image-generic, etc). 
    You can also specify the version number, so the above command can look like, sudo apt install 3.19.0-43-generic

    Alternatively, if you just want the updated kernel version, just use dist-upgrade, it performs upgrades to all package on your system:

    $ sudo apt dist-upgrade
