# What is a Decentralised Identifier ("DID")?

Decentralised Identifiers ("DIDs") are essential cornerstones of how decentralised identity works at a technical level. They are very important to understand conceptually.

According to the [World Wide Web Consortium ("W3C")](https://www.w3.org/TR/did-core/), a Decentralized Identifier, or DID, is _“a globally unique identifier that does not require a centralized registration authority because it is registered with distributed ledger technology or other form of decentralized network.”_

This definition is a bit complex and technical, so let's try and simplify it down.

## What is a DID?

It is easy to think of DIDs as identifying something **in the same way as how a registration plate identifies a car**, and a car's owner.

To take an example, this is **James Bond's Aston Martin DB5**.

![Image showing James Bond's Aston Martin DB5](<../../../.gitbook/assets/James Bond DB5.png>)

James Bond's Aston Martin has a unique identifier, the license plate, identifying the owner of the car and also the features of the car:

{% hint style="success" %}
BMT 216A
{% endhint %}

Similarly, a DID is a unique identifier, identifying the DID subject (a person, company or thing), and providing information about the DID subject.

{% hint style="success" %}
did:cheqd:mainnet:zF7rhDBfUt9d1gJPjx7s1JXfUY7oVWkY
{% endhint %}

Both identifiers can be checked against a registry in order to provide verifiable information about the thing that the identifier is identifying.

The process for withdrawing the information from the DID is very similar to the license plate number: this will be expanded on in the section [How do you resolve a DID?](how-do-you-resolve-a-did.md)

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

### Understanding DIDs

To fully understand how DIDs work and why they are important, we will walk through the core information required for DIDs:

{% content-ref url="how-do-you-resolve-a-did.md" %}
[how-do-you-resolve-a-did.md](how-do-you-resolve-a-did.md)
{% endcontent-ref %}

{% content-ref url="what-is-a-did-document.md" %}
[what-is-a-did-document.md](what-is-a-did-document.md)
{% endcontent-ref %}

{% content-ref url="how-do-dids-build-trust.md" %}
[how-do-dids-build-trust.md](how-do-dids-build-trust.md)
{% endcontent-ref %}

For further reading on DIDs, you can read:

{% content-ref url="what-is-a-verifiable-data-registry.md" %}
[what-is-a-verifiable-data-registry.md](what-is-a-verifiable-data-registry.md)
{% endcontent-ref %}

{% content-ref url="what-is-a-did-method.md" %}
[what-is-a-did-method.md](what-is-a-did-method.md)
{% endcontent-ref %}

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

