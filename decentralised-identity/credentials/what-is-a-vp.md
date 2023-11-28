# What is a Verifiable Presentation?

A Verifiable Presentation is a combination of [Verifiable Credentials](what-is-a-vc.md), bundled together into a format to present to a third party.

Like VCs, Verifiable Presentations contain proofs (i.e. they can be signed with cryptographic keys). In this regard, a major difference between VCs and Verifiable Presentations is that Verifiable Presentations **are signed with cryptographic keys of the holder** to prove, for example, that the actor who is sharing the Verifiable Presentation is also the credential subject of the underlying VCs.

With some credential formats like AnonCreds, holders can freely choose which information (from underlying VCs) they include in a Verifiable Presentation and thus, share with a relying party. It is even possible for holders to prove to a relying party that they possess a certain attribute or fulfil certain conditions without disclosing details (e.g. the proof that one is older than 18 without revealing the real age) via so-called 'Zero Knowledge Proofs'.

There are multiple standards used for Verifiable Presentations, that will be listed below:

### Aries Present Proof

{% embed url="https://github.com/hyperledger/aries-rfcs/blob/main/features/0454-present-proof-v2/README.md" %}

### Presentation Exchange 2.0.0

{% embed url="https://identity.foundation/presentation-exchange" %}
