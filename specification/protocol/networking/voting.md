# Voting

## Voting for Inclusion of Blocks

Voting is the central mechanism through which new blocks are added to the pog.network network.

Users can submit blocks to any node; however, only Prime Delegates can start a voting round. Once a prime delegate receives a block, they must forward it to all other Prime Delegates and ten non-prime-delegate nodes.

This is called a `vote-proposal`, and includes the sender's decision signed with their private key. Once a prime delegate receives such a vote proposal, they must cast their vote and send it to all other Prime Delegates (and ten non-prime delegate nodes). This process ensures that the original delegate doesn't exclude anyone; however, nodes need to keep track of their sent votes not to process blocks multiple times.

Once a quorum has been reached (60% of online voting power has voted), all nodes who see this quorum must send a `final-vote` to all other Prime Delegates (and ten non-prime-delegates). After this, they can include the block in the network once more than 60% of online nodes have confirmed their final vote again (by also sending a final vote back).

## Voting for Green Wallets

More than 70% of online importance needs to vote in favor of adding a green wallet. However, only 40% is required to remove these addresses again. The process through which this happens is yet to be specified; however, it should be similar to block votes.
