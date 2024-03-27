There is a service called syslog that sends this information to the system logger.

Syslog actually contains many components, one of the important ones is a daemon running called syslogd (newer Linux distributions use rsyslogd), 
that waits for event messages to occur and filter the ones it wants to know about, 
and depending on what it's supposed to do with that message, it will send it to a file, your console or do nothing with it.

You would think that this system logger is the centralized place to manage logs, 
but unfortunately it's not. You'll see many applications that write their own logging rules 
and generate different log files, however in general the format of logs should include a timestamp and the event details.

Here is an example of a line from syslog:


pete@icebox:~$ less /var/log/syslog
