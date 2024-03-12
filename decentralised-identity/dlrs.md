---
description: Learn about digital resources written on cheqd
---

# What are DID-Linked Resources?

cheqd has built a **Resources Module** to extend the functionality of our decentralised identity network, providing capabilities not found on other self-sovereign identity networks.

A **DID-Linked** **Resource** is a blob of information stored on-ledger, discoverable through the same [Decentralized Identifier (DIDs) syntax](broken-reference) that is widely used within the SSI industry.

## What issues do DID-Linked Resources solve?

### Centralisation

Many SSI resources such as schemas currently reference web URLs such as [Schema.org](https://schema.org/). Other areas where this can be issues are:

* DID methods, such as [`did:web`](https://w3c-ccg.github.io/did-method-web/) and [`did:github`](http://docs.github-did.com/), where trust is based on Web 2.0 infrastructure
* Revocation lists maintained on servers, such as [Status List 2021](https://w3c-ccg.github.io/vc-status-list-2021/)

If, for example, any of the infrastructure listed above was to experience downtime due to technical faults, a dDoS attack or a failure of a cloud hosting provider, this could hugely disrupt the proper use of Verifiable Credentials in a production environment.

### Link Rot and Longevity

Such web URLs as described above are also single-points of failure due to [link rot](https://en.wikipedia.org/wiki/Link\_rot).

Credential schemas, once defined, should be able to be used and referenced for many years, without being changed. For this reason, keeping an up-to-date version of the links themselves is crucial. Moreover, if the schema locations are moved and the links are broken, the Credentials issued become far less trustworthy.

### Semantic Linkage

The way schemas are currently referenced from web URLs (e.g., schema.org/Person) is not immutable. Schemas may be changed and previous schema definitions may be purged from the database. This means if you had a Verifiable Credential issued in 2015 which referred to a particular schema in 2022, that schema definition may have significantly changed.

On the other hand, solutions that _do_ currently store schemas on ledger (e.g., Hyperledger Indy) don't have semantic linkage between old and new versions. In this instance, current ledgers allow new versions to be made but don't offer an easy way for client apps to discover linkages as they evolve over time.

## Use cases for DID-Linked Resources

The use of Resources is potentially very broad; they can provide many different roles, such as:

* A **schema**, such as Camenisch-Lysyanskaya ("CL") schema ‘CL’, JSON-LD schema, JSON schema etc.
* A **visual representation**, such as [Overlays Capture Architecture (OCA)](https://oca.colossi.network/), [Apple Wallet PassKit](https://developer.apple.com/documentation/passkit), [Google Wallet Passes](https://developers.google.com/wallet), etc
* A **document**, such as [a Governance Framework](broken-reference)
* An **branding elements**, such as a company logo, brandmark, etc which can be pulled directly by block explorers and other Web3 applications
* A **revocation registry** for revoking already-issued credentials.

Through extending the use of DIDs to identify other on-ledger resources, trust can begin to be chained.

### New use cases enabled by DID-linked Resources

| Audience              | Quick wins                                                                                                                                                                                                                                              | Longer term strategic objectives                                                                                                                                                                                                                                   |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **SSI Community**     | Create a much more **secure, resilient and decentralised format for storing schemas** than [schema.org](https://schema.org/)                                                                                                                            | Lay the technical foundations for **supporting** [**AnonCreds**](https://hyperledger-indy.readthedocs.io/projects/sdk/en/latest/docs/design/002-anoncreds/README.html) **compatible Verifiable Credentials on cheqd**, in addition to support for JSON and JSON-LD |
| **Web 3.0 community** | Extend the [Trust over IP Resource Parameter Specification](https://wiki.trustoverip.org/display/HOME/ToIP+Governance+Metamodel+Specification), enabling **DIDs to act as #Web3 hyperlinks for any on (or off) ledger URL, Resource, file, or content** | Enable Web3 Companies to use on-ledger Resources to **fetch company information (such as logos, token info, relevant token APIs)** to **populate Block Explorers and Exchanges**, rather than through Keybase or manual processes.                                 |

> You can think of it as a hyperlink for #Web3. But unlike a hyperlink, it is possible to specify the type of resource to be retrieved, and reject anything unexpected.
