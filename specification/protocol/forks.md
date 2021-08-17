# Forks

## Hard Forks

Hardforks are the mechanism POG uses to upgrade its protocol. Hard forks are a good thing: To improve is to change; to be perfect is to change often.

POG conducts hardforks different from other cryptocurrencies, since blocks are processed asynchronously.
Hard Forks need to go through a lenghty standertization process described in [Protocol Changes](./protocol-changes.md). When this document is finalized, a unix epoch (timestamp) will be chosen after which prime delegates which have updated their nodes to support the new changes will begin to broascast votes in favor of the changes to all prime delegates and a portion of non-prime delegates. Once 60% of online importance is reached, all nodes will stop processing blocks for 60 seconds to allow the network to propagate the update to all nodes.

## Legacy Blocks

To update the block format, PPs can be introduced as part of a hard fork that update the block version (We want everyone to be onboard with new changes and not soft-fork the network). The old transaction format will then be depricated until a later hardfork disables it for good (We want to avoid having old code lying around that could introduce issues). This could also be used as an alternative to the hard fork mechanism described above by using the block version field to signal switching over to a new protocol version.

# Hard Fork #1

The first Hard Fork is already planned. To ensure a smooth start, the initial version of pog will not include support for send and recieve transactions which will be enabled later on in this hardfork.

This is to ensure a diverse selection of Prime Delegates and provide a certain amount of security by not putting any funds at risk in case a critical vulnerability is discovered.
