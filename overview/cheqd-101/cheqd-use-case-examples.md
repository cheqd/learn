# cheqd use case examples

## cheqd use case examples

One of the most repeated bits of feedback that we've had, throughout our survey results and community engagement, is that: **more easy explanation and examples on how cheqd can be used in practice would better help people understand the project**.

This page will try and lay out simple use cases where cheqd will be able to create new commercial models. It will be split into two parts:

1. What cheqd fixes now
2. What cheqd fixes in Web 3.0

### Example of holder paying for Verifiable Credentials

For a high level explanation of how decentralised identity and cheqd's payment rails work, please see the pages:

{% content-ref url="../introduction-to-decentralised-identity/" %}
[introduction-to-decentralised-identity](../introduction-to-decentralised-identity/)
{% endcontent-ref %}

{% content-ref url="../introduction-to-usdcheq.md" %}
[introduction-to-usdcheq.md](../introduction-to-usdcheq.md)
{% endcontent-ref %}

#### What cheqd fixes now

![](<../../.gitbook/assets/Jane Doe image>)**This is Jane Doe**

Jane Doe has recently completed her university degree at Bright University. She wants to receive a digital, verifiable and certifiable copy of her diploma to apply for a prospective job.

In order for this to happen, first Bright University needs to register their [Decentralised Identifier (DID)](../introduction-to-decentralised-identity/what-is-a-decentralised-identifier-did/) to a [Verifiable Data Registry](../introduction-to-decentralised-identity/what-is-a-decentralised-identifier-did/what-is-a-verifiable-data-registry.md) or ledger. In this case, Bright University anchor their [DID](../introduction-to-decentralised-identity/what-is-a-decentralised-identifier-did/) to cheqd, using the cheqd DID method.

![University anchors DID to cheqd mainnet](<../../.gitbook/assets/Jane Doe - Issuer anchors DID.png>)

The specific Public DID is registered as `did:cheqd:mainnet:923u592u5ghgu3r8`

Bright University also anchors an adjacent DID Document which contains information about Bright University such as:

* This is the DID of Bright University
* This is the endpoint for Bright University's help/contact address
* These are the list of public keys that Bright University might sign with for Verifiable Credentials for University Degrees.&#x20;

To learn about what a DID and a DID Document is, please see the page:

{% content-ref url="../introduction-to-decentralised-identity/what-is-a-decentralised-identifier-did/" %}
[what-is-a-decentralised-identifier-did](../introduction-to-decentralised-identity/what-is-a-decentralised-identifier-did/)
{% endcontent-ref %}

Jane has completed her degree and she has successfully achieved a First Class Honours. Now, she wants to receive a digital copy of the diploma to be able to hold it in her digital identity wallet.&#x20;

On the physical certificate there is a QR code which Jane scans. This creates a peer-to-peer encrypted channel between the University and Jane's phone, which has her digital identity wallet.

Bright University issues a [Verifiable Credential](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/) to Jane through this peer-to-peer encrypted channel. The [Verifiable Credential](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/) has the following claims:

* This is Jane Doe's diploma
* Jane Doe graduated from Bright University in the year 2022
* Jane Doe achieved a First Class Honours in her MSC degree in Computer Science.&#x20;

The Verifiable Credential has a proof, meaning it is digitally signed by the Public DID of Bright University, as well as potentially cryptographic material referring to a specific public key, which may be used for a particular purpose (such as asserting claims).&#x20;

To learn more about Verifiable Credentials, please see the page:

{% content-ref url="../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/" %}
[what-is-a-verifiable-credential-vc](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/)
{% endcontent-ref %}

![Issuer issues Jane Doe a Verifiable Credential anchored on cheqd mainnet](<../../.gitbook/assets/Jane Doe - Issuer issues VC.png>)

In return for a very high value University Credential, that provides Jane a verifiable record of her diploma, and is an optional addition to Jane's physical diploma, Jane is required to pay the University $10.00 USD.&#x20;

Jane is required to pay this $10.00 in $CHEQ (or a stablecoin that she holds), before she is able to receive the [Verifiable Credential](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/). In the background the price of $CHEQ is equated to $10.00 USD, and is transferred to Bright University's wallet address.&#x20;

Jane receives the [Verifiable Credential](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/) to her digital identity wallet once the payment has been successfully completed. This entire data flow takes place off-ledger. This is important because it keeps all of Jane's personal information private, and only with her.&#x20;

&#x20;

![Jane Doe pays issuer for the Verifiable Credential using $CHEQ or a stablecoin](<../../.gitbook/assets/Jane Doe - Pays for Credential.png>)

Jane now holds a Verifiable Credential of her University degree in her digital identity wallet and is able to use this to prove claims about herself.

Jane applies online for a new job as a Lead Engineer at a leading technology company.

The technology company asks for Jane to upload her education records. Rather than filling out the form manually; Jane scans another QR code to create a peer-to-peer encrypted channel with the technology company. Jane sends a [Verifiable Presentation](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/what-is-a-verifiable-presentation.md) containing her claims and the attached proof to those claims, in a few clicks or taps.&#x20;

![Jane Doe presents the Credential as a Verifiable Presentation to the Verifier](<../../.gitbook/assets/Jane Doe - Presents Credential to Verifier.png>)

The technology company is able to verify the validity of the claims that Jane presents, by resolving the DID embedded in the Presentation. Through resolving the DID, the technology company is able to see the DID Document and the information contained. Automatically, the technology company is able to ascertain that the proof inside Jane's Verifiable Presentation was issued by the real Bright University and is for the correct purpose.&#x20;

The technology company is now satisfied and progresses Jane to the next phase of the application.&#x20;

#### What cheqd fixes in Web 3.0

![](<../../.gitbook/assets/John Smith image>)**This is John Smith**

John Smith is a gamer who has built a substantial in-game profile for game developer's, Digiplay, latest metaverse game. John wants to receive a verifiable copy of his in game assets, which he can hold ownership of, unilaterally, in his digital data wallet, in order to port these assets over to a new game made by MetaZap.

In order for this to happen, first DigiPlay needs to register their [Decentralised Identifier (DID)](../introduction-to-decentralised-identity/what-is-a-decentralised-identifier-did/) to a [Verifiable Data Registry](../introduction-to-decentralised-identity/what-is-a-decentralised-identifier-did/what-is-a-verifiable-data-registry.md) or ledger. In this case, DigiPlay anchors their [DID](../introduction-to-decentralised-identity/what-is-a-decentralised-identifier-did/) to cheqd mainnet, using the cheqd DID method.

![DigiPlay anchors DID to cheqd mainnet](<../../.gitbook/assets/John Smith - Issuer anchors DID.png>)

The specific Public DID is registered as `did:cheqd:mainnet:6nhj3p3yf8f83g14`

DigiPlay also anchors an adjacent DID Document which contains information about the game developer, such as:

* This is the official game developer DigiPlay
* This is the endpoint for DigiPlay's help/contact address
* These are the list of public keys that DigiPlay might sign with for Verifiable Credentials for different game accomplishments and in-game assets.

John has put a significant amount of hours into DigiPlay's title, but does not want to lose the progress he's made, as the game becomes obsolete and older. He wants to be able to port his progress into another, technically compatible title, in order to continue progressing from a relative position. He also has unlocked unique and rare skins, cosmetics and in-game assets which he wants to be able to use in future games.&#x20;

Therefore, he scans a QR code provided by DigiPlay on their in-game main menu which creates a pairwise, peer-to-peer encrypted channel between John and DigiPlay. Through this channel, DigiPlay issues John a [Verifiable Credential](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/#what-is-a-verifiable-credential), or series of Verifiable Credentials, with various in game information such as:

* This is John Smith's gamertag: JohnSmith99
* John has reached rank 55 in our title
* John has received the following achievements on his profile:
  * Achievement A
  * Achievement B&#x20;
  * Achievement C
* John has unilateral ownership of rare and unique items in this game:
  * NFT Blue Leopard skin for GG-B67
  * NFT Navy-blue 49145 player skin
  * NFT  8676 Custom stock

In this instance, the [Verifiable Credential](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/#what-is-a-verifiable-credential) gives John a way to prove that he owns these items, easily, and he is able to showcase his profile and in-game assets in compatible wallets and third-party games.&#x20;

![DigiPlay issues Verifiable Credential to John Smith, anchored on cheqd mainnet](<../../.gitbook/assets/John Smith - Issuer issues VC to John.png>)

Since without a Verifiable Credential, John will lose these in-game assets he has earnt, he is happy to pay a $15,00 one-time fee to get a verifiable digital copy of his assets in order to hold them unilaterally in a digital wallet, data vault or secure enclave on his PC, games console, or mobile phone.

Before John is able to receive the Verifiable Credential, in the background the price of $CHEQ is equated to $15.00 USD, and is transferred to DigiPlay's wallet address.&#x20;

John receives the Verifiable Credential once the payment has been successfully completed.

![John Smith pays for Verifiable Credential in $CHEQ or stablecoin](<../../.gitbook/assets/John Smith - Pays for VC.png>)

John now holds a Verifiable Credential of his in-game profile in his digital data wallet on his desired console, mobile or computer, and is able to use this to prove attributes about himself.

John now wants to start a new game with a brand new metaverse title, made by game's company MetaZap.

John wants to port his in game assets, skins and prestige to MetaZap to build verifiable status in his player profile and allow him to use his unique items.&#x20;

When John starts up MetaZap, the initial loading menu asks John whether he wants to port over any existing assets. John scans another QR code to create a peer-to-peer encrypted channel with MetaZap. John sends a [Verifiable Presentation](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/what-is-a-verifiable-presentation.md) containing his relevant data and claims with the attached proof to those claims.&#x20;

![John Smith presents Credential as a Verifiable Presentation to MetaZap](<../../.gitbook/assets/John Smith - Presents VC to Verifier.png>)

MetaZap is able to verify the validity of the claims that John presents, by resolving the DID embedded in the Presentation. Through resolving the DID, MetaZap is able to see the DID Document and the information contained from DigiPlay. Automatically, it is able to ascertain that the proof inside John's [Verifiable Presentation](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/what-is-a-verifiable-presentation.md) was issued by the real DigiPlay and starts downloading John's assets into his MetaZap account.
