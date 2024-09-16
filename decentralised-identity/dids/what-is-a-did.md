# What is a DID?

{% hint style="success" %}
DIDs can identify any entity in a digital way.
{% endhint %}

It is easy to think of DIDs as identifying something **in the same way as how a registration plate identifies a car**, and a car's owner.

To take an example, this is **James Bond's Aston Martin DB5**.

![Image showing James Bond's Aston Martin DB5](<../../.gitbook/assets/James Bond DB5.png>)

James Bond's Aston Martin has a unique identifier, the license plate, identifying the owner of the car and also the features of the car:

{% hint style="info" %}
BMT 216A
{% endhint %}

Similarly, a DID is a unique identifier, identifying the DID subject (a person, company or thing), and providing information about the DID subject.

{% hint style="info" %}
did:cheqd:mainnet:fbe76ff9-54c0-49ce-ab18-aab8137dc8a6
{% endhint %}

Both identifiers can be checked against a registry in order to provide verifiable information about the thing that the identifier is identifying.

The process for withdrawing the information from the DID is very similar to the license plate number: through resolving a DID to get information about the DID Document.

### Why are these identifiers important?

License plates and DIDs both give third parties a high degree of trust and confidence in who/what they are interacting with.

To understand what we mean here, let's look at the following scenario:

#### If James Bond rocked up to a swanky spy party in his DB5, and someone were to accuse him of stealing the car, how could he prove ownership and control of it?

Well, James Bond can likely prove control and ownership of that car in **3 main ways**:

1. The license plate is on James Bond's car. And the unique registration plate `BMT 216A` will be linked to Mr Bond's identity through a registry, such as the DVLA. Anyone is able to check that the registration details of the car match it's visual features, and authorised persons are able to check whether James Bond's identity matches the license plate.
2. James Bond holds the physical keys to unlock and use the car.
3. James Bond holds a physical document called a VC5 Logbook, which is a required document, alongside other identity documents, to update any of the information in the DVLA database.

This model uses the DVLA registry and the physical access/documentation about the car, as two separate layers of trust and assurance, meaning:

1. The `BMT 216A`license plate could be removed and placed on another car
2. James Bond's keys could be stolen
3. James Bond's VC5 Logbook could be stolen or forged

However, doing any of the above would not result in an ownership change on the DVLA registry.

Trust in Self-Sovereign Identity models works in a very similar way, where:

* A Decentralised Identifier (DID) is like the license plate
* A DID Document on a blockchain is like the DVLA registry
* A private cryptographic key is like the VC5 Logbook
* Authenticating using the keys in the DID Document is like proving that you can open the car with your set of keys

Of course, there is a lot of complexity here, so we will walk through each part in this learning documentation in simple terms.

{% hint style="info" %}
A DID is very similar to a car registration plate in the sense that it is a **unique identifier**, which if **resolved,** provides more information about the DID.
{% endhint %}

## Analogy: Resolving a License plate number

The equivalent to **searching a registration plate number** on a DVLA indexing site, is **resolving a DID** through a **DID resolution method**.

When you want to search for a License Plate registration, you generally search the Registration number into an indexing service, such as the DVLA website below:

![Image showing the DVLA license plate number index and search service](<../../.gitbook/assets/DVLA License plate registry search.png>)

Through this search function, you are able to retrieve information about what the license plate refers to.

For example, with James Bond's license plate, the following information is fetched:

![Indexed information about James Bond's DB5](<../../.gitbook/assets/James Bond DB5 registry details.png>)

This creates a level of confidence in the fact that the registration plate belongs to the specific car, as a person could cross reference the listed features against the visual features of the car. Further, any competent authority would have the power to go one level deeper and tie the legal owner of the car to the license plate.

## Resolving a DID

As previously mentioned a DID is a unique identifier that can be anchored to a [Verifiable Data Registry](what-is-a-vdr.md), in order to store information in a highly available way.

A DID at face value is a URL, which has the following composition:

![DID URL syntax and composition](<../../.gitbook/assets/DID URL syntax.png>)

cheqd has multiple implementations of a DID Resolver, and for more technical information you can look at our [Architecture Decision Record on DID Resolver](https://docs.cheqd.io/identity/architecture/adr-list/adr-003-did-resolver).

One common implementation of a DID Resolver is through hosting a DID Resolver on the [**Universal Resolver**](https://dev.uniresolver.io/).

Below, you can see the method for resolving a registration plate number, as well as the similar method for resolving a DID.

![Two images showing the similarities between a License plate lookup and a DID lookup service](<../../.gitbook/assets/DID cheqd universal resolver.png>)

When inputted here, relevant information will be shown about the DID, in the form of a **DID Document**. This is possible because the DID and it's adjacent DID Document are both stored on a [Verifiable Data Registry](what-is-a-vdr.md), such as a blockchain or trustworthy database.

## What does a DID Document contain?

An example of a **DID Document** is below, which explains various information about the **DID subject**. We will walk through this sequentially as it is quite technical and complex.

```json
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

## Coming back to the important question

Earlier, I asked the rhetorical question: how can James Bond prove ownership and control of this car if someone was to challenge that it was his?

The next question is, **how can James Bond prove control of his car, with the use of DIDs, DID resolution and verification keys?**

James Bond still can likely prove control and ownership of that car:

1. The unique DID related to his Aston Martin DB5 will be registered on a Verifiable Data Registry, such as a blockchain.
2. Through using a DID Resolver to resolve the DID, a third party would receive a DID Document, containing verification keys.
3. The third party creates a challenge request to authenticate the DID, and James is able to use his private key to prove control of the public key listed in the DID document. This proves James has legal control of the car without reliance on a centralised party.
4. James Bond still holds the physical keys to unlock and use the car. He now also holds cryptographic keys to authenticate and prove ownership.

Through this method of **DID resolution** and **authentication**, people, organisations or objects can have a level of cryptographic trust in the identifiers relating to them, without reliance on traditional centralised models.

This is, and will continue to be, a core building block for Web 3.0 going forward.
