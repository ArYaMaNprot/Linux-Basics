The main purpose of init is to start and stop essential processes on the system. 

There are three major implementations of init in Linux, System V, Upstart and systemd. 

In this lesson, we're going to go over the most traditional version of init, System V init or Sys V (pronounced as 'System Five').

if you have an /etc/inittab file you are most likely running Sys V.

When using Sys V, the state of the machine is defined by runlevels which are set from 0 to 6. 

These different modes will vary depending on the distribution, but most of the time will look like the following:

    0: Shutdown
    1: Single User Mode
    2: Multiuser mode without networking
    3: Multiuser mode with networking
    4: Unused
    5: Multiuser mode with networking and GUI
    6: Reboot
    When your system starts up, it looks to see what runlevel you are in and executes scripts located inside that runlevel configuration. 
    The scripts are located in /etc/rc.d/rc[runlevel number].d/ or /etc/init.d. 
    Scripts that start with S(start) or K(kill) will run on startup and shutdown, respectively. 
    The numbers next to these characters are the sequence they run in.

    For example:


    pete@icebox:/etc/rc.d/rc0.d$ ls

    K10updates  K80openvpn        

    We see when we switch to runlevel 0 or shutdown mode, our machine will try to run a script to kill the updates services and then openvpn. 
    To find out what runlevel your machine is booting into, you can see the default runlevel in the /etc/inittab file. 
    You can also change your default runlevel in this file as well.
