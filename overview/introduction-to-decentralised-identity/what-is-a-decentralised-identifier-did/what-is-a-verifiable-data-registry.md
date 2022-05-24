# What is a Verifiable Data Registry?

## What is a Verifiable Data Registry?

A Verifiable Data Registry ("VDR"), in the context of decentralised identity, is a place where Decentralised Identifiers (DIDs) can be anchored to.&#x20;

### Blockchain

Commonly, VDRs are blockchains, like cheqd. This is because they are great places to store data immutably.&#x20;

### Web domain

However, a VDR could also be a web domain, like [http://cheqd.io](https://www.cheqd.io/). We could store a public DID on this website, because only the admins of cheqd have the ability to edit this.&#x20;

This is largely secure, but is not as resilient as a blockchain, because, for example, the hosting provider for the website could take it down&#x20;

### Sidetree

New innovations in decentralised identity have tried to create a more flexible storage layer for DIDs. Sidetree is a technology which stores DIDs and DID Documents in a temporary Layer 2 storage layer called Sidetree. This data is stored in IPFS, batched and anchored to blockchains in rollups. This minimisese the amount of transactions necessary to be made to the Layer 1 blockchain.&#x20;

Hypothetically, by storing DIDs in a temporary storage Layer 2, with backups in IPFS, the DID could also be updated from being stored on one VDR to another VDR. This is currently the exploratory work of did methods such as did:orb.&#x20;

### KERI

KERI, meaning Key Event Rotation Infrastructure, is another emerging innovation in decentralised identity. Rather than anchoring a DID to a specific location or block within a chain, KERI relies on nodes witnessing Key Event Logs (KELs). A KEL may hold an authoritative source of truth about what the latest keys related to a DID are, and who holds them.

In simple terms, KERI's logs are not immutable like a blockchain, but rely on the law of large numbers, and trust that KERI witnesses will act in a trustworthy fashion - providing the most up to date KELs with the correct Key events.&#x20;



