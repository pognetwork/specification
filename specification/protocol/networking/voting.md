<!-- prettier-ignore -->
!!! warning
    This page is not final and still needs some work

# Voting

## Voting for inclusion of blocks

Voting is the central mechanism through which new blocks are added to the pog network.

Blocks can be submitted to any node, however only prime delegates can start a voting round. Once a prime delegate recieves a block, it must forward it to all other prime delegates (and 10 non-prime-delegates).

This is called a `vote-proposal`, and includes the senders decision signed with their own private key. Once a prime delegate recieves such a vote proposal, they must cast their own vote and send it to all other prime delegates (and 10 non-prime delegate nodes). This ensures that the original delegate doesn't exclude anyone, however nodes need to keep track of their send votes to not process blocks multiple times.

Once quorum has been reached (60% of online voting power has voted), all nodes who see this quorum must send a `final-vote` to all other prime delegates (and 10 non-prime-delegates) and can include the block in the network once more than 60% of online nodes have confirmed their final vote (by also sending a final vote back).

## Voting for green wallets

To add a wallet as a green wallet, more than 70% of online importance needs to vote in favor of the addition. However only 40% is required to remove these addresses again. The process through which this happens is yet to be specified, however it should be similar to block votes.
