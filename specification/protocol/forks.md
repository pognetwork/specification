# Forks

## Epochs

Epochs are the mechanism POG uses to upgrade its protocol, enabling us to conduct hard forks. Hard forks are a good thing: Improving is changing; being perfect is to change often.

POG conducts hard forks different from other cryptocurrencies since blocks are processed asynchronously.
Hard Forks need to undergo a lengthy standardization process described in [Protocol Changes](./protocol-changes.md). A Unix epoch (timestamp) will be chosen when this document is finalized. Prime Delegates who have updated their nodes to support the new changes will begin to broadcast votes in favor of the changes to all Prime Delegates and a portion of non-Prime Delegates. Once 60% of online importance (Prime Delegates) have voted, the proposal is accepted.

Depending on the proposed changes, they either get set into motion immediately (if they are backward compatible), or a transition phase begins.
In such a transition phase, both blocks confronting the new and the old rules are processed. For example, this might be the case if the fees are updated to reflect current market prices better.

The exact durations of these phases are up to the PIP-Proposal.

## Ethics of Forks

Transactions on our network are immutable. We will never, nor can we, reverse a legitimate transaction.
A legitimate transaction is any transaction signed by a legitimate private key, simple as that.

One exception to this is smart contract data. While transactions won't be able to be reversed, we will try to take the necessary steps for our network not to get poisoned by illicit material. If CP makes its way onto our network, the next hard fork will include code to disable the associated smart contracts and delete their related data.

Further, large files like videos and music are generally not allowed to be stored in the network and are considered spam, which (with the approval of our Prime Delegates) can also be removed.

## Hostile Takeovers

We are aware that our concept might be susceptible to Prime Delegates, which go against the values of our network. This might someday necessitate a split in the network, which is expected. Our protocol has the concept of different chains, so this process will be done smoothly, even if we don't reach 60% of the votes.

If this amount of votes is not reached for a proposal, it is possible to create a new proposal that will create a new fork off of the chain.
One such chain might also choose to make the transition irreversible. In this case, account address generation can be slightly tweaked, so a new chain can receive transactions from another chain but not send them back.

# Hard Fork #1

The first Hard Fork is already planned. To ensure a smooth start, the initial version of pog.network will not include support for sending and receiving transactions, which will be enabled later in this hard fork.

This is to ensure a diverse selection of Prime Delegates and provide a certain amount of security by not putting any funds at risk if a critical vulnerability is discovered.
