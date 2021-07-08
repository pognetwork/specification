# Blocks

In POG, one transaction is contained and limited to one block which can only be added to the account owners chain. The blocks must be verified by the delegates to be accepted by the network. If the block is accepted, it it broadcasted to other accounts.

There are 4 different types of blocks:

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
    Assigns a new [delegate](consensus/delegates.md) for the account.
