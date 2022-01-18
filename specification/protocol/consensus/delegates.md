# Delegates

## TLDR

- Accounts have [importance](dpoi.md) which represents their power to do network decisions
- Importance can be delegated to other accounts
- The 128 most important online accounts are called prime delegates
- A single prime delegate can never have more than 25% of the total online voting power

## What are Delegates

Delegate accounts are active accounts on the network that vote on the legitimacy of new blocks.
Over time, an account builds up [importance](dpoi.md), which represents the amount of power someone has for making important network decisions.
This trust can also be transferred to other accounts by delegating your voting power. This enables the creation of a democratic system, where a group of delegates are democratically elected. This election runs constantly, so bad behavior can be instantly reprimanded by the rest of the network. This is essentially the parliament of pog.network, where the top 128 delegates of the community decide the fate of the network and contribute to it's security and stability. These top delegates are called prime delegates.

All this is done to find a balance between decentralization and speed. Accounts outside of the prime delegates wouldn't meaningfully contribute to the vote total and this can thus enable a huge speedup in transaction processing times while also helping to reduce emissions by requiring fewer actively running servers. Further, this will prevent the stagnation of participation in the network which has been seen in many DAO-projects.

## How to become a Prime Delegate

To become a delegate, you need to build a good reputation in the community and support the pog ecosystem. There is no monetary incentive of running a delegate node outside of increasing the value of the network. To start being a delegate, you just need to run a full-node on a stable server infrastructure and campaign for other accounts to delegate their power to you.

## Tasks of a Prime Delegate

Prime Delegates

- vote on which new blocks to include
- have the opportunity to suggest green wallets and vote for other green causes that they wish the network to support, see [green addresses](./../../glossary.md#green-addresses)
- keep the network honest by actively checking the honesty of all other prime delegates

## Delegate Keys

Delegates will have the option to create `private delegate keys` which enable them to have node operations running without exposing their private key on _hot_ servers (which have the potential of being hacked. For this, we will soon introduce a new transaction type.
