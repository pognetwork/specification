# Blocks

In POG, transactions are contained in blocks. The blocks must be verified by more than 50% of prime delegates to be accepted by the network.

There are 4 different types of transactions:

<!-- prettier-ignore -->
=== "Open"
    To create a new account, the account owner must create the open block.

    !!! note "Idea"
        This block might be avoided by using the first `claim` block

<!-- prettier-ignore -->
=== "Send"
    This sends the funds out of the owners account and sets the block to pending until it is `claimed` by a receiving account.

<!-- prettier-ignore -->
=== "Claim"
    Since only the account owner can add blocks to their own account chain, receiving funds involves creating a `claim` block to collect the pending transaction.

<!-- prettier-ignore -->
=== "Delegate"
    Assigns a new [delegate](../consensus/delegates.md) for the account.

## Broadcasting Blocks

Newley created blocks need to be published to all prime delegates.
These then publish their decision (accept or deny the block) to all other prime delegates and a subset of non-prime representatives (gossip about gossip).

To learn more about delegates, check out our [page about them](../consensus/delegates.md)
