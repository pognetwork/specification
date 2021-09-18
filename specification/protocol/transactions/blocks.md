# Blocks

In POG, transactions are contained in blocks. These blocks must be verified by more than 60% of prime delegates to be accepted by the network.
Blocks contain sevaral fields:

## Block Header

| field     | type  | size    | description                                                                                 |
| --------- | ----- | ------- | ------------------------------------------------------------------------------------------- |
| timestamp | u64   | 64 bit  | seconds of UTC time since Unix epoch (defined by the first node which sees the transaction) |
| signature | bytes | 512 bit | signature of the block contents                                                             |
| publicKey | bytes | 256 bit | account's public key                                                                        |

## Block Contents

| field         | type              | size         | description                                                 |
| ------------- | ----------------- | ------------ | ----------------------------------------------------------- |
| version       | varint            | up to 32 bit | block version                                               |
| signatureType | varint            | up to 32 bit | only Ed25519 currently                                      |
| height        | varint (unsigned) | up to 64 bit | the block height (block index); starts at 0                 |
| balance       | varint (unsigned) | up to 64 bit | the new account ballance after applying all transactions    |
| previous      | bytes (optional)  | 256 bit      | hash of the previous block                                  |
| transactions  | Transaction       | variable     | all transactions included in the block (TODO: limit amount) |

## Transactions

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

### Transaction IDs

To ensure transaction IDs are unique, they're calculated as follows:

```
tx_id = sha3(block_hash + tx_hash);
```

## Broadcasting Blocks

Newley created blocks need to be published to all prime delegates.
These then publish their decision (accept or deny the block) to all other prime delegates and a subset of non-prime representatives (gossip about gossip).

To learn more about delegates, check out our [page about them](../consensus/delegates.md)
