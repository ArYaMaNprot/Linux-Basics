## Manage Logging
The logrotate utility does log management for us. 
It has a configuration file that allows us to specify how many and what logs to keep,
how to compress our logs to save space and more. 
The logrotate tool is usually run out of cron once a day and the configuration files can be found in /etc/logrotate.d.

There are other logrotating tools you can use to manage your logs, but logrotate is the most common one.
