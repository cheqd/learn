# 🪙 Introduction to $CHEQ

## Background

Before reading this page, please familiarise yourself with the page:

{% content-ref url="../introduction-to-decentralised-identity/" %}
[introduction-to-decentralised-identity](../introduction-to-decentralised-identity/)
{% endcontent-ref %}

cheqd is unique in that it provides a way for [Verifiable Credentials](../introduction-to-decentralised-identity/what-is-a-verifiable-credential-vc/) to be monetised using its native token, $CHEQ. **** There are various commercial models that may be created by using the cheqd network.

We will give the example of three distinct payment models:

* [Holder pays issuer](./#holder-pays-issuer)
* [Verifier pays holder](./#verifier-pays-holder)
* [Verifier pays issuer](./#verifier-pays-issuer)

## Payment models explained

### Holder pays issuer

A holder could pay for Verifiable Credentials from an issuer. An instance where this could be useful is an individual paying for their education records or employment records, to be able to have a stronger CV.

![Holder pays Issuer](../../.gitbook/assets/Holder%20pays%20Issuer.png)

### Verifier pays holder

A verifier could pay a holder for sharing Verifiable Credentials. This may be an important use case where a company wants to receive extra preference data from a holder, and is willing to pay a fee for it because it is verifiable.

![Verifier pays Holder](../../.gitbook/assets/Verifier%20pays%20Holder.png)

### Verifier pays issuer

A verifier could pay the issuer for Verifiable Credentials it receives from the holder. This gives the issuer a recurring revenue stream each time the Credentials it issues need to be live-checked by the issuer.

The mechanism for this payment is through a revocation registry that the issuer establishes. The verifier will make a payment only if it wants to check whether the holder’s credentials have been revoked or not.

This is important to maintain privacy of the holder, preventing a correlation risk.

![Verifier pays Issuer](../../.gitbook/assets/Verifier%20pays%20Issuer.png)
