<!-- prettier-ignore -->
!!! warning
    This page is not final and still needs some work

# Overview

While the next pages will go more into detail of the how and why, we want to give a rough overview of the components that make up our currency.
For a more technical overview, check out champ's documentation [here](https://pog.network/champ/overview/).

POG is a cryptocurrency similar to the big players like Bitcoin and Ethereum, with two major differences:

1. **The Datastructure**
   Instead of a single Blockchain where one block comes after each other, we're using a more advanced Datastructure called [Block-lattice](ledger.md).
   Here, each user essentially has their own "blockchain" in which only they can append new blocks. To exchange funds, we have special transaction types to receive and send funds (and data) to other "account chains".
2. **The Consensus Algorithm**
   We're using a specialized version of **Proof of Stake**, which we're calling **Delegated Proof of Importance**.
   Let's take bitcoin as an example. Here new blocks are added by the first node (member of the network) who can proof that they have complete a certain amount of work (in extremely simplified terms). At pog, instead of requiring wasteful calculations which are harmful to the environment, nodes are delegated by the rest of the network to do the verification of new blocks. These nodes are comparable to a voted parliament, which handles important questions and votes on features relevant to our cryptocurrency.
