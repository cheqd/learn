# 🟢 Introduction to Decentralised Identity

### What is Decentralised Identity? <a href="#what-is-self-sovereign-identity-ssi" id="what-is-self-sovereign-identity-ssi"></a>

**Decentralised Identity**, otherwise known as **Self-Sovereign Identity ("SSI")** is an emerging technology that enables individuals and/or organizations to maintain direct control of data relating to them, with the ability to explicitly consent to where it is shared, used and processed.

Decentralised identity aims to create a **trusted data economy**, where it is possible to verify, check and trust exactly who you are interacting with, in both physical and digital domains.&#x20;

Through this data model, it is possible to:

* Reduce fraud, scams and phishing attempts online through digital identity proofs;
* Increase efficiency of signing up for new services, accessing events or proving attributes about yourself;
* Eliminate the need for hundreds of passwords;
* Empower individual privacy and GDPR data subject rights by design;
* Increase accountability in digital environments, minimising trolls and hate speech.

### The Trust Triangle

Any distinct model of decentralised identity revolves around three specific actors: the [issuer](./#bccf), the [holder](./#1776) and the [verifier](./#d449). Together, these three actors constitute what is known as the **Trust Triangle**.

![Self-Sovereign Identity Trust Triangle: Basic](<../../.gitbook/assets/cheqd trust triangle no explanations.jpg>)

Let’s discuss these three in turn:

#### Who are Issuers? <a href="#bccf" id="bccf"></a>

An issuer is an entity that is able to issue trusted data in the form of [Verifiable Credentials](what-is-a-verifiable-credential-vc/). Issuers can come in many shapes and sizes. In most typical SSI use cases, issuers tend to be large organisations such as governments, financial services, health services, insurers or education faculties.&#x20;

However, an issuer could also quite easily be a friend, family member or even a local café. In fact, in the DeFi world, issuers could be those who you have interacted with online who attest to something about you.&#x20;

All an issuer needs to be able to do is to attest a fact or attribute about someone else. The level of trust in that attestation is up for the [verifier](./#d449) to decide.

#### Who are Holders? <a href="#1776" id="1776"></a>

A holder can be an individual, an organisation, a product or an object, which has a certain set of attributes that have been attested to by an [issuer](./#bccf).&#x20;

The holder is able to hold and manage these attributes, in the form of [Verifiable Credentials](what-is-a-verifiable-credential-vc/), and directly consent to when, and with whom, these credentials are shared. This empowers the holder to be able to enact their [GDPR Data Subject Rights](https://gdpr-info.eu/chapter-3/) by design and by default.&#x20;

A holder is able to bundle their [Verifiable Credentials](what-is-a-verifiable-credential-vc/) into a [Verifiable Presentation](what-is-a-verifiable-credential-vc/what-is-a-verifiable-presentation.md) in order to prove attributes about itself to a third party. There are different types of Verifiable Credentials that a holder may hold; they may have different Signature schemes, some may afford greater privacy preserving benefits such as Zero Knowledge Proofs or Selective Disclosure.

#### Who are Verifiers? <a href="#d449" id="d449"></a>

A verifier is any entity that can verify the authenticity and validity of a [Verifiable Credential](what-is-a-verifiable-credential-vc/), via a presented [Verifiable Presentation](what-is-a-verifiable-credential-vc/what-is-a-verifiable-presentation.md).&#x20;

The verifier is able to check that the data presented was issued by the correct, legitimate [issuer](./#bccf) and that the [Verifiable Credential](what-is-a-verifiable-credential-vc/) has not been tampered with. In most instances, the verifier may be able to check that the [Verifiable Credential](what-is-a-verifiable-credential-vc/) has not expired or been revoked.&#x20;

### Understanding the basics of the trust triangle

The following image shows the basic flow of how SSI works, without getting into the technical details.&#x20;

![Self-sovereign identity Trust Triangle: Simplified explanation](<../../.gitbook/assets/Trust Triangle - simplified explanation.jpg>)

Let's run through this flow in turn.

1. **Trust anchor:** Issuer registers a digital signature to the blockchain

One of the most important components of SSI, is understanding what goes on the blockchain and what does not.

In this first step, the issuer anchors a public signature to the blockchain in the form of a [Decentralised Identifier (DID)](what-is-a-decentralised-identifier-did/#what-is-a-did) and [DID Document](what-is-a-decentralised-identifier-did/#what-is-a-did-document). In non-technical terms, the information contained in this signature is a statement from the issuer saying:

> "Hey, this is my digital signature and signing keys that I am openly publishing to the world. This will help verifiers trust that if they see a digital signature within data they are presented, they can check whether it is mine or not."

The issuer may also publish what is known as a Schema, which is a list of the types of attributes there will be listed in a Credential that it issues. Schemas are useful for Credential interoperability.&#x20;

2\. **Peer-to-peer connection**: Issuer sends signed, verifiable data to the holder&#x20;

Once the issuer has publicised their signature and signing keys, they are able to issue a [Verifiable Credential](what-is-a-verifiable-credential-vc/) to a holder.&#x20;

To do this, the issuer needs to establish a secure off-chain, peer-to-peer connection channel with the holder. This is to preserve privacy and ensure that no personally identifiable information goes onto the blockchain.

A holder may use a digital identity wallet app to scan a QR code from the issuer to create a pairwise relationship.&#x20;

Through this secure channel, an issuer will send a Verifiable Credential. This Credential is a packet of data which is tamper-proof and verifiable. Within the Credential will be the public signing keys and signature of the issuer, present in the DID Document (written to the ledger in step 1).

The Credential may also reference a particular schema, which the structure of its contents mirrors.&#x20;

3\. **Self-Sovereignty:** Holder can hold, control and consent to where their data is used

Once the Credential is sent to the holder, they now have a signed, verifiable and trustworthy instance of their data in a digital wallet that they control.

Digital identity wallet apps will have user interface which helps arrange different data by type and by substance, making it easy for the holder to have a holistic view of all their Credentials.&#x20;

The holder is now empowered with full control and management capabilities over their personal data. The holder can consent and directly choose when their data is shared.

4\. **Peer-to-peer connection:** User can share trustworthy data with a third party verifier&#x20;

Once again, if the User wants to share their data with a third party, another peer-to-peer channel needs to be created with a verifier. In a similar process, the holder might use their wallet app to scan a QR code from the verifier to create a secure, off-chain communications channel.

Once this channel is established, the verifier may request a selection of data from the holder.&#x20;

The holder will be able to choose whether it wants to accept the request and will be able to explicitly consent to what data is shared with the verifier.

The holder shares the data with the verifier in the form of a [Verifiable Presentation](what-is-a-verifiable-credential-vc/what-is-a-verifiable-presentation.md). Importantly, the data shared with the verifier is still visible in the holder's digital identity wallet app. This data can be revoked at any time by the holder, in a few clicks, in accordance with their data subject rights.

5\. **Decentralised trust:** Verifier trust the issuer's signature in the data received

As mentioned in Step 2, the Credential that the holder presented to the verifier contained the signing keys and digital signature of the issuer.&#x20;

Using the blockchain, and a process called DID Resolution, the verifier is able to check whether the signature and signing keys in the data received, correlates with what is published in the issuer's DID Document.&#x20;

The verifier may also check the schema referenced in the credential, to check that all the correct attributes are present, and to also make it easier for the verifier to receive similar Credentials in the future, given there may be a common format.

The process of DID Resolution builds a chain of decentralised trust between the issuer, holder and verifier - without the issuer and verifier needing to have a direct relationship with each other.

### Why is the Trust Triangle important?

The Trust Triangle enables a [verifier](./#d449) to be able to trust data it receives from a [holder](./#1776) without having to have any direct interaction or relationship with the [issuer](./#bccf).

It also empowers the [holder](./#1776) to maintain total control of their data and where it is used, through decentralised trust, utilising [Decentralised Identifiers ("DIDs")](what-is-a-decentralised-identifier-did/) and [Verifiable Credentials ("VCs")](what-is-a-verifiable-credential-vc/).

This is incredibly powerful for establishing trusted interactions at a large scale.

