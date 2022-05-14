# What is the Gravity Bridge?

![](<../../.gitbook/assets/image (24).png>)

The Gravity Bridge is a trustless, neutral bridge between the Ethereum and Cosmos ecosystems built by the [Althea](https://www.althea.net/) team. Built using the Cosmos SDK, it uses the validator set to sign transactions instead of a multi-sig or permissioned set of actors.

The neutrality here implies that the entire focus of the Gravity community is on providing the most effective and secure bridge possible instead of on a DeFi application on the local chain. This neutrality aggregates volume from a number of blockchains and sources, increasing efficiency and lowering costs. All control over the bridge is handled entirely by the Gravity Bridge validator set.

The Gravity Bridge has two defined components:

1\) A [Solidity contract on Ethereum](https://github.com/Gravity-Bridge/Gravity-Bridge/blob/main/solidity/contracts/contract-explanation.md)

2\) A [Cosmos SDK module](https://github.com/Gravity-Bridge/Gravity-Bridge/tree/main/module/x/gravity/spec) on the Gravity Bridge blockchain

The way Gravity Bridge works is similar to how all cross-chain bridges work, i.e. locking up a native token on one side of the bridge and minting a representation of that token on the other. The user then uses this representation before it is returned to the bridge and redeemed for the native asset on the other chain.

The most critical component for bridges to and from Ethereum is the Solidity contract. It holds the native assets being sent across the bridge.

[Gravity.sol](https://github.com/Gravity-Bridge/Gravity-Bridge/blob/main/solidity/contracts/Gravity.sol), the Solidity contract developed by the [Althea](https://www.althea.net/) team, holds funds for Gravity Bridge on Ethereum. In contrast to the prevailing trend in other bridge designs, at a mere 580 lines of code, Gravity.sol is compact and easy to review.

It has been audited by three independent teams ([Informal](https://informal.systems/), [Least Authority](https://leastauthority.com/), and [Code4rena](https://code4rena.com/)), and it is not upgradable, meaning that auditors found it cannot be tampered with by any malicious actor and does not contain any trusted parties of any kind.

To interact with Gravity Bridge, head to[ SpaceStation.zone](https://spacestation.zone/) (supported by [Cosmostation](https://www.cosmostation.io/)), where you can connect your [MetaMask](https://metamask.io/) and[ Keplr wallet](https://www.keplr.app/).

![](https://miro.medium.com/max/1400/0\*V8LU91Wi951BqoFS)

If you want to learn more, hear from the[ Gravity team themselves here](https://blog.cosmos.network/gravity-is-an-essential-force-of-the-cosmos-aligning-all-planets-in-orbits-in-the-composable-b1ca17de18cc) or head over to the[ Gravity Docs](https://github.com/Gravity-Bridge/Gravity-Bridge). .

\
