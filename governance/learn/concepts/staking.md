# Staking

## What does staking mean?

**A stake** is the amount of tokens a **Node Operator** puts aside and dedicates to a network’s active pool to contribute to governance and earn rewards. **Staking** is the verb used to describe this contribution. As cheqd is a Proof of Stake (PoS) Network, rewards can be earned in direct correlation with the amount of stake a Node Operator contributes.

## What is delegation?

Token holders, ‘**users’,** can **delegate** their tokens to Node Operators in order to earn rewards and participate in governance. Once a user has delegated tokens to a Node Operator and has tokens added to the active pool, they are known as **Participants.**

Users can delegate to multiple Node Operators at the same time to essentially diversify their bonded token portfolio.

## What does bonded mean?

Bonded tokens are those present in the active pool.

**Bonded** tokens = **staked** tokens by Node Operator + **delegated** tokens by a user.

## What is a User?

Users are persons who hold $CHEQ. Users are able to delegate tokens to Node Operators in order to have those tokens bonded and added to the active pool.

## What is a Participant?

Once a User has delegated tokens to a Node Operator and has tokens added to the active pool, they are known as "**Participants".**

## Why stake?

Participants may be eligible for a percentage of the rewards that Node Operators earn during the course of running a node. Node Operators may offer a certain **commission** for delegating to them. Participants earn rewards on the delegated tokens which are bonded to the Validator.

Therefore, you may want to delegate and stake your tokens for two reasons:

1. To participate in Network Governance;
2. To earn rewards proportionate to your stake in the Network.

## How do I choose which Node Operator to stake to?

Choosing your Node Operator or multiple Node Operators is an important decision. There are a few things you can take into consideration:

### **Commission rate**

The incentive for delegating tokens to a Node Operator is that you, as a participant, can earn rewards based on the stake of the Node Operator. Each Node Operator will have a **commission rate.** This is the percentage of tokens that the Node Operator will take as **commission** for running the infrastructure — the remaining percentage is distributed to the **Participants**.

### **Reputation**

You should be mindful about what reputation the Node Operator has. This is because the Node Operator may use your votes against the best interest of yourself and the community. As cheqd evolves, it is likely that there will become a political spectrum of Node Operators, who will cast their vote in different directions. Some may want to create chaos on the network and vote to disrupt the established paradigms, for example. A chaotic actor may lure users to delegate to them with a favourable commission rate and use the accumulated bonded tokens against the network’s best interests. For this reason, the choice of Node Operator you delegate to is very important.

### **Slashing and Validator Jail**

As the name would suggest, staking is not risk-free. As the word stake literally means “having something to gain or lose by having a form of ownership of something”, individuals should be wary of the risk, as we’ll come on to.

Think of it like this, if someone says to you “_what’s at stake_?” they are essentially asking: “_what am I risking in return for the potential rewards?_”

Node Operators might exhibit bad behaviour on the Network and, as a result, have their stake slashed. Slashing means taking the **stake** away from the Node Operator and adding it to the Community Pool.

Bad behaviour in this context usually means that the Node Operator has not signed a sufficient number of blocks as ‘pre commits’ over a certain period of time. This could be due to inactivity or potential malicious intent.

For example in June 2019, CosmosPool a former Cosmos validator experienced a server outage on their main node; downtime that resulted in its validator being temporarily jailed and its stake being slashed by 0.01%, including that of its delegators. This was what’s call [a downtime slashing incident (soft slashing) whereby the validator and delegators were punished for downtime proportionally to their stake](https://p2p.org/economy/slashing-overview-in-cosmos-network/) on the network. On top of this, further slashing later occurred as evidence was found of double block signing. Both CosmosPool AND the delegators’ stakes were slashed an additional 5% and the validator was permanently removed (‘tombstoned’).

Slashing can therefore certainly affect your delegated and bonded tokens, so it is important to consider your choice.

We currently have the slashing values to:

* **5% slashed** for double signing
* **1% slashed** for downtime (getting jailed)

These values may change over time through proposals that are voted on the network. You can read more about slashing [here](https://docs.cheqd.io/governance/learning-the-basics/validators/slashing).

## What if I change my mind about a Node Operator? Is it possible to redelegate or unbond from a Node Operator?

Yes, it is possible to instantly **redelegate** to a new Node Operator; however, you cannot ‘hop’ between Node Operators quickly. You must complete your redelegation to a Node Operator before moving again. If you want to completely withdraw and **unbond** your tokens, you need to be mindful that this process takes **two weeks** for the tokens to become available for use again. This **unbonding period** is an example of a parameter, which can be adjusted by the Governance Framework process.
