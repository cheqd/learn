# What is a Decentralised Identifier ("DID")?

Decentralised Identifiers ("DIDs") are essential cornerstones of how decentralised identity works at a technical level. They are very important to understand conceptually.

According to the [World Wide Web Consortium ("W3C")](https://www.w3.org/TR/did-core/), a Decentralized Identifier, or DID, is _“a globally unique identifier that does not require a centralized registration authority because it is registered with distributed ledger technology or other form of decentralized network.”_

This definition is a bit complex and technical, so let's try and simplify it down.

### What is a DID?

It is easy to think of DIDs as identifying something in the same way as how a registration plate identifies a car, and a car's owner.&#x20;

This is James Bond's Aston Martin DB5.

![](<../../../.gitbook/assets/image (29).png>)

The important question is, how can James Bond prove ownership and control of this car if someone was to challenge that it was his?

Well, James Bond can likely prove control and ownership of that car in 2 main ways:

1. The unique registration plate `BMT 216A` will be linked to Mr Bond's identity through a central registry. Anyone is able to check that the registration details of the car match it's visual features, and the police are able to check the registered identity against the registration plate.&#x20;
2. James Bond holds the keys to unlock and use the car.&#x20;

For point number one, if you check and resolve the specific plate number using the service registry, you find the following information:\
\
![](<../../../.gitbook/assets/image (19).png>)

This creates a level of confidence in the fact that the registration plate belongs to the specific car, as a person could cross reference the listed features against the visual features of the car. Further, any competent authority would have the power to go one level deeper and tie the legal owner of the car to the license plate.&#x20;

However, how does this hold up if the car is compromised?

#### Stolen vehicle

Let's take the hypothetical scenario that Goldfinger, a classic James Bond villain, steals the keys to James Bond's car, and escapes with it for his own nefarious purposes.&#x20;

Firstly, in this scenario, a competent authority would have the capacity to be able to link the registration plate of this vehicle to James Bond's identity, through the registry, and track it down accordingly.

Secondly, if Goldfinger did try and update the registration of the car, he would struggle. This is because proving control of the keys to the car is not enough to prove ownership of the car. On top of having the keys, he would also need to provide control of something known as a "V5C logbook" to the DVLA. This logbook acts as a separate layer of protection, outside of controlling the physical car key. He would also need to impersonate James Bond, know personal information such as his post code, and likely his signature, in order to transfer the car to himself or another person, which would be very difficult for Goldfinger to pull off.&#x20;

In this way, the use of the physical car key, the V5C logbook as a verification method, the registry as a trusted data source and specific knowledge belonging to James Bond, safeguard the car from being stolen and legally changed hands.

#### These are all incredibly important concepts to understand when considering DIDs.&#x20;

### How do DIDs fit in here?

A DID is very similar to a car registration plate in the sense that it is a unique identifier, which if **resolved,** provides more information about the controller of the car, on in our case the DID.&#x20;

#### How do you resolve a DID?

The equivalent to searching a registration plate number on a DVLA indexing site, is **resolving** a DID through a **DID resolution method**. One common example is through using the [**Universal Resolver**](https://dev.uniresolver.io).

Below, you can see the method for resolving a registration plate number, as well as the similar method for resolving a DID.

![](<../../../.gitbook/assets/image (27).png>)

![](<../../../.gitbook/assets/image (14).png>)

When inputted here, relevant information will be shown about the DID, in the form of a DID Document. This is possible because the DID and it's adjacent DID Document are both stored on a Verifiable Data Registry, such as a blockchain or trustworthy database.&#x20;

### What is a DID Document?

The information which the **DID** resolves to is called the **DID Document**. This is the equivalent to the Vehicle Details that the vehicle registration plate number resolves to.

However, rather than having a database, held by a centralised company, such as the DVLA, the DID Document is stored generally on a blockchain, or occasionally within a decentralised storage platform such as IPFS. This enables third parties to trust the contents of it, without reliance on any company or server being online.

An example of a **DID Document** is below, which explains various information about the **DID subject**. We will walk through this sequentially as it is quite technical and complex.

```
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

#### `id`

The `id` field at the top, and outermost layer of the code map, identifies the **DID subject**. Using the above analogy, the **DID subject** would be James Bond's Aston Martin DB5, because it is the entity that is identified by the identifier. In more general identity use cases, the **DID subject** _could_ be an entity such as a car, but is usually a company or organisation.

{% hint style="info" %}
Note: This is the same identifier as what is inputted into the **resolver** to return this **DID Document**.&#x20;
{% endhint %}

#### `verificationMethod`

The `verificationMethod`, in this example, describes a cryptographic key or list of keys and the controller(s) of the key(s). Each Verification Key itself lists:

* an `ID` for the specific key;
* the `controller`, i.e., the identifier of the person or company with control over that key; and,&#x20;
* the `type` of cryptographic key.&#x20;

Going back to the above analogy, this is like holding the V5C logbook, as it enables **DID Controllers** to update/change/amend information about the ownership of the DID. Without access to the verification keys, the ownership or control of the DID would not be able to change.&#x20;

In reality, James Bond himself could have a specific verification key, his colleague "Q" could have a second specific key and the Secret Intelligence Service MI6, could have a third specific key. Each party would be known as a DID Controller, and would be able to update/change/amend the DID Document accordingly.&#x20;

#### `authentication`

The `authentication` property is very important. This property enables **only** the **DID subject** to prove and authenticate who they are.&#x20;

In our specific example, James Bond may be the only party that holds a Verification key, listed under the authentication property. This is almost analogous to holding the keys to the car. Using this property, if challenged about being the owner of the car, James Bond would have all the tools necessary to prove and authenticate the car, under this verification key for authentication. &#x20;

**`service`**

The `service` field provides further information about where to contact the DID subject. In our analogy, this could point to a specific email address for help@mI6.com. This property is quite flexible, but importantly, it should not disclose any personally identifiable information.&#x20;

There are also other useful fields which may be included in a DID Document, such as `assertionMethod`, `keyAgreement`, `capacityInvocation` and `capacityDelegation`. These are outside of the scope of this introductory information, and should be the topics of further reading.&#x20;

The key difference between the use of something like the license plate registry and the use of DIDs, is the former relies on a centralised database, whereas, the latter relies wholly on decentralised trust and cryptographic key management.

This makes DIDs far more extensible, scalable and workable beyond jurisdictional borders. &#x20;

#### Transferring the control over the DID&#x20;

Just like in the analogy provided earlier, where a seller of a car would need to update and then destroy the existing V5C logbook, whilst informing the DVLA, the DID controller would need to add another verification method for authentication, and remove the existing method for authentication.&#x20;

Updating the authentication method generally requires consensus of all the listed verification keys within the DID Document. This prevents there being an attack on someone who holds one key, who is able to compromise the control and ownership of the entire DID.&#x20;

#### The important question

Earlier, I asked the rhetorical question: how can James Bond prove ownership and control of this car if someone was to challenge that it was his?

The next question is, how can James Bond prove control of his car, with the use of DIDs, DID resolution and verification keys?

James Bond still can likely prove control and ownership of that car in 2 ways:

1. The unique DID related to his Aston Martin DB5 will be registered on a Verifiable Data Registry, such as a blockchain. Through resolving the DID, a third party would receive a DID Document, containing verification keys. The third party creates a challenge request to authenticate the DID, and James is able to use his private key to prove control of the public key listed in the DID document. This proves James has legal control of the car without reliance on a centralised party.
2. James Bond still holds the physical keys to unlock and use the car. He now also holds cryptographic keys to authenticate and prove ownership.

Through this method of **DID authentication**, people, organisations or objects can have a level of cryptographic trust in the identifiers relating to them, without reliance on traditional centralised models.&#x20;

This is, and will continue to be, a core building block for Web 3.0 going forward.&#x20;

For more information, please see the DID Core Specification below:

{% embed url="https://www.w3.org/TR/did-core" %}



