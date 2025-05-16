# SD-JWT

{% hint style="info" %}
_Much of the work in this page is influenced, iterated or directly replicated from_ our [partner Walt.id's docs on SD-JWT](https://docs.walt.id/v/ssikit/concepts/selective-disclosure/intro).
{% endhint %}

## What is Selective Disclosure?

Selective disclosure empowers an individual to decide which specific pieces of information, contained within a Verifiable Credential, will be disclosed to a verifier. This stands in contrast to the conventional practice of revealing all the data present in a Verifiable Credential.

For instance, Alice could selectively share only her age to confirm eligibility for purchasing products on an e-commerce platform, without divulging other personal details found in her Verifiable ID document used for verification. This approach enhances privacy and provides individuals with greater control over their personal data.

## The Significance of Selective Disclosure

Selective disclosure is a crucial element of Self-Sovereign Identity (SSI) because it allows individuals to share only the essential personal information required for a transaction or interaction. This minimizes the risk of identity theft and various forms of fraud.

## SD-JWTs: A Mechanism for Selective Disclosure

A Selective Disclosure JSON Web Token (SD-JWT) is a subtype of JSON Web Token wherein the claims within the body are hashed, rendering them unreadable without proper disclosure. The original values of the claims can be unveiled by providing the necessary disclosures.

### How it Operates

When presenting a conventional credential via JWT, the claims are plainly visible to the verifier. In contrast, with an SD-JWT credential, claims are encrypted in a hashed format, ensuring their unreadability. The holder can then choose which claims to reveal to the verifier by providing plain text key-value pairs (referred to as disclosures) alongside the SD-JWT. The verifier can hash these disclosures and compare them to the values in the SD-JWT, thereby verifying the inclusion of the claim in the SD-JWT. Additionally, SD-JWTs allow for the inclusion of decoy hashes in the credential, serving as dummy values to obfuscate the actual number of claims in the credential.
