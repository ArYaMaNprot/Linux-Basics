## Add a new route
    $ sudo route add -net 192.168.2.1/23 gw 10.11.12.3

## Delete a route
    $ sudo route del -net 192.168.2.1/23 
    You can also perform these changes with the ip command:

## To add a route
    $ ip route add 192.168.2.1/23 via 10.11.12.3

## To delete a route
    $ ip route delete 192.168.2.1/23 via 10.11.12.3
    or
    $ ip route delete 192.168.2.1/23
