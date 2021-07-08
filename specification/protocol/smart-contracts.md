<!-- prettier-ignore -->
!!! warning
    Smart Contracts aren't planned to be added in the first version of POG, but in a later update. This is a living document which will change over time.

# Smart Contracts

- In pog, Smart Contracts come in the form of **autonomous accounts**. These can be created by anyone using a `create` transaction and operate autonomously after this.
- These contracts are essentially a function which responds to events like send transactions to the account.
- Contracts have access to a append-only key-value database
- Contracts have access to a transactions
- Contracts have a main function where they can process arbitrary data send through `data` fields in transactions.
- The contract's code itself isn't stored on the blockchain but ipfs (would this make sense? still thinking about it)

Transactions which are send to an **autonomous account** trigger a new **execute** transaction, which can both send and recieve funds.

**execute** transactions can contain multiple **data** blocks which add new entried to the **AutAcc**'s database.

<!-- prettier-ignore -->
!!! note "Open Questions"
    - How do we prevent spam?
    - How do we calculate the cost of executing the code?
