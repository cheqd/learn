# 3⃣ Tokenomics: Part 3

{% hint style="info" %}
**Note:** _Despite the document below detailing out the payment models we are building, we are not trying to impose a single business model on everyone, we believe all ecosystems need to have their own choice in what works best for them. The tooling and patterns will be made available to the SSI community to use as they see fit, allowing for a mix of free and paid credentials._
{% endhint %}

_To use an example, we see it as_ [_unlikely that the National Health Service in the UK would charge for credentials moving between their own hospitals_](https://www.independent.co.uk/news/business/business-reporter/nhs-entrepreneurs-revolutionise-staffing-checks-b1883780.html)_. However, they may seek to monetise those which are used in private health._

_We believe both models should be possible and will be providing the tooling on that basis._

## What are we solving for? <a href="#e704" id="e704"></a>

### Example <a href="#8573" id="8573"></a>

The requirements explained below are best understood following an SSI example. We’ll briefly consider peer-to-peer verification before payments or transfers of digital assets, inc. NFTs.

Either through self-attested data or third-party attested data one user can prove their identity to another, [avoiding the service support imposters which have plagued OpenSea recently](https://nftcadets.com/opensea-to-add-metalink-customer-service-channel/) or remove the need for test transfers, i.e. sending 1 token to confirm the recipient then sending the balance. This could be especially powerful in allowing DeFi protocols to meet the[ Travel Rule](https://www.fincen.gov/sites/default/files/advisory/advissu7.pdf) whilst maintaining individual’s privacy as far as possible.

![](https://miro.medium.com/max/1400/0\*fDk7XJG1c\_sIKPPX)

User journey steps:

1. _Institution 1 shares documents to KYC provider_
2. _KYC provider issues certified docs to Institution 1_
3. _User creates DeFi pool (e.g. liquidity) with defined KYC criteria / process_
4. _Institution 1 provides appropriate KYC information_
5. _Pool processes certified docs and stores encrypted references_
6. _Institution 1 supplies / trades assets as desired._
7. _Institution 2 does not provide appropriate KYC info_
8. _Institution 2 attempts to supply / trade assets as desired but is blocked by pool_

### Principles <a href="#45ea" id="45ea"></a>

Before diving into the payment models, it is worth grounding on the principles which informed these. Whilst there are many detailed requirements they can be summarised into:

1. **Privacy:** It should not be possible to follow payments to either identify an individual or track their interactions (even pseudonymously).
2. **Privacy:** Resulting from 1, but also to ensure the network remains [General Data Protection Regulation (GDPR) ](https://www.europarl.europa.eu/RegData/etudes/STUD/2019/634445/EPRS\_STU\(2019\)634445\_EN.pdf)and other privacy regulation compliant, no personal data (even encrypted) should be written to the ledger.&#x20;
3. **Stability:** Any price for a credential should be stable (against fiat) across time to avoid misaligned incentives, i.e. a verification is delayed hoping for a price increase or decrease.
4. **Low-cost:** Transfers should not incur significant costs
5. **Arbitrage resistant:** Recipients of data should not be able to avoid paying for that data if a tariff has been set
6. **Commercially sustainable:** Any commercial model(s) should enable the network to be self-sufficient without penalising ecosystems on top.
7. **Flexible:** Proprietary credential formats should not be required.\
   Commercial models should not be dictated by the network. They should be available for those who wish to use them but not dictated by the protocol.

**Read vs write volumes**

One model we have seen frequently is monetising any “identity” writes to the ledger, with some focusing on public DIDs and others allowing personally identifiable information onto the ledger to make charging easier, albeit by sacrificing privacy.

We see this as an unnecessary sacrifice. From our analysis, it is much better to focus on credential presentations / reads rather than writes to the ledger which the table articulates using passport issuance in the UK as an example.

| Transaction                    | Location   | Analogous to                           | Frequency                | Volume                                                 |
| ------------------------------ | ---------- | -------------------------------------- | ------------------------ | ------------------------------------------------------ |
| Writing public DID to network  | On-ledger  | Refreshing SSL certificate for website | \~once per year          | \~ <10 per organisation                                |
| Issuing Verifiable Credential  | Off-ledger | Issuing Passport                       | \~1 per decade / 5 years | >5 million per year                                    |
| Reading / Verifying Credential | Off-ledger | Reading / checking passport            | >30 checks per year\*    | >15 million per year (using figures above and to left) |

_\*_ [_The average UK household takes \~3.9 holidays per year._ ](https://www.statista.com/statistics/480188/average-number-of-holidays-per-person-in-the-uk/)_Multiplying for both outbound and inbound flights (x2) and the touchpoints whilst travelling (x4: check-in, exit border, departures, entry border) equals 31.2 checks per year. This ignores non-travel uses of passports, i.e. opening bank, insurance or telecomms accounts._

Since credentials should not be written to the ledger, using passports as an example there is approximately a 1.5m factor between the DIDs written and the number of the credentials read / received. Monetising these fits the needs of the market most but also works best with the volumes.

Now to the payment model themselves.

## Payment models <a href="#b38f" id="b38f"></a>

Whilst there are numerous commercial models to come, we will focus on the two payment models which will help form the building blocks of these. These are:

* Holder pays issuer; Receiver pays holder
* Receiver pays issuer

![Payment model diagrams](https://miro.medium.com/max/1400/0\*fF0THe3wwNYHOZ0m)

_Note: Whilst the diagram shows one organisation as an issuer and one as a receiver, these roles are interchangeable depending on the data being transacted and the surrounding interaction._

As can be seen from the table below, each of these models has its place facilitating business models for identity already and we expect SSI ecosystems will combine these to suit their needs.

| Model                                    | Example                                                                                                                                                                                                                                                           |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Holder pays issuer; Receiver pays holder | <p>Buy your passport from the government (holder pays issuer).<br><br>E.g. UK passport has a £75.50 charge</p>                                                                                                                                                    |
| Receiver pays issuer                     | <p>Background checking company paying university for confirmation of applicant's degree.<br><br>E.g. <a href="https://www.imperial.ac.uk/student-records-and-data/verify-student-qualifications/">Imperial College Verification Service</a> has a £12 charge </p> |

### Receiver pays issuer <a href="#0278" id="0278"></a>

Firstly, we will tackle “receiver pays issuer” since it is both the model which is requested most by our partners and the model which will have the greatest impact on cheqd tokenomics.

We will be stepping through the building blocks before arriving at the solution we will be building, explaining our logic as we go, covering:

1. Revocation registries
2. Stablecoins
3. Escrows
4. Line of credit
5. Collateral

#### **Revocation registries**

Revocation registries, as their name suggests, are used to define whether a credential has been revoked or not once it has been issued. As usual this is best explained using an example:

_As we all know, driving licences are used for much more than proving the ability of an individual to drive. They are frequently used in bars or grocery shops for buying cigarettes or alcohol, or specific to the latter, picking up packages which have been delivered there. In this scenario, there is little benefit to knowing if the driving licence has been revoked or rescinded. Your legality to drive (or not) does not have any bearing on whether you are old enough to buy cigarettes or are the right individual to pick up a package._

_In contrast, your ability to rent a car is directly tied to that legality to drive, hence why rental agencies verify your licence as well as checking for any points._

Crucially, whilst revocation registries exist on-ledger, they do not identify individuals, preventing privacy leakage. This provides an ideal component for monetising credential verifications where desired.

For anyone interested in more detail, our partners at Tykn have [written an excellent explanation on the requirements and workings of current revocation registries on Hyperledger Indy](https://tykn.tech/identity-revocation-blockchain/#What\_is\_a\_Revocation\_Registry).

#### **Stablecoins**

Since one of the requirements was for the price of and payments for credentials to be stable over time, this enforced the need to use a stablecoin for denomination and payment. Using any volatile token could lead to arbitrage opportunities for both verifying or paying for credentials leading to dysfunctional ecosystems. However, since the tooling will be built to be agnostic, counterparties who wish to transact in non-stables will be able to do so.

Whilst we will initially build out around a single stablecoin for speed, we expect this to be flexible in the future so any ecosystem can decide to use any stablecoin. This would also allow settlement in Central Bank Digital Currencies / GovCoins which could bring broad adoption to cheqd.

Rather than build our own stablecoin, we will leverage pre-existing solutions in the market, partly for our own speed but also, if it’s not broken, it doesn’t need fixing.

#### **Escrows**

Since maintaining anonymity for individuals, minimising transaction costs and establishing an extensible pattern were key requirements, our team and advisors coalesced around an escrow pattern.

_An escrow is a contractual arrangement in which a third party (the stakeholder or escrow agent) receives and disburses money or property for the primary transacting parties, with the disbursement dependent on conditions agreed to by the transacting parties. (_[_Wikipedia_](https://en.wikipedia.org/wiki/Escrow)_)_

Escrows have been used for centuries to ensure payment is only made if certain conditions are met whilst preventing either the sender or the recipient from gaming the payment. Most people experience these when buying houses with funds put into escrow with solicitors until the transfer of ownership of the house can be confirmed, at which point the funds are unlocked.

_Uncoincidentally, our CEO holds_ [_patents for using escrows for Hashed Timelock Contracts for cross-blockchain payments_](https://patentimages.storage.googleapis.com/68/66/e8/f34a2a61885e4f/US11232441.pdf) _as part of his work on Central Bank Digital Currencies on the_ [_Jasper-Ubin_](https://www.mas.gov.sg/-/media/Jasper-Ubin-Design-Paper.pdf) _project with the Monetary Authority of Singapore and Bank of Canada._

This function maps extremely well to executing a payment only if a credential has been verified. Escrows also present additional benefits:

* Aggregating payments reduces the number of privacy attack vectors since payments are not made individually
* Aggregating payments reduces the transaction costs overall since payments are made in bulk
* Extensibility, see section further on.

#### **Line of credit**

A line of credit (LOC) is a preset borrowing limit that can be tapped into at any time. The borrower can take money out as needed until the limit is reached, and as money is repaid, it can be borrowed again in the case of an open line of credit. (Investopedia)

Since organisations prefer to maintain their capital / cash as far as possible rather than pay transactional fees, it does not make sense for any receivers to make payments to the escrow each time a verification is performed.

Instead, we expect organisations to prefer either a fortnightly or monthly payment cycle. Since payments are incurred per verification but only settled fortnightly, monthly or on-demand, this creates the need for credit with the receiver building up debt on the escrow before settling periodically. This is analogous to liquidity provisioning in pools in that liquidity can be bonded for a given timeframe, then claimed based on that committed timeframe.

The question then becomes, where does this line of credit come from. Since we are operating in a public-permissionless system, it makes little sense for issuers to extend lines of credit to receivers. Especially since these roles are interchangeable. Which leads us to collateral.

#### **Collateral**

This line of credit can be leased from the network through collateral locked to the escrows. This allows a receiver / receiver of data to maintain a line of credit up to the value of the CHEQ they hold multiplied by a factor to avoid [margin calls](https://www.investopedia.com/terms/m/margincall.asp), creating the two following scenarios:

* Receiver settles debt on time: credit limit remains
* Receiver does not settle on time: collateral slashed / penalised on pre-agreed terms

Over time, it is likely that the collateral will become blended to reduce volatility and hence reduce the factor required to avoid the margin calls mentioned above. [MakerDAO has plenty of excellent work](https://makerdao.world/en/learn/governance/param-liquidation-ratio/) on this which we will be leveraging so we don’t reinvent the wheel! Initially, we are likely to use a 200% liquidation ratio to protect against volatility with the aim of reducing this as the solution matures. Similarly, we will be looking at existing implementations such as [Aave](https://aave.com) to bootstrap development.

Please see more details in the Supply & Demand section below.

We are closely watching Osmosis’ [superfluid staking](https://www.youtube.com/watch?v=qlnjQ6V4LwM) and Persistence’s liquid [staking work](https://persistence.one) respectively for their ability to provide returns whilst assets are locked as collateral.

**Combined**\
Combining the components mentioned above results in the payment diagrams below. The arrows in white are the typical credential flow with those in gold showing the payment flows we will be laying on.

![Receiver pays issuer: credential exchange flow](https://miro.medium.com/max/1400/1\*1XMl9vwAF1wvKaWSKVV7bA.png)

User journey steps:

1. _**Issuer** publishes credential price and recipient wallet address (either on ledger or not)_
2. _**Receiver** stakes $CHEQ to Escrow contract to collateralise line of credit_
3. _**Issuer** issues credential to holder_
4. _**Issuer** updates revocation registry for the credential_
5. _**Holder** presents / shares credentials and commits to pay_
6. _**Receiver** presents which credential they want to verify to **Escrow** contract and commits to pay_
7. _**Escrow** checks CHEQ <> Stablecoin exchange rate for use to evaluate credit limit_
8. _**Escrow** increments debt amount with credential price_
9. _**Escrow** retrieves revocation result from the **Revocation registry**_
10. _**Escrow** returns revocation result to **Receiver**_
11. _**Receiver** pays **Issuer** in stablecoin_
12. _**Receiver** presents proof of payment to the **Escrow**_
13. _**Escrow** checks proof of payment_
14. _**Escrow** clears down the debt_
15. _Cycle repeats_

__

![Receiver pays issuer: settlement flow — happy path](https://miro.medium.com/max/1400/1\*T2NY8H-k8X-uUmoeGbFZrQ.png)

**Extensibility**\
As mentioned when explaining escrows, one of their benefits is extensibility, specifically for commercial models. The payment flow above represents a building block for these with the escrow the key piece of the puzzle to move from “receiver pays issuer” to much more complex commercial models such as subscriptions, volume-based discounting or cost mutualisation.

To achieve these, the escrow moves from facilitating payments between two organisations in a relatively dumb manner, e.g. debt is built up by receiver to an issuer and periodically settled, to adjusting the debt increment depending on a pre-agreed schedule, e.g. an issuer provides discounts to any receiver who verifies more than 10k credentials in a given month, or a consortium nets off their debts to each other before settlement to reduce the amounts being transferred unnecessarily.

We see this as one of the major benefits to using escrows for this purpose.

## Receiver pays holder; holder pays issuer <a href="#a3f8" id="a3f8"></a>

### Receiver pays holder <a href="#e6e1" id="e6e1"></a>

One of the greatest opportunities with these payment rails is rewarding the individual (holder) for the data they share, whether that data has come from an issuing organisation or is direct from themselves. Specifically flipping around the following quote:

_If you are not paying for it, you’re not the customer; you’re the product being sold._

Since there are already models for this interaction in the current world (brave browser and the Basic Attention Token), it is easy to model this into an SSI payment flow. Furthermore, the transaction fees and price stability requirements are less restrictive since the interaction is expected to be transactional and payment will be relatively instant whether issuing or presenting / sharing credentials.

That being said, the individual or organisation may wish to pay or be paid in either stablecoin or stable & privacy token to maintain price stability but more importantly their privacy.

![Receiver pays holder: credential exchange flow](https://miro.medium.com/max/1400/0\*5J3UHkVi\_Jci6sto)

## Holder pays issuer <a href="#fde6" id="fde6"></a>

As per Table 2, there are frequent interactions where an individual will purchase a credential from an organisation and then be able to share it elsewhere without restriction, potentially being paid / rewarded in the previous section. Passports are an easy example, but so is [classpass](https://classpass.com) (subscription / voucher which allows access to multiple gyms / salons), showing the range of value these credentials can represent.

The pervasiveness of this model already will guarantee this model will see frequent use.

![Holder pays issuer: credential exchange flow](https://miro.medium.com/max/1400/0\*tnEjXIGJ\_zru\_-BD)

## CHEQ supply & demand <a href="#5ffb" id="5ffb"></a>

As CHEQ will be used as collateral for the lines of credit mentioned above, we expect this will have a significant impact across supply & demand.

### Supply <a href="#cc8a" id="cc8a"></a>

The tokenomics at distribution / genesis were covered in our [earlier blog here](https://blog.cheqd.io/cheqds-tokenomics-for-ssi-explained-part-2-c4ecfc32b813). At the time of writing this blog (28th February 2022), the total supply of CHEQs in the market is \~1.008B with an inflation rate of \~2%, with a maximum of 4% currently set.

We are currently working on APIs to feed Total Current Supply and Current Circulating Supply directly into CoinMarketCap and CoinGecko since these are not readily available in Cosmos SDK.

### Demand <a href="#54d6" id="54d6"></a>

Since CHEQs will be used as collateral for lines of credit, across the entire network CHEQs will be locked up in proportion to the number of organisations maintaining these lines of credit and the size of the line of credit they wish to maintain.

The table below articulates the proportion of tokens which would be locked up dependent on the token price, assuming a 200% liquidation rate which would be likely when the payment models are first released.

![# CHEQs / % supply required to establish a given Line of Credit](https://miro.medium.com/max/1400/1\*32SwbHMnLOMMWEtJKAZSNQ.png)

Related to this, it is worth us re-sharing how many of these ecosystems /use-cases and hence companies (since each consortium will involve multiple companies) we are expecting to leverage the network.

![cheqd’s expectation of SSI ecosystem formation](https://miro.medium.com/max/1400/1\*mdbxgQWfbS2NajYvgevg2g.png)

## Building <a href="#b91f" id="b91f"></a>

### Still to come <a href="#6ad0" id="6ad0"></a>

Throughout this blog we have talked about the payment models being building blocks for the commercial models. Whilst the payment rails will keep the cheqd team busy enough for a while, we will then build out those customisable commercial models for DAOs, consortia and individual organisations.

Beyond this, we have ideas on how to solve reputation in a public-permissionless SSI ecosystem, i.e. ensuring incentives prevent bad actors from issuing fraudulent credentials, and counter-party risk, i.e. where poor quality or fraudulent credentials are issued, any party harmed by these can claim, potentially via insurance mechanisms.

Expect more blogs as we flesh out our ideas for tackling these.

### Next steps <a href="#f9c6" id="f9c6"></a>

This approach and architecture has been gestating since we founded cheqd with the last 6 months dedicated to establishing a standards-based viable network for anyone who wants to use the network regardless of payments.

We have now turned our focus to building the payment and commercial models for SSI as we originally set out to do. There is much more work to be done but we wanted to share our approach so that anyone who is interested in our mission and interested in collaborating can begin doing so.

