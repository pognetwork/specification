# Peering (Work-in-progress)

## Proposal 1

- prime delegates are always connected to all other prime delegates and 15 other nodes
- normal nodes are always connected to 20 other normal nodes and 5 prime delegates
- every keepalive packet include a list of 10 randomly selected other nodes and serve as the network discovery protocol
