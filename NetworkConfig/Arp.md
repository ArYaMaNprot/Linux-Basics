Remember when we lookup a MAC address with ARP, it first checks the locally stored ARP cache on our system, 
you can actually view this cache:

The ARP cache is actually empty when a machine boots up, it gets populated as packets are being sent to other hosts. 
If we send a packet to a destination that isn't in the ARP cache, the following happens:

The source host creates the Ethernet frame with an ARP request packet
The source host broadcasts this frame to the entire network
If one of the hosts on the network knows the correct MAC address, it will send a reply packet and frame containing the MAC address
The source host adds the IP to MAC address mapping to the ARP cache and then proceeds with sending the packet
You can also view your arp cache via the ip command:


$ ip neighbour show

