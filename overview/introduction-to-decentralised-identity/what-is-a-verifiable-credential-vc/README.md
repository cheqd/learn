# What is a Verifiable Credential ("VC")?

### How we generally think of the word "Credential"

A "[Credential](https://www.collinsdictionary.com/dictionary/english/credentials)", in an everyday sense, is an attestation, evidence or proof of qualification, competence or authority issued to an entity, either individual or person, by a third party with relevant authority or assumed competence to do so. This may be evidence of authority, status, rights, entitlement to privileges, or the like, usually in a written form.

Historically, we have relied on public issuing bodies to verify our identities — i.e. passports, driving licence, birth certificates, etc. These credentials go on throughout our lives, being issued to us or requested by us at times we need them. We provide them to others regularly, without ever wondering what happens to them, where they now sit, and how long they’ll be retained.

Essentially credentials are a means to verify identity.

### What is a Verifiable Credential?

A **Verifiable Credential ("VC")** is a tamper-evident data file with a set of claims about a person, organisation, or thing that can be **cryptographically verified**. These verifiable credentials can be used to build [Verifiable Presentations](https://www.w3.org/TR/vc-use-cases/#dfn-verifiable-presentations), which can also be cryptographically verified.

Okay, stop there, let's simplify what this technical language means.

#### A familiar concept: Email

Let's imagine something we're all familiar with.&#x20;

Here's a classic email with some attachments.&#x20;

This is how most people are familiar with sending information about themselves digitally.&#x20;

![](<../../../.gitbook/assets/image (12).png>)

I am sure everyone reading this has had to attach a photocopy of their passport to an email, in order to prove that they are who they claim to be. Or alternatively, has attached their CV to an email to prove their work and education records, either as a word document or PDF.

The problem with this system, is that it is not currently possible to check the validity of an attachment sent via email. Word Documents, PDFs, JPEGs etc have no security features that allows a third party to check if they were legitimate or not.&#x20;

Let's take the example of the CV. You receive it as an attachment, you read it, and to check the validity, you need to contact the references which are generally at the bottom of the CV to check whether this person really did all the things they claim to have done.&#x20;

This is time consuming, and frequently, owing to the lack of trust in these data formats.

#### How does Verifiable Credentials change this?

A Verifiable Credential is a digital file that stores data. However, importantly it is designed to hold two core types of data:

* **Claims**

A claim is an attestation about something. It could say that "I went to Oxford University".&#x20;

* **Proofs**

A proof is cryptographic evidence to support that claim. In decentralised identity, this evidence is generally attested to by an [issuer](../). This proof is often represented by both the [Decentralised Identifier ("DID")](../what-is-a-decentralised-identifier-did/) of the issuer, as well as a piece of cryptographic material, that relates to a specific public key of the issuer, for a specific purpose such as an assertionMethod.

### Why is this useful and important?

Verifiable Credentials change the way that data can be trusted when presented. This is because when you receive a Verifiable Credential, you are able to check, without contacting another party, whether that data was issued by a specific issuer.&#x20;

Unlike attachments in an email, which are data files that need to be independently verified, to trust their contents; Verifiable Credentials enable that verification innately, through the use of [Decentralised Identifiers](../what-is-a-decentralised-identifier-did/). This is a powerful component for building trust in a decentralised Web 3.0.

Therefore, you can reach the definition:

A **Verifiable Credential ("VC")** is a tamper-evident data file with a set of claims about a person, organisation, or thing that can be **cryptographically verified**. These verifiable credentials can be used to build [Verifiable Presentations](https://www.w3.org/TR/vc-use-cases/#dfn-verifiable-presentations), which can also be cryptographically verified.

For more information, please see the Verifiable Credential Data Model Specification below:

{% embed url="https://www.w3.org/TR/vc-data-model" %}
