Initially, POGs supply will be fixed, see [distribution](./distribution.md).
There isn't any "mining" happening, so no new coins are distributed with block rewards.
Still, we want to add fees to our system, because sustainability is our main goal.

# Inflation

To ensure long-term success and stability, we aim for a 2% yearly inflation rate.
Instead of charging fees, our inflation rate will serve as a kind of "carbon tax".
This inflation will initialy be regualary conducted using hard forks, and hopefully later integrated more tightly into the network.
These hard forks will be automated and based on the currently active green wallets.

# Fees

Transactions on the network will be free, however to prevent being marked as spam, they can choose to burn a certain amount of pog.
Our spam algorithm will determine the likelyhood of a transaction being spam based on it's computational usage, size and an accounts previous transactions.
Prime delegates will provide an open API which will enable wallets to figure out the likelyhood of a transaction to be accepted by the network.
