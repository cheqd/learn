# How DIDs build trust?

## Coming back to the important question

Earlier, I asked the rhetorical question: how can James Bond prove ownership and control of this car if someone was to challenge that it was his?

The next question is, **how can James Bond prove control of his car, with the use of DIDs, DID resolution and verification keys?**

James Bond still can likely prove control and ownership of that car:

1. The unique DID related to his Aston Martin DB5 will be registered on a Verifiable Data Registry, such as a blockchain.&#x20;
2. Through using a DID Resolver to resolve the DID, a third party would receive a DID Document, containing verification keys.&#x20;
3. The third party creates a challenge request to authenticate the DID, and James is able to use his private key to prove control of the public key listed in the DID document. This proves James has legal control of the car without reliance on a centralised party.
4. James Bond still holds the physical keys to unlock and use the car. He now also holds cryptographic keys to authenticate and prove ownership.

Through this method of **DID resolution** and **authentication**, people, organisations or objects can have a level of cryptographic trust in the identifiers relating to them, without reliance on traditional centralised models.&#x20;

This is, and will continue to be, a core building block for Web 3.0 going forward.&#x20;

For more information, please see the DID Core Specification below:

{% embed url="https://www.w3.org/TR/did-core" %}

