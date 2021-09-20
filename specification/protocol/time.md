# Time

Time is important in various places, notably for transactions and voting power calculations. To ensure cryptographically secure agreed uppon time across the network, we're utilizing the [roughtime protocol](https://blog.cloudflare.com/roughtime/).

In most places we do not need millisecond accuracy, but we need to be very sure on roughly the correct time to enable smart contracts, voting power calculations and even protocol upgrades.

Optionally, node operators can enable a separate roughtime server to share their timestamp with the rest of the network, otherwise publicly available servers will be used.
The overall precision has to be within 10 seconds to enable our use case (especially protocol upgrades where we want to minimize network downtime).
