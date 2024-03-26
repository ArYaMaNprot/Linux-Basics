 A continuous monitoring tool, something that will collect, report and save your system activity information. 
 In this lesson we will go over a great tool to use sar.
##  Installing sar
 Sar is a tool that is used to do historical analysis on your system, 

## Setting up data collection
    Usually once you install sysstat, your system will automatically start collecting data, 
    if it doesn't you can enable it by modifying the ENABLED field in /etc/default/sysstat.

## Using sar

    $ sudo sar -q
    This command will list the details from the start of the day.

    $ sudo sar -r
    This will list the details of memory usage from the start of the day.

    $ sudo sar -P
    This will list the details of CPU usage.

    To see a view of a different day,
    you can go into /var/log/sysstat/saXX where XX is the day you want to view.

    $sar -q /var/log/sysstat/sa02first make sure you have it installed by installing the sysstat package sudo apt install sysstat.
