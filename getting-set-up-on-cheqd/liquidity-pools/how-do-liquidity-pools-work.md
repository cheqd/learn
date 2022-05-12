---
description: A summary of the how liquidity pools work
---

# 🌊 How do liquidity pools work?

## Overview

In order for liquidity pools to function in the way that leads to the outcomes laid out in the previous page, i.e. greater decentralisation of projects and increasing liquidity, there are a number of key aspects worth understanding:&#x20;

* token weighting;&#x20;
* pricing;&#x20;
* market-making functions;&#x20;
* LP tokens.

(much of the following is taken from the official documentation from [Osmosis Labs](https://osmosis.gitbook.io/o/basic-concepts/amm)).

### Token Weight

Liquidity pools are simply clusters of tokens with pre-determined weights. A token's weight is how much its value accounts for the total value within the pool.

For example, Uniswap pools involve two tokens with 50-50 weights. The total value of Asset A must remain equal to the total value of Asset B. Other token weights are possible, such as 90-10.

### Pricing

With fixed predetermined token weights, it is possible for AMMs to achieve deterministic pricing, i.e. outcomes are precisely determined through known relationships among states and events, without any room for random variation. As a result, tokens in LPs maintain their value relative to one another, even as the number of tokens within the pool changes. Prices adjust so that the relative value between tokens remains equal.

For example, in a pool with 50-50 weights between Asset A and Asset B, a large buy of Asset A results in fewer Asset A tokens in the pool. There are now more Asset B tokens in the pool than before. The price of Asset A increases so that the remaining Asset A tokens remain equal in value to the total number of Asset B tokens in the pool.

Consequently, the cost of each trade is based on how much it disrupts the ratio of assets within the pool. Traders prefer deep liquid pools because each order tends to involve only a small percentage of assets within the pool. In small pools, a single order can cause dramatic price swings; it is much more difficult to purchase say 1,000 ATOMs from a liquidity pool with 2,000 ATOMs than a pool with 2,000,000 ATOMs.

### Market-Making Functions

AMMs leverage a formula that decides how assets will be priced in the pool. Many AMMs utilise the Constant Product Market Maker model (x \* y = k). This design requires that the total amount of liquidity (k) within the pool remains constant. Liquidity equals the total value of Asset A (x) multiplied by the value of Asset B (y).

Other market-making functions also exist, you can find out more about these here.

### Liquidity Pool Tokens (LP tokens)

When a user deposits assets into a Liquidity Pool, they receive LP tokens. These represent their share of the total pool.

For example, if Pool #1 is the OSMO<>ATOM pool, users can deposit OSMO and ATOM tokens into the pool and receive back Pool1 share tokens. These tokens do not correspond to an exact quantity of tokens, but rather the proportional ownership of the pool. When users remove their liquidity from the pool, they get back the percentage of liquidity that their LP tokens represent.

![](https://lh6.googleusercontent.com/PLQo6H2gnqgeO4cXmbKFl84D5WBomMOo-G\_SqLbrNHqVO5KzEZYK1pPVM9U3MMVsc4mb\_xPbXx3eqZ-TZzVH6dkdpw2GAHEAC\_uVXTUjqaugivJWIzd-I8JIutC-uT5Pi1arSTNP)

![Source: Osmosis Labs docs](https://lh6.googleusercontent.com/CfODbSpiJuhFR9VY-AQrNb4kAiaP2\_D72tVaCtAnInoQX8jzs1A\_PpFs\_Z9h3JZsiIuC\_-fNOb\_UVR8mD3e\_CdB3tjb8Scp0rzIPSTlYmDCcLFY4e0em4sx\_Sd4Hm0GSFT0e917U)

The collection of the mechanisms above is used to ensure liquidity pools are able to maintain a stable price and ultimately work as a traditional market maker would do.

However, in order to achieve their ultimate goals, encouraging token holders to provide liquidity to pools is required.

The aspects in place to do so is what is known as ‘liquidity mining’ or ‘yield farming’. Contributing to a pool makes an individual a liquidity provider (LPs).

## Liquidity mining

Liquidity providers earn through fees and special pool rewards. LP rewards come from swaps that occur in the pool and are distributed among the LPs in proportion to their shares of the pool’s total liquidity. So where do the rewards themselves come from?

Liquidity rewards are derived from the parameters laid out in the genesis of the AMM, in the case of the Cosmos Ecosystem this is Osmosis. For Osmosis, each day, 45% of released tokens go towards liquidity mining incentives.

When a liquidity provider bonds their tokens they become eligible for the OSMO rewards. On top of this, the Osmosis community decides on the allocation of rewards to a specific bonded liquidity gauge through a governance vote.

### Bonded Liquidity Gauges

Bonded Liquidity Gauges are mechanisms for distributing liquidity incentives to LP tokens that have been bonded for a minimum amount of time. For instance, a Pool 1 LP share, 1-week gauge would distribute rewards to users who have bonded Pool1 LP tokens for one week or longer. The amount that each user receives is in proportion to the number of their bonded tokens.

The rewards earned from liquidity mining are not subject to unbonding. Rewards are liquid and transferable immediately. Only the principal bonded shares are subject to the unbonding period.

However, as with any opportunity for gain, there is of course some degree of risk; i.e. an individual could be better off holding the tokens rather than supplying them.

This outcome is called impermanent loss and essentially describes the difference in net worth between HODLing and LPing (more here). Liquidity mining mentioned above helps to offset impermanent loss for LPs. There are also other initiatives within the Osmosis ecosystem and beyond exploring other mechanisms to reduce **impermanent** loss.
