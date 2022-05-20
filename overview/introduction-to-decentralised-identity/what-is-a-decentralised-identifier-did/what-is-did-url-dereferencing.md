# What is DID URL Dereferencing?

\[More to do]

When you resolve a DID, a DID Document is returned. For example, resolving: "did:cheqd:example1234" would return the full DID Document associated with the specific DID "did:cheqd:example1234".

Dereferecing a DID URL is slightly different. When you dereference a DID URL, you are parsing the DID URL for specific actions, for example:

* Fragment **( # )**
* Query **( ? )**
* Path **( / )**

For example, "did:cheqd:example1234?service=CLSchema" can be dereferenced. In this case it will query the service of type "CLSchema" within the DID Document and will return the resource specified at the Service Endpoint within the DID Document. It is this type of architecture that cheqd uses in this ADR to fetch schemas.
