# Delegates

## What are Delegates

Delegate accounts are active accounts on the network that vote on the legitamacy of a new block.

## How to become a Delegate

Over time, an account builds up [network importance](dpoi.md) that shows other accounts that a account can be trusted.
In addition to this, accounts on the network can transfer their importance to other accounts `delegate` their voting power and allow the more trusted account to have more voting power on the network. This results in a more secure network.
The 100 most important accounts will become `prime delegates`.

All this is done to find a balance between decentralization and speed. Delegates outside of the top 100 wouldn't meaningfully contribute to the vote total und thus enable a huge speedup in transaction processing times.

!!! note "100 might have performance problems"
This number may be changed at a later date after extensive network testing.

## Prime Delegates

Prime delegates have the opportunity to suggest green wallets and vote for other green causes that they wish the network to support.

## Delegate Keys

Delegates will have the option to create `private delegate keys` which enable them to have node operations running without exposing their private key on _hot_ servers which have the potential of being hacked. The mechanism for these hasn't been decided yet, we might introduce a new transaction type or update the delegate transaction type to be more of an catch-all for updating metadata associated with an account.
