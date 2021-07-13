<!-- prettier-ignore -->
!!! warning
    The POG.network specification is still a Work-In-Progress and this page isn't finalized yet.

# Block-lattice

POG uses a form of Directed Acyclic Graphs (DAGs) which is based on a concept pioneered by the nano currency.
In this graph, each account essentially has their own blockchain which can only be controlled with their private key. This enables POG to not 'ellect' leaders like other currencys (e.g miners in bitcoin). This removes a major bottleneck of only one node verifying transactions and improves decentralization through independent verification by all prime delegates.

## The Datastructure

```mermaid
sequenceDiagram
    Alice ->> Alice: Open Account
    Alice ->> Alice: Send 10 POG to John
    Bob ->> Bob: Open Account
    John ->> John: Open Account
    Bob ->> Bob: Send 10 Pog to Alice
    John ->> John: Recieve 10 POG from Alice
    Alice ->> Alice: Recieve 10 POG from Bob
```

## Accounts

## Blocks
