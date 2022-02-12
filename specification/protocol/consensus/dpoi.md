<!-- prettier-ignore -->
!!! warning
    This page is not final and still needs some work

# Delegated Proof of Importance - our consensus Mechanism

## Abstract

The consensus is the backbone of the crypto currency. It handles voting on the blocks to be added to a network.
The voting is only done by a small number of nodes in the network with the highest importance or voting power, the Prime Delegates.
Importance (or voting power. These will be used interchangeably) is used to filter out the most important nodes on a node in a network which will then gain the status of Prime Delegate and be tasked with voting on new blocks from the network. The Prime Delegates use their earned importance for voting which ensures that Wallets that are most active in the network will govern the network.
A number of factors are used to calculate the earned importance.

Like in nano[[1]](https://docs.nano.org/protocol-design/orv-consensus/), there is no economic incentive of running a node to prevent a list of issues[[2]](https://medium.com/@clemahieu/emergent-centralization-due-to-economies-of-scale-83cc85a7cbef). The only incentive is the health of the ecosystem.

## Factors for voting power calculation

These factors will be balance to make it harder for it to be abused.

### Currently

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

### Future ideas

- **Sending coins to "green wallets" increases importance**<br/>
  Green wallets are wallets that donate money to green causes. This idea is working progress.
- **Interactions with different accounts (network theory)**<br/>
  This idea suggests that wallets that interact with multiple different accounts should be more important
