# Glossary

### Nodes

Nodes are Computers/Servers which run pog's software. This software is what makes pog.network possible: anyone is able to create one of these to ensure and verify the safety and accuracy of the network and create consensus.

### Consensus Mechanism

Finding consensus essentially means every node agreeing on reality: what transactions happened and when.
To find out more about pog.network's consensus algorithm, check out [Delegated Proof of Importance](protocol/consensus/dpoi.md).

### Delegates / Delegate Nodes

Delegate Nodes are nodes which are part of the top 128 nodes with the highest online importance score. They play a crucial part in the stability of the network by voting on [green addresses](#green-addresses) and by their votes being rebroadcasted by all other nodes.

### Green Addresses

Green Addresses are addresses of vetted, transparent and climate focused organizations or organizations supporting these. They live in a global pool of approved green addresses. To be added to this pool, more than 70% of online importance needs to vote in favor of the addition. However only 40% is required to remove these addresses again.

### Importance Score

Check out [Delegated Proof of Importance](protocol/consensus/dpoi.md)

### Online Importance Score

The total online importance score is calculated by sampling the total importance of all nodes every hour and by taking the mean of these values across a week.
