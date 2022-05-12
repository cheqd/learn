# Introducing the CHEQ-ERC20 wrapped token

To create an ERC20 representation of the Cosmos based CHEQ token we’ve used a bridge. A blockchain bridge or ‘cross-chain bridge’ enables users to transfer assets or any form of data seamlessly from one entirely separate protocol or ecosystem to another (i.e. Solana to Ethereum, or in our case Cosmos to Ethereum and vice versa).

Bridges generally use some kind of mint-and-burn function to keep token supply constant across all platforms. When the token leaves one blockchain, it is burned or locked, and an equivalent token is minted on the opposite blockchain. Conversely, the equivalent token is burned or locked when the token moves back to its original network. This equivalent token is known as a ‘wrapped token’ because the original asset is put in a wrapper, a kind of digital vault that allows the wrapped version to be created on another blockchain.

The [CHEQ-ERC20 wrapped token can be found here](https://etherscan.io/address/0x70EDF1c215D0ce69E7F16FD4E6276ba0d99d4de7) (you can also add it to your MetaMask wallet through this link — _go to profile summary > click ‘more’ > ‘add token to MetaMask’_ )

![](<../../.gitbook/assets/image (26).png>)
