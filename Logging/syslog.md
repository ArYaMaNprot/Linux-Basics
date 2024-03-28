The syslog service manages and sends logs to the system logger. 
Rsyslog is an advanced version of syslog, most Linux distributions should be using this new version. 
The output of all the logs the syslog service collects can be found at /var/log/syslog (every message except auth messages).

To find out what files are maintained by our system logger, look at the configuration files in /etc/rsyslog.d:


pete@icebox:~$ less /etc/rsyslog.d/50-default.conf 

Let's actually see logging in action, you can manually send a log with the logger command:
  
  logger -s Hello

