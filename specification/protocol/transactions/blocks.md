# Blocks

In POG, transactions are contained in blocks. These blocks must be verified by more than 60% of prime delegates to be accepted by the network.
Blocks contain several fields:

## Block Header

| field     | type  | size    | description                                                                                 |
| --------- | ----- | ------- | ------------------------------------------------------------------------------------------- |
| timestamp | u64   | 64 bit  | seconds of UTC time since Unix epoch (defined by the first node which sees the transaction) |
| signature | bytes | 512 bit | signature of the block contents                                                             |
| publicKey | bytes | 256 bit | account's public key                                                                        |

## Block Contents

| field         | type              | size         | description                                                                 |
| ------------- | ----------------- | ------------ | --------------------------------------------------------------------------- |
| version       | enum              | up to 32 bit | block version                                                               |
| signatureType | varint            | up to 32 bit | only Ed25519 currently                                                      |
| height        | varint (unsigned) | up to 64 bit | the block height (block index); starts at 0                                 |
| balance       | varint (unsigned) | up to 64 bit | the new account ballance after applying all transactions                    |
| previous      | bytes (optional)  | 256 bit      | hash of the previous block                                                  |
| transactions  | Transaction       | variable     | all transactions included in the block (limited to 255 unique transactions) |

## Block IDs

Block IDs have to be unique as long as the block content is a valid new block, so block hashes are their ids.

## Broadcasting Blocks

Newley created blocks need to be published to all prime delegates.
These then publish their decision (accept or deny the block) to all other prime delegates and a subset of non-prime representatives (gossip about gossip).

To learn more about delegates, check out our [page about them](../consensus/delegates.md)

# Transactions

There are 4 different types of transactions:

<!-- prettier-ignore-start -->
=== "Open"

    To create a new account, the account owner must create the open block.

    | field | type | size     | description                                   |
    | ----- | ---- | -------- | --------------------------------------------- |
    | type  | enum | variable | Managed Account (0) or Autonomous Account (1) |

=== "Send"
    This sends the funds out of the owners account and sets the block to pending until it is `claimed` by a receiving account.

    | field    | type   | size         | description                              |
    | -------- | ------ | ------------ | ---------------------------------------- |
    | reviever | bytes  | up to 32 bit | account pog is being transfered to       |
    | amount   | uint64 | 64 bit       | amount of pog transfered to that account |
    | data     | bytes  | variable     | any data associated with the transaction |

=== "Claim"
    Since only the account owner can add blocks to their own account chain, receiving funds involves creating a `claim` block to collect the pending transaction.

    | field         | type  | size         | description               |
    | ------------- | ----- | ------------ | ------------------------- |
    | transactionID | bytes | up to 32 bit | transaction being claimed |

=== "Delegate"
    Assigns a new [delegate](../consensus/delegates.md) for the account.

    | field          | type  | size    | description             |
    | -------------- | ----- | ------- | ----------------------- |
    | representative | bytes | 192 bit | account being delegated |
<!-- prettier-ignore-end -->

### Transaction IDs

To ensure transaction IDs are unique, they're calculated as follows:

```
tx_id = sha3(block_hash + tx_hash);
```

# ID Encoding

Block and Transaction IDs should always be encoded as bytes when used over the wire. When presented on user-facing interfaces, like for addresses z-base-32 should be used.
However, in addition to this they should be prefixed with `blk-`/`txn-` (there prefixes should be optional but be displayed by default).
Example: `blk-t518zdq98f6yah4c18zgyirkyouz5zq4wzaj8gw3wuej897hs5jo` (56 chars)
