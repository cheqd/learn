---
description: Understand how $CHEQ is used for payments for verifiable credentials
---

# ♻️ Credential Payments

## Overview

One of the most repeated bits of feedback that we've had, throughout our survey results and community engagement, is that: **more easy explanation and examples on how cheqd can be used in practice would better help people understand the project**.

These subpages will try and lay out simple use cases where cheqd will be able to create new commercial models.

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><mark style="color:blue;"><strong>Verifier Pays Issuer</strong></mark></td><td>This is cheqd's unique superpower for monetising credential issuance, creating new commercial models for companies engaging in credential ecosystems.</td><td><a href="verifier-pays-issuer.md">verifier-pays-issuer.md</a></td></tr><tr><td><mark style="color:blue;"><strong>Holder pays Issuer</strong></mark></td><td>A more simple payment flow, enabling Holders to pay Issuers directly for "purchasing" credentials from them.</td><td><a href="cheqd-use-case-examples.md">cheqd-use-case-examples.md</a></td></tr></tbody></table>

## Payment models explained

There has been a **consistent cold start problem for digital credential ecosystems** where organisations do not see a clear commercial model or revenue opportunity to justify the switch up costs to credential-based technologies. This is because the perceived value in Verifiable Credentials is the costs saved when there is a significant amount in circulation (the chicken🐔), but this cannot occur without organisations issuing credentials in the first place (the egg🥚).

Unfortunately, the benefits of credentials, prior to the point of mass adoption, provide no compelling reason for businesses to change their current data collection and retention practices until this is the case.

Since launching cheqd, our hypothesis has been that **Credential Payments will be the catalyst for credential adoption**, by incentivising issuers to release data back to the holder, and allowing them to set a price for trusted data checks. This thinking has since been validated by data collected by cheqd’s partners and potential customers, where **70% of respondents believed that payment rails would help drive adoption with their customers.**

We now believe that credential ecosystems are technically mature enough to scale, especially with [new regulations like eIDAS 2.0](https://blog.avast.com/eidas-2.0-avast) accelerating their adoption and providing a template for interoperability. Yet, there is a barrier between the theoretical and philosophical benefits of Verifiable Credentials, and the commercial and business benefits of Verifiable Credentials. A **payments or incentive layer is still required to provide a compelling reason for&#x20;**_**enterprise organisations**_**&#x20;to make the switch**.

To achieve this shift, we’ve built Credential Payments into our [**cheqd Studio**](https://cheqd.io/solutions/cheqd-studio/) product to allow organisations to build trusted data markets easily, with simple REST APIs. This abstracts the complexity and responsibility of handling interactions with the ledger and provides a clear integration pathway for developers that are not familiar with decentralised identity standards or blockchain.
