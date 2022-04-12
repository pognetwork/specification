# Delegates

## TLDR;

- Accounts have [importance](dpoi.md), which represents their power to make network decisions
- Users can delegate importance to other accounts
- The 128 most important online accounts are called Prime Delegates
- A single prime delegate can never have more than 25% of the total online voting power

## What Are Delegates

Delegate accounts are active accounts on the network that vote on the legitimacy of new blocks.
Over time, an account builds up [importance](dpoi.md), which represents the amount of power someone has for making important network decisions.
Users can also transfer this trust to other accounts by delegating their voting power, which enables a democratic system where a group of delegates are democratically elected. This election runs constantly, and the rest of the network can instantly reprimand bad behavior. These nodes are essentially the parliament of pog.network, where the top 128 delegates of the community decide the fate of the network and contribute to it's security and stability. These top delegates are called Prime Delegates.

All this is done to find a balance between decentralization and speed. Accounts outside the Prime Delegates wouldn't meaningfully contribute to the total vote. This can thus enable a colossal speedup in transaction processing times while also helping to reduce emissions by requiring fewer online servers. Further, this will prevent the stagnation of participation in the network seen in many DAO projects.

## How to Become a Prime Delegate

To become a delegate, you need to build a good reputation in the community and support the pog.network ecosystem. There is no monetary incentive for running a delegate node outside of increasing the value of the network. To start being a delegate, you need to run a full node on stable server infrastructure and campaign for other accounts to delegate their power to you.

## Tasks of a Prime Delegate

Prime Delegates

- vote on which new blocks to include
- have the opportunity to suggest green wallets and vote for other green causes that they wish the network to support, see [green addresses](./../../glossary.md#green-addresses)
- keep the network honest by actively checking the honesty of all other Prime Delegates

## Delegate Keys

Delegates will have the option to create `private delegate keys`, which enable them to have node operations running without exposing their private key on _hot_ servers (which have the potential of being hacked. For this, we will soon introduce a new transaction type.
