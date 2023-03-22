# How do you resolve a DID?

## Analogy: Resolving a License plate number

The equivalent to **searching a registration plate number** on a DVLA indexing site, is **resolving** a DID through a **DID resolution method**.

When you want to search for a License Plate registration, you generally search the Registration number into an indexing service, such as the DVLA website below:

![Image showing the DVLA license plate number index and search service](<../../../.gitbook/assets/DVLA License plate registry search.png>)

Through this search function, you are able to retrieve information about what the license plate refers to.

For example, with James Bond's license plate, the following information is fetched:

![Indexed information about James Bond's DB5](<../../../.gitbook/assets/James Bond DB5 registry details.png>)

This creates a level of confidence in the fact that the registration plate belongs to the specific car, as a person could cross reference the listed features against the visual features of the car. Further, any competent authority would have the power to go one level deeper and tie the legal owner of the car to the license plate.

## Resolving a DID

As previously mentioned a DID is a unique identifier that can be anchored to a [Verifiable Data Registry](what-is-a-verifiable-data-registry.md), in order to store information in a highly available way.

A DID at face value is a URL, which has the following composition:

![DID URL syntax and composition](<../../../.gitbook/assets/DID URL syntax.png>)

cheqd has multiple implementations of a DID Resolver, and for more technical information you can look at our [Architecture Decision Record on DID Resolver](https://docs.cheqd.io/identity/architecture/adr-list/adr-003-did-resolver).

One common implementation of a DID Resolver is through hosting a DID Resolver on the [**Universal Resolver**](https://dev.uniresolver.io/).

Below, you can see the method for resolving a registration plate number, as well as the similar method for resolving a DID.

![Two images showing the similarities between a License plate lookup and a DID lookup service](<../../../.gitbook/assets/DID cheqd universal resolver.png>)

When inputted here, relevant information will be shown about the DID, in the form of a [DID Document](what-is-a-did-document.md). This is possible because the DID and it's adjacent DID Document are both stored on a [Verifiable Data Registry](what-is-a-verifiable-data-registry.md), such as a blockchain or trustworthy database.

Learn how to understand the outcome of a DID resolution, a DID Document, in the next section.
