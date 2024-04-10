The Internet Control Message Protocol (ICMP) is part of the TCP/IP protocol suite, 
it used to send updates and error messages and is an extremely useful protocol used for debugging network issues such as a failed packet delivery.

Each ICMP message contains a type, code and checksum field. 
The type field is the type of ICMP message, the code is a sub-type and describes more 
information about the message and the checksum is used to detect any issues with the integrity of the message.

Let's look at some common ICMP Types:

Type 0 - Echo Reply
Type 3 - Destination Unreachable
Type 8 - Echo Request
Type 11 - Time Exceeded
When a packet can't get to a destination, Type 3 ICMP message is generated, within Type 3 there are 16 code values that will further describe why it can't get to the destination:

Code 0 - Network Unreachable
Code 1 - Host Unreachable
etc..etc..

netstat -at
The netstat -a command shows the listening and non-listening sockets for network connections, the -t flag shows only tcp connections.

The columns are as follows from left to right:

Proto: Protocol used, TCP or UDP.
Recv-Q: Data that is queued to be received
Send-Q: Data that is queued to be sent
Local Address: Locally connected host
Foreign Address: Remotely connected host
State: The state of the socket
See the manpage for a list of socket states, but here are a few:

LISTENING: The socket is listening for incoming connections, 
remember when we make a TCP connection our destination has to be listening for us before we can connect.
SYN_SENT: The socket is actively attempting to establish a connection.
ESTABLISHED: The socket has an established connection
CLOSE_WAIT: The remote host has shutdown and we're waiting for the socket to close
TIME_WAIT: The socket is waiting after close to handle packets still in the network

sudo tcpdump -i wlan0
  i for specific interface
