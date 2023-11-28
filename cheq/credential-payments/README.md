# ♻ Credential Payments

## Payment models explained

One of the most repeated bits of feedback that we've had, throughout our survey results and community engagement, is that: **more easy explanation and examples on how cheqd can be used in practice would better help people understand the project**.

This page will try and lay out simple use cases where cheqd will be able to create new commercial models. It will be split into two parts:

1. What cheqd fixes now
2. What cheqd fixes in Web 3.0

### Holder pays issuer

A holder could pay for Verifiable Credentials from an issuer. An instance where this could be useful is an individual paying for their education records or employment records, to be able to have a stronger CV.

![Holder pays Issuer](<../../.gitbook/assets/Holder pays Issuer.png>)

### Verifier pays holder

A verifier could pay a holder for sharing Verifiable Credentials. This may be an important use case where a company wants to receive extra preference data from a holder, and is willing to pay a fee for it because it is verifiable.

![Verifier pays Holder](<../../.gitbook/assets/Verifier pays Holder.png>)

### Verifier pays issuer

A verifier could pay the issuer for Verifiable Credentials it receives from the holder. This gives the issuer a recurring revenue stream each time the Credentials it issues need to be live-checked by the issuer.

The mechanism for this payment is through a revocation registry that the issuer establishes. The verifier will make a payment only if it wants to check whether the holder’s credentials have been revoked or not.

This is important to maintain privacy of the holder, preventing a correlation risk.

![Verifier pays Issuer](<../../.gitbook/assets/Verifier pays Issuer.png>)
