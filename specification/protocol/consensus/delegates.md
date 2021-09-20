# Delegates

## What are Delegates

Delegate accounts are active accounts on the network that vote on the legitimacy of a new block.
Over time, an account builds up [importance](dpoi.md) which represents the amount of say someone has for making important network decisions.
This trust can also be transferred to other accounts by `delegate` your voting power and enables the creation of a democratic system where a group of delegates are democratically elected. This election runs constantly, so bad behavior can be instantly reprimanded by the greater network. This is essentially the parliament of pog.network, where the top 128 delegates of the community decide the fate of the network and contribute to it's security and stability.

<!-- prettier-ignore -->
!!! note "Delegates Name"
    This name may be changed at a later date or be used to address any account with importance on the network. Maybe use a different name for the Top 128?

All this is done to find a balance between decentralization and speed. Accounts outside of the top 128 wouldn't meaningfully contribute to the vote total and can thus enable a huge speedup in transaction processing times while also helping to reduce emissions.

<!-- prettier-ignore -->
!!! note "128 might have performance problems"
    This number may be changed at a later date after extensive network testing.

A single delegate can never have more than 25% of the total online voting power.

## How to become a Delegate

To become a delegate, you need to build a good reputation in the pog.network community and support the pog ecosystem. There is no monetary incentive of running a delegate node outside of increasing the value of the network. To start being a delegate, you just need to run a full-node on a good server infrastructure and campaign for votes.

## Tasks of a Delegate

- Delegates have the opportunity to suggest green wallets and vote for other green causes that they wish the network to support, see [green addresses](./../../glossary.md#green-addresses).

## Delegate Keys

Delegates will have the option to create `private delegate keys` which enable them to have node operations running without exposing their private key on _hot_ servers which have the potential of being hacked. The mechanism for these hasn't been decided yet, we might introduce a new transaction type or update the delegate transaction type to be more of an catch-all for updating metadata associated with an account.
