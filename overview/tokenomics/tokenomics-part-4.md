# 4 Tokenomics: Part 4

## Identity network transaction pricing

_Tokenomics are typically documented and distributed via a dedicated whitepaper. However, since our tokenomics will be a constant iteration, we have been using blogs to explain these in an easier-to-digest format, with a summary available in the Governance Framework._

- _[Part 1 of cheqd’s tokenomics](https://blog.cheqd.io/cheqds-tokenomics-for-ssi-explained-f13f680cf00d) covered the context/background, utility through parameters such as initial supply and inflation, and governance tokenomics. It’s now time to complete the picture with distribution/allocations._

- _[Part 2 of cheqd’s tokenomics](https://blog.cheqd.io/cheqds-tokenomics-for-ssi-explained-part-2-c4ecfc32b813) covered the initial distribution of the token._

- _[Part 3 of cheqd’s tokenomics](https://cheqd.io/blog/cheqds-tokenomics-for-ssi-explained-part-3-payment-models) covered the planned architecture of the payment rails._

## TL;DR

Tokenomics part four outlines measures to improve the tokenomic sustainability of the cheqd network. This is achieved through an increase in the network’s identity transaction pricing for DIDs and Resources (from gas price to more concrete dollar values) and the introduction of deflationary mechanisms in the form of burns. Essentially, the fee used for identity transactions will be split: a portion will go back to Validators and Delegators as block rewards, a portion will be burnt (destroyed) to reduce supply, and a portion will be designated to the Community Pool. **The exact weighing of this split is for _you_, the community, to decide**.  

We are proposing to introduce two new mechanisms to the cheqd tokenomics:

### 1. Identity transaction pricing

- Identity transactions such as DIDs, credential schema, etc. writes will have a cost greater than gas which will increase rewards from the network as identity utility increases.
- This is similar to [Osmosis’ external incentive charges funding the community pool](https://github.com/osmosis-labs/osmosis/blob/main/x/pool-incentives/keeper/distr.go)and [rewards on Kujira stakers scaling with network utility use](https://docs.kujira.app/tokenomics/kuji-token/kuji-sustainability).
- This has been achieved using genesis parameters which will be updated periodically to maintain stable pricing for users until we migrate to using [oracles such as those provided by Umee](https://umee.cc/blog/announcing-orion-umee-is-building-a-decentralized-price-oracle-native-to-cosmos/).

### 2. Burns

- A proportion of the identity transaction charges will be burnt to establish equilibrium with the inflation on the network and target total supply returning to a total initial supply of one billion $CHEQ.
- A Commonwealth discussion has been created to open up discussion on the proportion of any charges which should be burnt.

### 3. Community pool parameter increase

- The $CHEQ community pool recently funded work by [Animo](https://animo.id/) to reward them for their work on their [Anoncreds demo on cheqd](https://www.youtube.com/watch?v=QILE98VMwZw&t=1s) and continue their work on [Anoncreds ledger independence](https://commonwealth.im/cheqd/discussion/7159-community-pool-spend-proposal-for-animo-solutions). We believe the percentage of network rewards should be increased to encourage work such as this.
- A Commonwealth discussion has been created to open up discussion on the proportion of network rewards which should be allocated to the community pool.

Identity transaction pricing and burns will augment the work we are doing on payments for self-sovereign identity/decentralised identity.

![identity pricing tokenomics](<../../.gitbook/assets/tokenomics-part-4-img-1.png>)

## Introduction

It’s almost a year to the day since we successfully launched the [cheqd mainnet](https://cheqd.io/blog/cheqd-launches-mainnet-network). In that time, we have learnt a huge amount, especially regarding tokenomics which we are now proposing to update.

Currently (prior to the proposed update), writing a DID to cheqd mainnet only costs gas, which is approximately 0.004 $CHEQ. This is extremely cheap when compared to networks such as Sovrin, where writing a DID costs $10, especially taking into account  the value we are bringing as a network, protocol and team.

Alongside this, $CHEQ is currently inflationary (where staking rewards come from), with only slashing, tombstoning or no-with-veto slashing providing any deflationary pressure.

**We are proposing to update and improve both of these**.

The best and easiest place to start is **pricing**.

## Network Pricing

Per the introduction, current identity transactions on cheqd are too cheap for the value they create. We intend to move to the following pricing structure, which is still extremely competitive whilst matching the value created much closer.

![identity tx pricing](<../../.gitbook/assets/tokenomics-part-4-img-2.png>)

_Note: Currently, schemas, credential definitions and revocation registry transactions are all priced the same since on-ledger they are all categorised  as “[resources](https://cheqd.io/blog/our-approach-to-resources-on-ledger)”. Over time, these will likely become opinionated and differentiated according to the value they create and the burden they place on the ledger._

The keen-eyed of you will notice that the pricing above is in dollars, and obviously, cheqd mainnet runs in $CHEQ. In short, we are setting parameters to convert from US dollars to $CHEQ using baselined $CHEQ pricing at network update. _For more details, please see the Implementation: Dollar to $CHEQ section below._

At current price levels ($0.03-$0.04), writing a DID will equate to 66.6 - 50 $CHEQ, which leads us to where these tokens will be distributed upon writes. This mechanism is similar to the mechanism [Osmosis uses to fund the community pool through network charges for anyone creating external pool incentives](https://github.com/osmosis-labs/osmosis/blob/main/x/pool-incentives/keeper/distr.go). It also brings us towards the mechanisms built by the [Kujira team for rewards to increase as the use of the network utility increases](https://docs.kujira.app/tokenomics/kuji-token/kuji-sustainability).

## Distribution, rewards & burn

The tokens being charged by the network can either be distributed across stakers or burnt (or both according to a defined split):

- Burn: Provides a deflationary mechanism to counter inflation on the network.
- Distribution: Augments inflation-based rewards so APY will rise as network use does.

### Distribution and rewards

If we assume that 50% of the tokens spent will be burnt, we have 50% being distributed to delegators, validators and the community pool.

Using the example in the diagram below, any block with a DID written within it is worth approximately ~four times a standard block where the block reward is ~12 $CHEQ. **This means rewards on the network will begin to rise with adoption**.

![current vs future rewards](<../../.gitbook/assets/tokenomics-part-4-img-3.png>)

It is also worth noting that whilst resource transactions (which include revocation writes and updates) are substantially cheaper than DID transactions, we are expecting them to be orders of magnitude more frequent. Sovrin mainnet has a ratio of approximately fifty revocation registry updates to every DID, which we believe will be on the extreme low-side as adoption scales.

Repeating a table we included in Tokenomics part 3 below, issuing credentials and hence interacting with revocation registries is significantly higher than DID transactions.

![tokenomics part 3 image](<../../.gitbook/assets/tokenomics-part-4-img-4.png>)

Tokens which have been charged by the network for identity transactions but not burnt will be distributed according to stake on the network so, distributed across delegators, validators and the community pool.

## Burn

As mentioned above, the network is currently inflationary only aside from slashing, tombstoning and no-with-veto having deflationary effects. Implementing a burn mechanism will bring the system into equilibrium.

![inflation and deflation](<../../.gitbook/assets/tokenomics-part-4-img-5.png>)

The volume of tokens burnt will increase in the same way as distributions will, with the aim of **bringing total supply back to one billion**.

![inflation and equilibrium](<../../.gitbook/assets/tokenomics-part-4-img-6.png>)

## All together

Bringing distribution, rewards and burn all together means the system will be dynamic and as the network use increases, both rewards and burns will increase, increasing APY whilst also bringing the total supply back towards one billion. As rewards increase, the $CHEQ community can prioritise APY or accelerating burns to drive total supply down to the original initial supply.

## Implementation

### Dollar to $CHEQ

In the first version of identity transaction pricing, we are achieving dollar pricing through periodically adjusting on-ledger parameters , using baselined $CHEQ prices, via governance votes. Over time, we intend to migrate to oracles such as those provided by [Umee](https://umee.cc/blog/announcing-orion-umee-is-building-a-decentralized-price-oracle-native-to-cosmos/) to maintain constant dollar pricing for our partners. Until we have implemented oracles, we propose to update the parameters quarterly to keep pricing stable. _Please see the Community and Governance section for more details._

![inflation and deflation](<../../.gitbook/assets/tokenomics-part-4-img-7.png>)

_[Genesis parameters](https://github.com/cheqd/cheqd-node/blob/ante-impl/networks/mainnet/genesis.json)_

### Burn percentage

As can be seen in the image above showing the genesis parameters which define the costs in $CHEQ, there is also a “burn_factor” variable which sets the percentage of the tokens charged for identity transactions which will be directly burnt. This can be adjusted through on-ledger governance votes according to the cheqd community preferences.

## Community and Governance

Implementation of these mechanisms (pricing, distribution, and burn) will require on-ledger votes both to implement but also to periodically maintain these, especially before we implement pricing oracles to programmatically maintain stable dollar pricing for our partners.

We would welcome the community's feedback on the _burn_factor,_ specifically on whether they would prioritise burning more or increasing rewards on the network.

Our view is that a high `burn_factor` in the immediate term would be preferable since this minimises the amount of burning required in the future to return to the total initial supply (one billion) whilst maintaining rewards where they currently are but would welcome the community’s views and opinions. We’re looking forward to engaging here. To that end, we have begun a Commonwealth discussion here.

## Frequency

Until we build support for oracles so that dollar pricing can be maintained programmatically, we will need to periodically update the genesis parameters covered in `Implementation: Dollar to $CHEQ`. _Currently, we believe this should be quarterly so that we do not need to hold governance votes every month which would put too much burden on both delegators and validators. However we would welcome feedback from the community.

## Community pool

This also feels an opportune time to open a discussion on the percentage of network rewards allocated to the community pool, specifically to increase the percentage allocated and hence empower and reward more work like [Animo](https://animo.id/)’s work on [demonstrating AnonCreds on the cheqd network](https://www.youtube.com/watch?v=QILE98VMwZw&t=1s) [via the community pool](https://commonwealth.im/cheqd/discussion/7159-community-pool-spend-proposal-for-animo-solutions). We have therefore opened up another Commonwealth discussion here.

## Next steps

We believe all of these changes will improve the sustainability and success of the cheqd ecosystem but, as always, want to hear the community’s feedback. As per the introduction, we are constantly learning here at cheqd and want to make sure we build on those learnings to achieve maximum success.

We want to open these changes up for discussion, specifically, the _burn_factor_ which will define the proportion of network charges which will be burnt and how much will be distributed to delegators, validators and the community pool. We also want to open up a discussion to increase the proportion of rewards allocated to the community pool to further incentivise work like that being delivered by Animo.

As we launch these implementations onto the network, we are able to focus on building support for cheqd into more SDKs to allow our partners to access the network utility more easily as well as focusing on our USP: payments, which is what we’re most excited about.

Please head to the following Commonwealth discussions for each debate or our [Telegram](https://t.me/cheqd) and [Discord](https://cheqd.link/discord) for more informal conversations:

- Burn percentage discussion
- [Community pool percentage discussion](https://commonwealth.im/cheqd/discussion/7159-community-pool-spend-proposal-for-animo-solutions)

We look forward to hearing from you.

Thanks, \
The cheqd team

## Disclaimers

_The values and statements made above are indicative only and should not be construed as an offer or guarantee._

## About this Document

_This document sets out the aims and intentions of the core cheqd team for the payment models, based on the current state of its ecosystem in November 2022. These evaluations are subject to change for technical, legal, business and other reasons. We will make our best efforts to keep the entire cheqd community informed and updated with changes to this distribution strategy_.

**_cheqd Governance_**

_Integral to cheqd is the concept of decentralised Governance, explained in full detail in our [Governance Framework](http://docs.cheqd.io/governance). This is important because the content of the cheqd tokenomics and this distribution document are subject to change if the governance mechanism opts to make [Major Network Changes](https://docs.cheqd.io/governance/contributing/major-network-changes). Such governance decisions are outside of the direct control of the core team. As such, changes may affect (among other things) the token ($CHEQ) price , the specifics of token distribution and the network parameters._

**_Legal Uncertainty as a Risk Factor_**

_There is underlying legal uncertainty in the nature of blockchain projects due to how quickly the industry is evolving and how legal regulations and frameworks need to adapt to keep up. For this reason, it is reasonably foreseeable that there will be further guidance and regulations on digital assets, cryptocurrency, Decentralised Autonomous Organisations (DAOs) and digital identity going forward. cheqd’s core team has made the best efforts to build cheqd in a [generative](https://dash.harvard.edu/bitstream/handle/1/9385626/zittrain_generativeinternet.pdf?sequence=1) way to develop alongside updates in the law. This notwithstanding, there is still a surface area of risk, where future or existing legal regulations could have a negative effect on the proper functioning of the project and on the value of $CHEQ._

_No regulatory authority in Singapore, including the Monetary Authority of Singapore, has reviewed or approved the $CHEQ tokens or any of cheqd’s documentation, including blog posts, website material, webinars, events, videos or other graphics (the “Information Material”). The acquisition of tokens is subject to a potential acquirer’s compliance with the laws and regulations in the jurisdiction they reside in._

**_Acquisition as a Risk Factor_**

_The acquisition of $CHEQ tokens carries with it significant risks. Prospective acquirers should carefully assess and take into account such risks prior to acquiring $CHEQ tokens. cheqd's initial core team and all of their collective past, present or future officers, directors, managers, employees, agents, advisors or consultants, or any other person (collectively, “cheqd”), expressly disclaims any and all responsibility for any direct or consequential loss or damage of any kind whatsoever arising directly or indirectly from: (a) reliance on any information contained in the Information Material; (b) any error, omission or inaccuracy in any such information; and (c) any action resulting therefrom. cheqd does not guarantee the accuracy of the statements made or conclusions reached in the Information Material and does not make, and expressly disclaims, all representations and warranties (whether express or implied by statute or otherwise). Past is not a reliable indicator of the future. The Information Material does not constitute advice, nor any recommendations or an offer, by cheqd or any of its affiliates and all of their collective past, present or future officers, directors, managers, employees, agents, advisors or consultants, or any other person, to any recipient of the Information Material. cheqd strongly encourages you to seek appropriate advice in respect of $CHEQ tokens and taking into account your personal circumstances, including but not limited to financial, legal, tax advice_.

**_The Use Case as a Risk Factor_**

_The $CHEQ token is worthless in itself and gains potential value within the cheqd ecosystem only through the protocol, its use and through continual use of [Verifiable Credentials](https://www.w3.org/TR/vc-data-model/) utilising cheqd payment functionality. Therefore, the success of the coin’s utility depends on multiple factors, including but not limited to, the health of the overall cryptocurrency market, the resilience of the cheqd protocol, and the success of Self-Sovereign Identity vendors in implementing real-world use cases_.

_$CHEQ must also be held within a wallet that can, ideally, consume Verifiable Credentials as well as $CHEQ tokens. This relies on the work of third parties to facilitate a functioning and healthy ecosystem._

_In order to offer access to acquiring the $CHEQ tokens, it is essential that cheqd engages centralised or decentralised exchanges to list and facilitate the trade of tokens. The dependence on exchanges to recognise and list $CHEQ is a large risk vector. The likelihood of (specifically centralised) exchanges listing cheqd is directly correlatable to the size and activity of the cheqd community and the functional capabilities of the protocol and its governance model._

**_Security of Technology as a Risk Factor_**

_Blockchains are not infallible to risk; nor is the storage of private keys for the purposes of owning $CHEQ and Verifiable Credentials. The wallet and the tokens it contains can only be accessed using the corresponding private keys. The owner of the tokens is solely responsible for keeping their private keys safe and protecting the safekeeping and protection of the private keys for the wallet against unauthorised access. While there will be safeguards put in place to help prevent such loss, the issue cannot be ruled out._

_51% Proof of Stake attacks as well as rogue, malicious Governance proposals could be damaging to the proper functioning of cheqd as a protocol and as a community. It can also not be ruled out that blockchains generally, the cheqd Network, or other decentralised protocols become the target of attacks by hackers - alongside the further development of new technologies such as quantum computing._
