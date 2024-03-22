Upstart was developed by Canonical, so it was the init implementation on Ubuntu for a while, however on modern Ubuntu installations systemd is now used. 
Upstart was created to improve upon the issues with Sys V, such as the strict startup processes, blocking of tasks, etc. 
Upstart's event and job driven model allow it to respond to events as they happen.

To find out if you are using Upstart, if you have a /usr/share/upstart directory that's a pretty good indicator.

    For example, in the networking.conf file, it could say something as simple as:


    start on runlevel [235]

    stop on runlevel [0]

    This means that it will start setting up networking on runlevel 2, 3 or 5 and will stop networking on runlevel 0. There are many ways to write the configuration       file and you'll discover that when you look at the different job configurations available.

    The way that Upstart works is that:

    First, it loads up the job configurations from /etc/init
    Once a startup event occurs, it will run jobs triggered by that event.
    These jobs will make new events and then those events will trigger more jobs
    Upstart continues to do this until it completes all the necessary jobs
