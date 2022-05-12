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

![cheqd trust triangle basic](<../../.gitbook/assets/cheqd trust triangle no explanations.jpg>)

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

### Why is the Trust Triangle important?

The Trust Triangle enables a [verifier](./#d449) to be able to trust data it receives from a [holder](./#1776) without having to have any direct interaction or relationship with the [issuer](./#bccf).

It also empowers the [holder](./#1776) to maintain total control of their data and where it is used, through decentralised trust, utilising [Decentralised Identifiers ("DIDs")](what-is-a-decentralised-identifier-did/) and [Verifiable Credentials ("VCs")](what-is-a-verifiable-credential-vc/).

To find out and understand exactly how this works, you need to firstly familiarise yourself with [DIDs](what-is-a-decentralised-identifier-did/) and [VCs](what-is-a-verifiable-credential-vc/), and [how they work together](broken-reference).&#x20;

![cheqd trust triangle explanatory](<../../.gitbook/assets/cheqd trust triangle.jpg>)

