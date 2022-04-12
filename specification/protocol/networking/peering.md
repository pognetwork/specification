# Peering

To spread information out across the entire network, we deploy a variety of methods.

- Prime Delegates are always connected to all other Prime Delegates and 15 other nodes
- normal nodes are always connected to 20 other normal nodes and 5 Prime Delegates
- every keepalive packet include a list of 10 randomly selected other nodes and serve as the network discovery protocol
- in case a node deviates from the rest of the network, it can connect to an archive node (which archives all past votes from Prime Delegates) and use these to verify new blocks where a deviation to the rest of the network occured
