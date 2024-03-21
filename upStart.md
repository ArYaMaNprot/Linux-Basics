Upstart was developed by Canonical, so it was the init implementation on Ubuntu for a while, however on modern Ubuntu installations systemd is now used. 
Upstart was created to improve upon the issues with Sys V, such as the strict startup processes, blocking of tasks, etc. 
Upstart's event and job driven model allow it to respond to events as they happen.

To find out if you are using Upstart, if you have a /usr/share/upstart directory that's a pretty good indicator.
