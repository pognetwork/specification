!!! warning
    The POG.network specification is still a Work-In-Progress and this page isn't finalized yet.

# Our consensus Mechanism

### Delegated Proof of Importance

Consensus only needs to be reached for double-spend transactions.
To reach consensus quickly, a group of representatives are ellected by all users.
The weight of these representatives is determined by the "importance score" of all it's users. 
This score is calculated from a variety of factors like coins held, age of these coins, amount of active transactions and more (the details aren't 100% clear yet, we might want to look at NIM's implementation of this)

Like in nano[[1]](https://docs.nano.org/protocol-design/orv-consensus/), there is no economic incentive of running a node to prevent a list of issues[[2]](https://medium.com/@clemahieu/emergent-centralization-due-to-economies-of-scale-83cc85a7cbef). The only incentive is the health of the ecosystem. 

## Factors for voting power calculation
* age of account
* coins in account
* interactions with other accounts (network theory) (importance of these accounts)
* All of these factors will be limited
* sending coins to "green adreses"