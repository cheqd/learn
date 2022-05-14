# What other bridging options did we explore?

Whilst beginning our investigation into bridges, we came across varying bridging techniques available, mainly in the Cosmos ecosystem, although these remain much the same across protocols.

Although many of the wrapped tokens available require a custodian to manage this minting and burning (aka. centralised or trusted bridges), the more innovative bridges that now exist (aka. noncustodial, decentralised or trustless bridges) do this through automated methods using contracts on either side of the bridge, as we’ll come on to.

As mentioned, our initial priority with a bridge is for ease of accessing stablecoins for settling payments for trusted data that will be facilitated on the cheqd network. With this in mind, our bridging requirements at this stage are less complex than they might be in the future (for example, we aren’t necessarily in need of a fully-fledged solution that allows the bridging of smart contracts across protocols like EVMos will in time enable).

If you’re a project looking at bridging, we’d recommend you [check out this great explainer video](https://www.youtube.com/watch?v=I5ijyRF2FD0\&t=842s) put together on bridges by Ken Timsit from Cronos (Cronos also plan to use the Gravity Bridge, launching in Q2)

### Evmos <a href="#7e1b" id="7e1b"></a>

Evmos is a Secondary Bridge leveraging a third party — the Connext Peer-to-Peer Bridge. Connext acts as an intermediary to provide liquidity on both sides by locking up purchased tokens and adding these

Essentially when using EVmos you don’t have an Ethereum contract (like Gravity does with Gravity.sol), but it uses the existing contracts of the tokens that exist on the other side. Therefore, given other third parties provide the liquidity, we felt this would be a greater overhead for our team compared to Gravity and more centralised.

That said, we are excited by EVMos and the great team working on this project, who look to have an exciting year ahead with four different DEXs, lending protocol, two perpetual platforms and at least three NFT collections for the NFT marketplaces.

### Connext <a href="#66b3" id="66b3"></a>

[Connext](https://www.connext.network/) is a peer-to-peer bridge / cross-chain swap. It uses a similar method to the Hashed Timelock Contract, a transactional agreement used on the Bitcoin network to produce conditional payments wherein the receiver or the beneficiary must acknowledge the receipt of payment before a predetermined time or a preset deadline.

Basically, when you want to transfer tokens, there is one router which will be assigned and takes the responsibility of fronting the liquidity. In exchange, they will wait to get paid after the transaction is completed on Ethereum with the same amount of tokens.

Connext’s network utilises [nxtp](https://github.com/connext/nxtp), a lightweight protocol for generalised cross-chain transfers. Nxtp is made up of a simple contract that uses a locking pattern (mentioned above) to prepare and fulfil transactions, a network of off-chain routers that participate in pricing auctions and pass calldata between chains and a user-side SDK that finds routes and prompts on-chain transactions.

### Thorchain <a href="#cc5d" id="cc5d"></a>

[Thorchain](https://www.thorchain.com/) is a blockchain protocol built on[ Cosmos](https://decrypt.co/crypto-news/cosmos) that aims to “make all of crypto liquid”. It seeks to do this by enabling the trading of non-native crypto assets, such as trading Bitcoin for Ethereum, but in a completely decentralised way. In essence, it does much of what Coinbase and Binance do — but without a third party ever taking control of the funds.

The Thorchain protocol also powers a decentralised exchange ([DEX](https://decrypt.co/resources/what-is-decentralized-exchange-dex)) by the same name. Like[ Uniswap](https://decrypt.co/resources/what-is-uniswap) or[ SushiSwap](https://decrypt.co/resources/what-is-sushiswap-how-to-buy-sushi-2021), the Thorchain DEX allows anyone to trade or lend their crypto assets by providing liquidity to an asset pool and, in exchange, earn a return (or “yield”) on those assets. With 1.5 million transactions to date and >80 validators, it is a leading solution, however, for our use case, it just didn’t offer the simplicity and ease of enabling a $CHEQ token on Ethereum.

Since we completed our investigation, Osmosis has also spent some time exploring how they plan to bridge their DEX’s requirements. Axelar, Wormhole and Nomad were also discussed here — all options we came across but did less investigating at the time. You can also find the RFPs for these Bridge proposals links: [Axelar](https://docs.google.com/document/d/11b4haQp7tOG2GAuGiIRAcoVjWjnUgcd3N3xfoOL7Csg/edit), [Gravity Bridge](https://docs.google.com/document/d/1PP0qQfSPq-dYSLFlnMwuLimtxmUNh3xeQpKUMMHHiwU/edit), [Nomad](https://docs.google.com/document/d/1ztF6vNmxrYiSMZZsTPbdTS7lAVfOoezvGyjqo2zOo98/edit), [Wormhole](https://spacemandev.notion.site/Wormhole-Proposal-for-Osmosis-db6ce7f0781549c1bbf0b07015380bdb)

A brilliant panel with some of the bridge providers can be found here, and the [write-up also available here. ](https://medium.com/osmosis-community-updates/osmosis-town-hall-choosing-a-bridge-service-provider-63e0835d78e)The Osmosis Discord has had perhaps the most lively debate since [Robo McGobo](https://twitter.com/RoboMcGobo?s=20\&t=ImuN9LXPmjxANj\_SGuqF6A) created a [special channel for bridge discussions](https://discord.com/channels/798583171548840026/943934970995572777), and representatives from the various teams have been quite responsive there.
