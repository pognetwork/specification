<!-- prettier-ignore -->
!!! warning
    This page still needs some love, check back later!

# Delegated Proof of Importance - Our Consensus Mechanism

## What Is a Consensus Mechanism?

The consensus algorithm is the backbone of any cryptocurrency. It is the method used to agree on data in a distributed system. In the case of pog.network, this data is the blocks that are part of the network. Consider a group of people wanting to play a game. If most of them decide to play Monopoly, consensus has been reached, and everyone has to abide by their decision.

Consensus mechanisms have been used for decades for scaling databases, application servers, and other infrastructure. Only recently have new consensus mechanisms been invented, which take this a step further and make this process trust-less. This means badly behaving members can be securely excluded or split off without destroying the rest of the network.

Consensus mechanisms are engineered to make 51%-attacks infeasible so to prevent bad actors from taking over the network.

## What is Proof of Importance

### History

The first generation of Cryptocurrencies uses Proof-of-Work based systems. Here, the network was secured by cryptographically proving that you have spend effort on something, normally wasting energy and resources.

Because this is obvously not sustainable in the age of Climate Change and Chip shortages, a new model was introduced: Proof of Stake. Here, instead of spending resources, you had to stake your money on being correct. This essentially means that you had to put your money at risk to give everyone confidence in your decisions, since if you behaved badly, the rest of the network would repremand you and burn your funds.

This approach introduces a few new challenges, which we aim to solve:

- **Nothing At Stake Problem**
- **How is Value created?**
- **Preventing an Aristocracy**

### Our Approach

Instead of only looking at the net worth of network members, we have a unique algorithm to determine everyone's importance to the network. The different factors have been fine-tuned to:

- discourage spamming the network
- give advantages to smaller wallets (we don't want money to equal power)
- discourage gaming the system
- encourage being active in the network and not holding onto your funds for ages

We do this fully knowing that people will try to optimize and gain an advantage, which is fine. These values can be further tweaked when the network is online through hard forks, and we know very well that it is impossible to make the system perfect; it's just possible to make it harder to be a bad actor.

Only a few members, those with the highest importance, vote in the network. These are also called the Prime Delegates. This system can be compared to representative democracy, with the significant difference being that the network is in constant flux. Everyone can change whom they vote for whenever they want, making reprimanding bad actors fast and efficiently.

Like in nano[[1]](https://docs.nano.org/protocol-design/orv-consensus/), there is no economic incentive of running a node to prevent a list of issues[[2]](https://medium.com/@clemahieu/emergent-centralization-due-to-economies-of-scale-83cc85a7cbef). The only incentive is the health of the ecosystem.

## Factors for Voting Power Calculation

### Calculation of Importance

- **Higher balance in an account increases importance**<br/>
  Straight line graph. As balance increases, importance increases.
  $importance=x*normalization$
- **Negative cashflow (money leaving the account) increases importance**<br/>
  Straight line graph. As cashflow decreases, importance increases.
  $importance=-x*normalization$
- **A healthy amount of blocks created increases importance**<br/>
  Slight curve. As blocks per week increase, the importance increases. At a specific amount of blocks per week, importance decreases.
  This mitigates spamming for importance.<br/>
  \\(importance=(\frac{1}{(\frac{x}{p}-1)^{2m} + 1})\*normalization\\)
- **The older an account, the higher the importance**<br/>
  A slight increase that slows down as the account gets older. Its negative in the first couple of weeks for an account to mitigate spam accounts
  $importance=(\log_{10}({x + 1.0}) + \sqrt{(0.1x + 3.0)} - 4.0)*normalization$

- **Being inactive in the network decreases importance**<br/>
  Percentage cut. If cashflow is exactly 0, a percentage of the balance is used to decrease importance<br/>
  _(this may be changed to a percentage of overall importance and we may introduce a buffer around 0 to mitigate micro spending)_

### Future Ideas

- **Sending coins to "green wallets" increases importance**<br/>
  Green wallets are wallets that donate money to green causes. This idea is working progress.
- **Interactions with different accounts (network theory)**<br/>
  This idea suggests that wallets that interact with multiple different accounts should be more important
