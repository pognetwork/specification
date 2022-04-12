# Block-lattice

POG uses a form of Directed Acyclic Graphs (DAGs), which is based on a concept pioneered by the nano currency.
Each account has its blockchain in this graph, which can only be controlled with its private key. This enables POG to not 'elect' leaders like other currencies (e.g. miners in bitcoin), removes a significant bottleneck of only one node verifying transactions, and improves decentralization through independent verification by all Prime Delegates.

## The Datastructure

```mermaid
sequenceDiagram
    Alice ->> Alice: Open Account
    Alice ->> Alice: Send 10 POG to John
    Bob ->> Bob: Open Account
    John ->> John: Open Account
    Bob ->> Bob: Send 10 Pog to Alice
    John ->> John: Receive 10 POG from Alice
    Alice ->> Alice: Receive 10 POG from Bob
```

## Accounts

## Blocks
