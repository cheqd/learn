# What is a Validator / Node Operator?

In blockchain ecosystems, the **Node Operator** runs what is called a **node**. A node can be thought of as a power pylon in the physical world, which helps to distribute electricity around a wide network of users.



![Source: National Grid](https://miro.medium.com/max/1280/0\*lYscyX3yFJQx\_Iyq)

Without these pylons, electricity would be largely centralised in one location; the pylons help to distribute power to entire wide-scale populations. And if one pylon fails, the grid is set up to circumvent this pylon and re-route the electricity to a different route.

Similarly, in blockchain infrastructure, each node runs an instance of the consensus protocol and helps to create a broad, robust network, with no single point of failure. A node failing will have little impact on the Network as a whole; however, if multiple nodes fail, or disagree with information entered into the transaction, then the block may not be signed, and there are fail-safe measures to notify the rest of the Node Operators of this.

The terms Validator and Node Operator are somewhat synonymous. Validator is the term used more commonly in the[ Cosmos documentation](https://docs.cosmos.network/) when referring to a Node Operator that is validating transactions on a blockchain. The only point worth mentioning is you can have a Node Operator that is NOT a Validator. These are known as Observer nodes, which play a more passive role on the network, as they don’t stake on the network or validate transactions, but can observe them.

## What does a Validator actually do? <a href="#a192" id="a192"></a>

The [Cosmos Hub](https://hub.cosmos.network/main/gaia-tutorials/what-is-gaia.html) is based on [Tendermint](https://tendermint.com/docs/introduction/what-is-tendermint.html), which relies on a set of validators to secure the network. By ‘secure the network’, this refers to the way in which validators “_participate in consensus by broadcasting votes which contain_ [_cryptographic signatures signed by their private key_](https://hub.cosmos.network/main/validators/validator-faq.html)”. In English pls…

A cryptographic signature is a mathematical scheme for verifying the authenticity of digital messages or documents. A private key is like a password — a string of letters and numbers — that allows you to access and manage your crypto funds (your mnemonic is a version of this). So, the above is saying validators can broadcast that they agree with transactions in a block, using their password to sign their agreement in a mathematical way which ensures security and privacy.

\
