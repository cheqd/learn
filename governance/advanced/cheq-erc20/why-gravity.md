# Why did we decide to use the Gravity Bridge?

After exploring the options available, we felt the Gravity Bridge was the most suitable and could help us achieve our results in the fastest whilst safest way possible.

One of the key things that attracted us to the Gravity Bridge is the way in which the Ethereum contract has been highly optimised, utilising batches to dramatically reduce the cost of transfers between Cosmos and Ethereum.

We also felt the decentralised running of the network was most in line with our vision at cheqd. As it’s a non-custodial solution, a stake can be slashed for any misbehaviour in accurately bridging assets or secure messages.

In addition, as a native bridge, the value of tokens on the destination chain and the absence of double spending are guaranteed by the same consensus as on the consensus chain. This means all the validators are coming to a consensus that the individual owns the tokens that are registered on both sides (the same amount of tokens has been launched on both sides of the bridge — i.e. on both chains).

Finally, we also saw the bridge as a powerful way to ensure having a token on another chain doesn’t fracture liquidity like wrapped tokens through a custodian would do.

## Potential issues identified

One of the issues that was raised with the Gravity Bridge is down to the upgrade process. Given the team’s warranted focus on simplicity, it has led to the Solidity contract (gravity.sol) being non-upgradeable, whereas the other bridges can be upgraded by multi-sig wallets. This means the validators and their delegators are completely in control of the Gravity Bridge, and no one else can change the code.

Although we recognise this concern, we feel that the validators on the Gravity Bridge chain have a legitimate governance process and have acted in line with our principles to date. We also plan to set up a validator node on the Gravity chain and engage more in the governance and running of the bridge itself.
