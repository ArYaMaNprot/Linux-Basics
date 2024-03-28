The syslog service manages and sends logs to the system logger. 
Rsyslog is an advanced version of syslog, most Linux distributions should be using this new version. 
The output of all the logs the syslog service collects can be found at /var/log/syslog (every message except auth messages).

To find out what files are maintained by our system logger, look at the configuration files in /etc/rsyslog.d:


pete@icebox:~$ less /etc/rsyslog.d/50-default.conf 

Let's actually see logging in action, you can manually send a log with the logger command:
  
  logger -s Hello

### /var/log/messages

    This log contains all non-critical and non-debug messages,
    
    includes messages logged during bootup (dmesg), auth, cron, 
    
    daemon, etc. Very useful to get a glimpse of how your machine is acting.

#### /var/log/syslog

    This logs everything except auth messages, it's extremely useful for debugging errors on your machine.
    
    These two logs should be more than enough when troubleshooting issues with your system, 
    
    However, if you just want to view a specific log component, there are also separate logs for those as well.
