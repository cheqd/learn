# 1⃣ Tokenomics: Part 1

## Summary

Over the past months, the team has been analysing the desired behaviour of the network stakeholders as well as the available functionality provided by Cosmos to identify the levers to achieve the right incentives. Whilst there are many parameters, we will focus the analysis on the key parameters which affect the incentives on the network.

Our Network parameters are listed here:

{% embed url="https://docs.cheqd.io/governance/tokenomics/parameters/network-parameters" %}

It should be noted that these parameters can, at any point, be modified via the governance procedures.

### General

The main function of the general parameters is to set supply, inflation and targets for bonded targets.

#### **Initial supply and goal_bonded**

* The **Initial supply** of tokens, i.e. to be minted at the Token Generation Event, is set to **1b (1 x 10^9)** which we deemed adequate for the initial size of the network. Please see inflation for how this is likely to increase.
* The goal for the percentage of bonded tokens (**goal_bonded**) is currently set to **60%**. This was benchmarked against a number of projects and we feel this strikes the balance between securing the network and paying for identity transactions.

The inflationary parameters were much more impactful to network incentives based on our analysis. Implementing zero inflation would eliminate block rewards and therefore incentivise the push for maximum adoption of the network utility since rewards would entirely depend on transaction fees. Rewards would scale with transaction volume but consequently rewards would be low at low transaction volumes and also unpredictable. As a benchmark, Sovrin’s self-sovereign identity [network has variable volumes month-by-month for various transaction types](https://sovrin.org/ssi-metrics-dashboards/), and thus rewards for node operators / validators that only relied on transaction fees would make it difficult for node operators to predict fees collected from the network.

#### Inflation: inflation_min and inflation_max

Inflation (**inflation_min** & **inflation_max**) somewhat solves this problem by introducing block rewards which are independent of transaction and hence gas fees. Assuming there is little to no downward pressure on price at low inflation, block rewards provide a largely predictable reward over sufficient time, ensuring support and securing of the network is rewarded. However, inflation dilutes the incentive for network use, i.e. scaling rewards according to transaction volume.

Consequently, inflation can be seen as a double-edged sword. It rewards maintaining the network even at low volumes, but dilutes the incentive to drive maximum adoption.

By modelling rewards against transaction volume and using a number of reference points ([CIVIC](https://coinmarketcap.com/currencies/civic/), [EVEREST](https://coinmarketcap.com/currencies/everest/), [LUNA](https://coinmarketcap.com/currencies/terra-luna/) & [UST](https://coinmarketcap.com/currencies/terrausd/) all-time high transaction volumes) we established that **inflation_max** should be <4% to achieve any meaningful incentives through transaction volumes. We similarly used all-time low transaction volumes to identify **inflation_min** as 1% to maintain sufficient rewards at low volumes.

### Distribution

#### **Communitytax, baseproposerreward & bonusproposerreward**

As with the _general_ parameters above, we analysed existing projects (e.g. [Fetch.ai](https://coinmarketcap.com/currencies/fetch/), [Terra](https://coinmarketcap.com/currencies/terra-luna/) & [Akash](https://coinmarketcap.com/currencies/akash-network/)) and modelled various scenarios to understand the impact of the parameters on the network.

Across these projects, the values for **communitytax**, **baseproposerreward** and **bonusproposerreward** appear to be set to their defaults. Our modelling suggests the reason for this is that aside from **communitytax,** rewards across the network are largely dictated by stake regardless of the **baseproposerreward** and **bonusproposerreward** values**.**

As a result, we similarly didn’t see a reason to change the default values.

However, as the network progresses and becomes increasingly decentralised, it may become beneficial to reduce these values. For example, looking at Osmosis, another token on Cosmos, the community[recently lowered these values to 0](https://www.mintscan.io/osmosis/proposals/31). The logic behind this decision was to reduce the Node Operators with the largest stake on the network from getting richer, and to incentivise a wider breadth of stake distribution.

### Governance

Tokenomics is a subset of overall network governance. It is a way of incentivising or decentivising different actions on the network through economic forces, which in turn, regulates user behaviour.

For tokenomics to have an effect on the progression of the network, there must also be ways that a User can interact with its governance. In cheqd’s Network, we use a system of collective voting, based on [liquid democracy](https://en.wikipedia.org/wiki/Liquid_democracy). This voting architecture has a symbiotic relationship with the tokenomics to regulate the network.

Let’s explain this simply. I want to make a materially significant change on the Network, let’s say a Parameter Change, adjusting the default parameters explained in this post. The steps necessary to reach an accepted Proposal are as follows:

1. I need to draft a Proposal;
2. I need to make a deposit alongside my Proposal to publish it on-ledger;
3. I need that deposit to reach a parameter known as MinDeposit;
4. This needs to happen before the max-deposit-period expires.

The Proposal will then reach what is known as voting stage, where:

1. Enough people need to vote on the proposal for it to be valid (quorum);
2. A minimum threshold need to vote ‘Yes’ on the Proposal;
3. Below a certain number of votes must veto the Proposal;
4. The ‘Yes’ threshold must be met before the voting period expires,

If all the stars align above, then the Proposal will be accepted and the changes will be rolled out across the Node Operators in a process known as **signal** and **switch**. The specifics of this process will be articulated and explained in greater depth and detail in our Governance Framework.

So where do tokenomics come in? Well, someone needs to set the default parameters for:

1. MinDeposit
2. MinDeposit period time limit
3. Quorum
4. Threshold
5. Veto
6. Voting period time limit

The value of these parameters has a knock-on effect on other aspects of the network. For this reason, choosing these parameters is therefore not a simple game of ‘[numberwang](https://www.youtube.com/watch?v=0obMRztklqU)’. We selected each value for a reason.

#### MinDeposit

We did a detailed analysis of each token on Cosmos, taking the MinDeposit as a factor of the amount of tokens staked on the respective Network.

| Name       | Total in circulation | Total bonded | Min deposit          | Min deposit as a factor of total bonded | Inflation | Project duration |
| ---------- | -------------------- | ------------ | -------------------- | --------------------------------------- | --------- | ---------------- |
| Osmosis    | 164,109,266          | 41,585,288   | 500 (initially 2500) | 83,171 (from 16,634 roughly)            | Dynamic   | 3 months         |
| KAVA       | 91,443,180           | 51,696,320   | 1000                 | 51,696                                  | 20%       | 22 months        |
| Starname   | 134,963,184          | 61,556,708   | 1000                 | 61,557                                  | 0%        | 6 months         |
| Sifchain   | 172,008,780          | 28,522,261   | 10                   | 2,852,226                               | 0%        | 7 months         |
| IRIS       | 1,096,877,712        | 429,756,688  | 1000                 | 429,757                                 | 4%        | 7 months         |
| Cosmos Hub | 278,726,583          | 189,421,850  | 64 (initially 512)   | 2,959,716 (369,965)                     | 7%        | 30 months        |
| cheqd      |                      |              | Range 361 - 36,070   | 1-3%                                    |           |                  |

We found that the range was very large and calculated that our minimum deposit could sit proportionately as low as 360 (Cosmos’ lowest value) or as high as 36,000 (Osmosis’ highest value), given our total tokens at 1 billion and a bonded goal of 60%.

Another common theme we noticed was that projects tended to begin with a higher MinDeposit and then lower this value through a Proposal as the Network matured (Cosmos and Osmosis). This is something that we thought would be valuable to replicate as well, in line with the [Principle of Entropy](https://blog.cheqd.io/entropy-in-decentralised-governance-part-one-b6dc2dab0085).

We settled on a value of **8,000 as MinDeposit.** This was not only a sensible middleground given our calculations, but gives us the option to Propose to scale down the value as the network progresses and becomes more decentralised.

**Max_deposit_period** and **voting period**

For the **MinDeposit time period (max_deposit_period)** and **voting period (voting_period)** we settled on the value of **1 week**. This is because this figure seems unproblematic and functional for healthy Cosmos communities. 2 weeks, which was the parameter on our testnet, was too long to wait in order to push through new updates.

#### Quorum and threshold

For the quorum and threshold, there is a very strong relationship between the two values. Once again we have decided to stick with Cosmos’ default parameters because they work well in healthy governance communities.

These are:

* **33.34% quorum**; and
* **50% threshold**.

One model of Governance that we think would be a valuable addition further along our roadmap, however, is Polkadot’s system of [Adaptive Quorum Biasing](https://wiki.polkadot.network/docs/learn-governance). In this model, the lower the quorum tends, the higher the threshold tends, and vice versa. If this feature was implemented into Cosmos SDK’s governance module, Proposals to move to this would certainly be welcomed.

#### Veto

Veto is possibly the most extreme example of where governance and tokenomics overlap, as a veto vote ‘burns’ the tokens invested in the Proposal which sit in an escrow called a ModuleAccount.

We believe that the **33.34%** default setting for veto is both high and low enough. Veto votes should be used sparingly, only when Users think that a Proposal is contradicting a core cheqd Principle (to be released in our Governance Framework).

## Changes

### A starting point

As we’ve mentioned briefly above, these values are very much the start and we fully expect these to be updated by the community through the processes set out in the governance framework. Our hope though is that these values set a strong foundation for a successful, self-governing ecosystem.

### Improvements

As we covered in the context section, these values are the Minimum Viable Tokenomics to establish the network. As the base values are updated by the community, the team will begin delivering more complex tokenomic functionality including a variety of commercial models such as transactional payments, subscriptions or volume-based discounting.

Our primary focus will be on enabling these commercial models along with stable settlement, achieved through support for stablecoins and potentially central bank digital currencies.

## Our tokenomics webinar

If you rather watch a video about our tokenomics, _cheq_ out our webinar below.

> [cheqd Tokenomics Webinar](https://www.youtube.com/watch?v=KYs5QjRbDBs)

You can also [download the cheqd Tokenomics slides here](../../.gitbook/assets/cheqd-Tokenomics_deck-Webinar_Sharing.pdf).
