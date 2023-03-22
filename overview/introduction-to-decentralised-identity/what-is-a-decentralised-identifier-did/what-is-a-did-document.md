# What is a DID Document?

## Context

The information which the **DID** resolves to is called the **DID Document**. This is the equivalent to the Vehicle Details that the vehicle registration plate number resolves to.

However, rather than having a database, held by a centralised company, such as the DVLA, the DID Document is stored generally on a blockchain, or other [Verifiable Data Registry](what-is-a-verifiable-data-registry.md). This enables third parties to trust the contents of it, without reliance on any company or server being online.

## What does a DID Document contain?

An example of a **DID Document** is below, which explains various information about the **DID subject**. We will walk through this sequentially as it is quite technical and complex.

```jsonc
{
  "@context": [
    "https://www.w3.org/ns/did/v1",
    "https://w3id.org/security/suites/ed25519-2020/v1"
  ],
  "id": "did:cheqd:mainnet:N22KY2Dyvmuu2PyyqSFKue",
  "verificationMethod": [
    {
      "id": "did:cheqd:mainnet:N22KY2Dyvmuu2PyyqSFKue#authKey1",
      "type": "Ed25519VerificationKey2020", // external (property value)
      "controller": "did:cheqd:mainnet:N22N22KY2Dyvmuu2PyyqSFKue",
      "publicKeyMultibase": "zAKJP3f7BD6W4iWEQ9jwndVTCBq8ua2Utt8EEjJ6Vxsf"
    },
    {
      "id": "did:cheqd:mainnet:N22KY2Dyvmuu2PyyqSFKue#capabilityInvocationKey",
      "type": "Ed25519VerificationKey2020", // external (property value)
      "controller": "did:cheqd:mainnet:N22N22KY2Dyvmuu2PyyqSFKue",
      "publicKeyMultibase": "z4BWwfeqdp1obQptLLMvPNgBw48p7og1ie6Hf9p5nTpNN"
    }
  ],
  "authentication": ["did:cheqd:mainnet:N22KY2Dyvmuu2PyyqSFKue#authKey1"],
  "capabilityInvocation": ["did:cheqd:mainnet:N22KY2Dyvmuu2PyyqSFKue#capabilityInvocationKey"],
}
```

### `id`

The `id` field at the top identifies the **DID subject**. Using the above analogy, the **DID subject** would be James Bond's Aston Martin DB5, because it is the entity that is identified by the identifier. In more general identity use cases, the **DID subject** _could_ be an entity such as a car, but is usually a company or organisation.

{% hint style="info" %}
Note: This is the same identifier as what is inputted into the **resolver** to return this **DID Document**.
{% endhint %}

### `verificationMethod`

The `verificationMethod`, in this example, describes a cryptographic key or list of keys and the controller(s) of the key(s). Each Verification Key itself lists:

* an `ID` for the specific key;
* the `controller`, i.e., the identifier of the person or company with control over that key; and,
* the `type` of cryptographic key.
* the verification key material such as `publicKeyMultibase`

Going back to the above analogy, holding a private key for a certain cryptographic key pair is like holding the **V5C logbook**, as it enables **DID Controllers** to update/change/amend information about the ownership of the DID.

Without access to the verification keys, the ownership or control of the DID would not be able to change.

In reality, James Bond himself could have a specific verification key, his colleague "Q" could have a second specific key and the Secret Intelligence Service MI6, could have a third specific key. Each party would be known as a DID Controller, and would be able to update/change/amend the DID Document accordingly.

### `authentication`

The `authentication` property is very important. This property enables **only** the **DID subject** to prove and authenticate who they are.

In our specific example, James Bond may be the only party that holds a Verification key, listed under the authentication property. **This is almost analogous to holding the keys to the car**. Using this property, if challenged about being the owner of the car, James Bond would have all the tools necessary to prove and authenticate the car, under this verification key for authentication.

### `service`

The `service` field provides further information about where to contact the DID subject. In our analogy, this could point to a specific email address for help@MI6.com. This property is quite flexible, but importantly, it should not disclose any personally identifiable information.

There are also other useful fields which may be included in a DID Document, such as `assertionMethod`, `keyAgreement`, `capacityInvocation` and `capacityDelegation`. These are outside of the scope of this introductory information, and should be the topics of further reading.

The key difference between the use of something like the license plate registry and the use of DIDs, is the former relies on a centralised database, whereas, the latter relies wholly on decentralised trust and cryptographic key management.

This makes DIDs far more extensible, scalable and workable beyond jurisdictional borders.
