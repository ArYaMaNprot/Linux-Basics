## ifconfig 
     The ifconfig tool allows us to configure our network interfaces, 
     if we don't have any network interfaces set up, the kernel's device drivers and the network won't know how to talk to each other. 
     Ifconfig runs on bootup and configures our interfaces through config files, but we can also manually modify them. 
     The output of ifconfig shows the interface name on the left side and the right side shows detailed information. 
     You'll most commonly see interfaces named eth0 (first Ethernet card in the machine), wlan0 (wireless interface), 
     lo (loopback interface). The loopback interface is used to represent your computer, it just loops you back to yourself. 
     This is good for debugging or connecting to servers running locally.

    The status of interfaces, can be up or down, as you can guess if you wanted to "turn off" an interface you can set it to go down. 
    The fields you'll probably look at the most in the ifconfig output is the HWaddr (MAC address of the interface), inet address (IPv4 address)
    and inet6 (IPv6 address). Of course you can see that the subnet mask and broadcast address are there as well. You can also view interface information at /etc/network/interfaces.

### To create an interface and bring it up
    $ ifconfig eth0 192.168.2.1 netmask 255.255.255.0 up
    This assigns an IP address and netmask to the eth0 interface and also turns it up.

### To bring up or down an interface
    $ ifup eth0
    $ ifdown eth0

### The ip command
    The ip command also allows us to manipulate the networking stack of a system. 
    Depending on the distribution you are using it may be the preferred method of manipulating your network settings.

Here are some examples of its use:

### To show interface information for all interfaces
    $ ip link show

### To show the statistics of an interface
    $ ip -s link show eth0

### To show ip addresses allocated to interfaces
    $ ip address show

### To bring interfaces up and down
    $ ip link set eth0 up
    $ ip link set eth0 down

### To add an IP address to an interface
    $ ip address add 192.168.1.1/24 dev eth0
