Systemd uses goals to get your system up and running. 
Basically you have a target that you want to achieve and this target also has dependencies that we need to achieve. 
Systemd is extremely flexible and robust, it does not follow a strict sequence to get processes started. Here's what happens during the typical systemd boot:

    First, systemd loads its configuration files, usually located in /etc/systemd/system or /usr/lib/systemd/system
    Then it determines its boot goal, which is usually default.target
    Systemd figures out the dependencies of the boot target and activates them
    Similar to Sys V runlevels, systemd boots into different targets:

    poweroff.target - shutdown system
    rescue.target - single user mode
    multi-user.target - multiuser with networking
    graphical.target - multiuser with networking and GUI
    reboot.target - restart
    
    The default boot goal of default.target usually points to the graphical.target.

    The main object that systemd works with are known as units. 
    Systemd doesn't just stop and start services, it can mount filesystems, monitor your network sockets,
    etc and because of that robustness it has different types of units it operates. The most common units are:

    Service units - these are the services we've been starting and stopping, these unit files end in .service
    Mount units - These mount filesystems, these unit files end in .mount
    Target units - These group together other units, the files end in .target
