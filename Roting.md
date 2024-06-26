## Distance vector protocol
    Distance vector protocols determine the path of other networks using the hop count a packet takes across the network. 
    If network A was 3 hops away and network B was next to network A, then we assume it must be 4 hops away. 
    In distance vector protocols, the next route would be the one with the least amount of hops.

    Distance vector protocols are great for small networks, when networks start to scale it takes longer for the routers to converge
    because it periodically sends the entire routing table out to every router.
    Another downside to distance vector protocols is efficiency, it chooses routes that are closer in hops, but it may not always choose the most efficient route.

    One of the common distance vector protocols is RIP (Routing Information Protocol), 
    it broadcasts the routing table to every router in the network every 30 seconds.
    For a large network, this can take some serious juice to pull off, because of that RIP limits it's hop count to 15.

## Link state protocols
    Link state protocols are great for large scale networks, they are more complex than distance vector protocols, 
    however a large upside is their ability to converge quickly, this is because instead of periodically sending out the whole routing table, 
    they only send updates to neighboring routes. 
    They use a different algorithm to calculate the shortest path first and construct 
    their network topology in the form of a graph to show which routers are connected to other routers.

    One of the common link state protocols is OSPF (Open Shortest Path First), 
    it only updates the routing tables if there was a network change. It doesn't have a hop limit.
