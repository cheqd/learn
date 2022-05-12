# Why identity needs a token

Every so often, we are asked why Self-Sovereign Identity (SSI) needs a token.

Briefly, [SSI](https://www.youtube.com/watch?v=z9f36Sh4CFM) is a new paradigm for exchanging authentic and trusted data related to people, companies, and things in a much more secure and privacy-preserving way. It gives the subject a verified master-copy of their own data, affording control over what information they share and removing the need to store personal data solely in central databases.

SSI has made fantastic progress in the last couple of years, as shown by [Northern Block's growing map of SSI implementations](https://northernblock.io). Still, we have seen many projects fail due to not being able to commercialise the technology, which we are solving. More than this, though, because SSI combines historically siloed datasets by making the user the ecosystem's centre, new opportunities and business models will become possible.

Essentially, our core hypothesis is that SSI needs commercial models that accelerate its adoption. In this equation, the token represents an enabler of those commercial models.

## Payment rails <a href="#a5c4" id="a5c4"></a>

Usually, the question of "why does SSI need a token" stems from a belief that there are existing, viable payment rails. However, as it was already [pointed out](https://sovrin.org/wp-content/uploads/Sovrin-Protocol-and-Token-White-Paper.pdf) in 2018, traditional rails don't work when issuers and receivers of credentials are unlikely to have a direct contractual relationship since the user is at the centre.

Let's use our example of working with two law firms (obviously anonymously):

* cheqd can pay via both USD and [USD Coin (USDC](https://en.wikipedia.org/wiki/USD\_Coin)) and holds accounts in country A and country B.
* Firm A takes payment in USD. Their bank is based in country B, but they use an intermediary bank in country C.
* Firm B takes payment in USDC.

### Fiat <a href="#8c6f" id="8c6f"></a>

To pay Firm A, we had a period of a week checking whether we could send directly from our bank account in country A where we hold the bulk of our funds to Firm A's account in country B. Paying directly from our account in country A is our preferred option since we get good exchange rates. Unfortunately, we couldn't send this payment via USD and hence had to begin checking losses from exchange rates and fees to make sure we got the amount right and minimise our losses. Eventually, we landed on sending the payment in multiple steps, from our account in country A to our account in country B, which required USD to EUR conversion due to the network used for the overseas transfer requiring EUR for the transfer. This was then converted back into USD due to Firm A's invoice being in USD and then to the Firm's account in Country B.

![](https://miro.medium.com/max/1400/1\*u8PDkLUHvw-8gtt9MPXjMg.png)

### Token <a href="#a76d" id="a76d"></a>

Since cheqd already holds USDC balances, we paid in USDC directly (noting both being in different countries).

![](https://miro.medium.com/max/1400/1\*purlHr0xcEawB3cD4497uQ.png)

### New rails <a href="#aa99" id="aa99"></a>

So, where does it leave us? Even where companies have contractual relationships, settling payments is still a huge headache. Expecting payments across an SSI ecosystem to be seamless and scalable using existing payment rails is laughable. Like other industries and technologies from finance to distributed storage like [IPFS](https://ipfs.io) and [Filecoin](https://filecoin.io), SSI needs to embrace tokens to be truly successful.

## The business model of SSI <a href="#f40d" id="f40d"></a>

Given SSI is targeting the world as a market, the potential for adoption and growth is colossal. We genuinely see token holders as being able to help get companies to adopt the paradigm and give data back to individuals whilst creating entirely new revenue streams. This will create a virtuous flywheel for self-sovereign identity growth, where:

* More issuing organisations are incentivised to give "back" trusted data to identity subjects. This will be data that belonged to or originated from identity subjects in the first place, but with the stamp of authority that the issuing organisation brings.
* With more SSI credentials in circulation, more organisations will accept SSI credentials as it is an easier, more efficient, and more secure way of getting trusted data with the consent of the identity subject.
* Growth in usage will attract more product companies (like cheqd) who build self-sovereign identity software across the stack, enrich features and functionality, and integrate SSI into their apps and services.
* As SSI credentials become more common, the genesis data needed to verify identity will become cheaper, lowering the cost structure for creating trusted data.
* Lower cost structures for creating trusted data will result in lower prices over time — than current, sometimes prohibitively expensive methods — for consuming verified identity data.
* Lower prices to consume trusted data for individuals and companies will provide a commercial driver to adoption.

## Marketing benefits <a href="#5cfc" id="5cfc"></a>

Less considered is the marketing benefit a token could have for SSI. Whilst companies are beginning to wake up to the possibilities, there is very little awareness amongst the general public. SSI has a tremendous community of passionate believers, but it has not cracked the public consciousness yet or broken materially out of the core supporters who have typically worked in the identity space previously.

A token provides a massive opportunity to broaden the audience. As a recent applicant said in an interview with us, "_My Dad can't switch on his computer but comes downstairs telling me about bitcoin market movements_".

Building public awareness will be key to having them drive adoption. Once they have experienced SSI in any area of their lives, they will demand it from any organisation they interact with. The parallels with neo-banks and the incumbent banks are strong here. Most neo-banks restructured their **Know Your Customer (KYC)** processes, moving from users filling in endless forms to be checked by an analyst to scan identity documents, leverage credit agency databases, and take quick selfies. This allowed them to provide KYC journeys in the order of minutes rather than days. That journey is now pervasive across banking and from car rental to coworking spaces, amongst others.

SSI will be the same; once someone experiences SSI, they will demand it of all their interactions.

As important, a token will provide a mechanism to being rewarded as the technology is adopted. There won't just be rewards for user experience and reclaiming privacy but also monetary rewards for and engaging with, supporting the ecosystem and encouraging adoption.

## Key takeaways <a href="#6b75" id="6b75"></a>

A token is undoubtedly needed to enable SSI to grow truly. Existing payment rails are not fit for purpose, especially on a global scale. It will also help SSI break into the public consciousness and further drive adoption.
