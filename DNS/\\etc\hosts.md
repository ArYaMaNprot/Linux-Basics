## /etc/hosts
    The /etc/hosts file contains mappings of some hostnames to IP addresses. 
    The fields are pretty self explanatory, there is one for the IP address, the hostname and then any alias's for the host.

    pete@icebox:~$ cat /etc/hosts

    127.0.0.1       localhost

    127.0.1.1       icebox

    You'll typically see your localhost address listed as a default in this file. 
    You can also manage access to hosts by modifying the /etc/hosts.deny or /etc/hosts.allow files. 
    However, if you were security conscientious, this isn't really the way to go and you should be modifying your firewall rules instead.

    Let's see a fun example of /etc/hosts. Modify the file and add a line for:
    123.45.6.7  www.google.com
    Save the file and now go to www.google.com. 
    Having issues aren't you? Well that's because we just mapped www.google.com to a completely wrong IP address. 
    Since our hosts first look locally for IP address mappings, it never reaches DNS to find google.com.

## /etc/resolv.conf
    Traditionally, we've used a file called /etc/resolv.conf to map DNS name servers for more efficient lookups, 
    however with the improvements made to DNS this file is quite often irrelevant, 
    in fact, you can see in my example below that /etc/resolv.conf isn't managed manually. 
    Refer to your distribution specific settings to manage DNS name server mappings.    
