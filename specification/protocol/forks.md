# Forks

## Epochs

Epochs are the mechanism POG uses to upgrade its protocol which enables us to conduct hard forks. Hard forks are a good thing: To improve is to change; to be perfect is to change often.

POG conducts hard forks different from other cryptocurrencies, since blocks are processed asynchronously.
Hard Forks need to go through a lengthy standardization process described in [Protocol Changes](./protocol-changes.md). When this document is finalized, a unix epoch (timestamp) will be chosen after which prime delegates which have updated their nodes to support the new changes will begin to broadcast votes in favor of the changes to all prime delegates and a portion of non-prime delegates. Once 60% of online importance (prime delegates) have voted, the proposal is accepted.

Now, depending on the proposed changes, they either get set into motion immediatly (if they are backwards compatible) or a transition phase begins.
In such a transition phase, both blocks confronting to the new and to the old rules are processed. This might e.g be the case if the fees are updated to better reflect current market prices.

The exact durations of these phases are up to the PP-Proposal.

## Ethics of forks

Transactions on our network are immutable. We will never nor can we reverse a legitimate transaction.
A legitimate transaction is any transaction signed by an legitimate private key, simple as that.

One exeption to this is smart contract data. While transactions won't be able to be reversed, we will try to take the neccecary steps for our network not to get poisoned by illicit material. In case CP makes its way onto our network, the next hard fork will include code to disable the associated smart contracts and delete their associated data.

Further, large files like videos and music are generally not allowed to be stored in the network and are considered spam, which (with the approval of our prime delegates) can also be removed.

## Hostile takeovers

We are aware that our concept might be succeptable to prime delegates which go against the values of our network. This might someday necessitate a split in the network, which is expected. Our protocol has the concept of different chains, so this process will be able to be done smoothly, even if we don't reach 60% of votes.

In case this amount of votes is not reached for a proposal, it is possible to create a new proposal which will create a new fork off of the chain.
One such chain might also choose to make the transition irreversable. In this case, account address generation can be slightly tweaked, so a new chain can recieve transactions from another chain, but not send them back.

# Hard Fork #1

The first Hard Fork is already planned. To ensure a smooth start, the initial version of pog will not include support for send and receive transactions which will be enabled later on in this hard fork.

This is to ensure a diverse selection of Prime Delegates and provide a certain amount of security by not putting any funds at risk in case a critical vulnerability is discovered.
