---
description: cheqd's unique superpower for monetising credential issuance
---

# Verifier pays Issuer

Verifier pays Issuer is a Credential Payment flow that enables "issuers" to charge a premium fee to validate the legitimacy of the credential's status. This is **an incredibly powerful tool** for companies that want to issue Verifiable Credentials, but also want to put a sensible commercial model in place.

## Example of Verifier pays Issuer flow

![Jane Doe](<../../.gitbook/assets/Jane Doe image.webp>) **This is Jane Doe**

Jane Doe has recently completed her university degree at Bright University. She wants to receive a digital, verifiable and certifiable copy of her diploma to apply for a prospective job.

#### DID and DID-Linked Resource Creation

In order for this to happen, first Bright University needs to register their [**Decentralised Identifier (DID)**](../../decentralised-identity/dids/what-is-a-did.md) to a [Verifiable Data Registry](../../decentralised-identity/dids/what-is-a-vdr.md) or ledger. In this case, Bright University anchor their DID to cheqd, using the cheqd DID method.

Bright University, however, want to make sure that they also receive a payment when Jane uses her digital diploma for other purposes. As such, Bright University create a "Premium" credential with a $20.00 fee to fully validate.

<figure><img src="../../.gitbook/assets/Registering Premium Credential.png" alt=""><figcaption><p>Bright University register DID and chargeable DID-Linked Resource</p></figcaption></figure>

Bright University anchor their DID to cheqd, and create a "chargeable" $20.00 DID-Linked Resource to allow relying parties to Pay to Trust the credential's status and also the governance framework under which the university operates.

The specific Public DID is registered as `did:cheqd:mainnet:923u592u5ghgu3r8` and the DID-Linked Resouce is available via `did:cheqd:mainnet:923u592u5ghgu3r8/resources/5c2529b0-656d-4244-8e55-906d124df523`.

Bright University specify that **$20.00** must be paid to Bright University to access the status information regarding the credential they will issue to Jane.

#### Credential Issuance

Jane has completed her degree and she has successfully achieved a First Class Honours. Now, she wants to receive a digital copy of the diploma to be able to hold it in her digital identity wallet.

On the physical certificate there is a QR code which Jane scans. This creates a peer-to-peer encrypted channel between the University and Jane's phone, which has her digital identity wallet.

Bright University issues a [Verifiable Credential](../../decentralised-identity/credentials/what-is-a-vc.md) to Jane through this peer-to-peer encrypted channel. The [Verifiable Credential](../../decentralised-identity/credentials/what-is-a-vc.md) has the following claims:

* This is Jane Doe's diploma
* Jane Doe graduated from Bright University in the year 2022
* Jane Doe achieved a First Class Honours in her MSC degree in Computer Science.
* **$20.00 ($CHEQ or stablecoin)** must be paid to Bright University to validate and verify the status pof the credential.&#x20;

The Verifiable Credential has a proof, meaning it is digitally signed by the Public DID of Bright University, as well as potentially cryptographic material referring to a specific public key, which may be used for a particular purpose (such as asserting claims).

<figure><img src="../../.gitbook/assets/Premium Credential Issued to Jane.png" alt=""><figcaption><p>Premium Credential issued to Jane's wallet</p></figcaption></figure>

Jane receives the [Verifiable Credential](../../decentralised-identity/credentials/what-is-a-vc.md) to her digital identity wallet and  this entire data flow takes place off-ledger. This is important because it keeps all of Jane's personal information private, and only with her.

Jane now holds a Verifiable Credential of her University degree in her digital identity wallet and is able to use this to prove claims about herself.

#### Verifiable Presentation flow

Jane applies online for a new job as a Lead Engineer at a leading technology company.

The technology company asks for Jane to upload her education records. Rather than filling out the form manually; Jane scans another QR code to create a peer-to-peer encrypted channel with the technology company. Jane sends a [Verifiable Presentation](../../decentralised-identity/credentials/what-is-a-vp.md) containing her claims and the attached proof to those claims, in a few clicks or taps.

The technology company is only able to verify the validity of the claims that Jane presents by resolving the DID embedded in the Presentation **and by paying $20.00 to Bright University** to verify the Credential's legitimacy, status and validity.

<figure><img src="../../.gitbook/assets/Paying for Premium Credential.png" alt=""><figcaption></figcaption></figure>

Through paying to verify the credential, the technology company is able to see the DID Document and also the Credential status information stored as a DID-Linked Resource. Automatically, the technology company is able to ascertain that the proof inside Jane's Verifiable Presentation was issued by the real Bright University and is for the correct purpose.

The technology company is now satisfied and progresses Jane to the next phase of the application.

On the other side, Bright University make $20.00, which they can later withdraw into fiat currency. This creates a trusted relationship between the "Verifier" (technology company) and the "Issuer" (Bright University) whereby a fair payment can be made for cryptographically verifiable data that makes the technology companies recruitment process much easier.
