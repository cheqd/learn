# What is a Verifiable Data Registry?

A Verifiable Data Registry ("VDR"), in the context of decentralised identity, is a place where Decentralised Identifiers (DIDs) can be anchored to.

## Types of Verifiable Data Registries

### Blockchain

Commonly, VDRs are blockchains, like cheqd. This is because they are great places to store data immutably.

### Web domain

However, a VDR could also be a web domain, like [http://cheqd.io](https://www.cheqd.io/). We could store a public DID on this website, because only the admins of cheqd have the ability to edit this.

This is largely secure, but is not as resilient as a blockchain, because, for example, the hosting provider for the website could take it down.

### Sidetree

New innovations in decentralised identity have tried to create a more flexible storage layer for DIDs. Sidetree is a technology which stores DIDs and DID Documents in a temporary Layer 2 storage layer called Sidetree. This data is stored in IPFS, batched and anchored to blockchains in rollups. This minimises the amount of transactions necessary to be made to the Layer 1 blockchain.

Hypothetically, by storing DIDs in a temporary storage Layer 2, with backups in IPFS, the DID could also be updated from being stored on one VDR to another VDR. This is currently the exploratory work of did methods such as did:orb.

### KERI

KERI, meaning Key Event Rotation Infrastructure, is another emerging innovation in decentralised identity. Rather than anchoring a DID to a specific location or block within a chain, KERI relies on nodes witnessing Key Event Logs (KELs). A KEL may hold an authoritative source of truth about what the latest keys related to a DID are, and who holds them.

In simple terms, KERI's logs are not immutable like a blockchain, but rely on the law of large numbers, and trust that KERI witnesses will act in a trustworthy fashion - providing the most up to date KELs with the correct Key events.

## Further reading

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><mark style="color:blue;"><strong>DID Core Spec</strong></mark></td><td>Dive into the W3C DID Core Recommendation to fully grasp the power of DIDs.</td><td><a href="https://www.w3.org/TR/did-core/">https://www.w3.org/TR/did-core/</a></td></tr><tr><td><mark style="color:blue;"><strong>DID Resolution Spec</strong></mark></td><td>Learn about how DIDs can be resolved or dereferenced from the W3C DID Resolution Spec.</td><td><a href="https://w3c-ccg.github.io/did-resolution/">https://w3c-ccg.github.io/did-resolution/</a></td></tr><tr><td><mark style="color:blue;"><strong>DID Spec Registries</strong></mark></td><td>Explore the different DID methods registered within the DID Spec Registries.</td><td><a href="https://www.w3.org/TR/did-spec-registries/">https://www.w3.org/TR/did-spec-registries/</a></td></tr><tr><td><mark style="color:blue;"><strong>cheqd DID Method</strong></mark></td><td>Learn specifically about cheqd's DID Method and how it works on the cheqd Network.</td><td><a href="https://docs.cheqd.io/identity/architecture/adr-list/adr-001-cheqd-did-method">https://docs.cheqd.io/identity/architecture/adr-list/adr-001-cheqd-did-method</a></td></tr></tbody></table>
