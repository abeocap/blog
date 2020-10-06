---
layout: post
title: The Path Forward
---

This post lays out the path forward for Cap. We decided on the following after much thought on system dynamics, incentives, and legal implications. We believe we've reached a system design that is robust, reliable, and timeless, as described below.

### CAP Token Burn

First we'd like to announce that we will be minting and burning 9.9 million CAP tokens. This will reduce the total CAP supply to 100K which will be the final number.

No CAP tokens will be allocated to the team. We believe the team is a weak link in a system whose goal is to live forever — more on that below.

After the burn, no CAP will ever be minted again, and the only way to own CAP would be to buy it from someone else, for example on the CAP/ETH Uniswap pool.

### Sunsetting Perpetuals

We will not be proceeding with the public launch of Perpetuals at this time. The Perpetuals system design relies partly on centralized infrastructure that we control, which makes it prone to censorship. 

In light of events that occurred in the past couple of weeks and with our intent to remain legally compliant in all jurisdictions where Perpetuals may be accessed, we've made the decision to pause the launch.

Perpetuals Beta will remain available to anyone who already has access, although deposits will no longer be accepted. If you still have funds on Perpetuals Beta, we encourage you to request a withdrawal. You can always reach out to our team on Telegram for assistance.

### Synthetics

Sunsetting Perpetuals allows us to focus fully on Synthetics. Our goal for Synthetics is to create indestructible trading infrastructure that people can rely on forever. To get there, we need to remove the largest point of failure from the system: our team. That means developing an open protocol with community governance.

We already have a first version of Synthetics deployed on testnet that lets you buy and sell AAPL tokens with DAI. While incredibly exciting, it is not enough. Several elements of the system can still be censored: our domain name (cap.finance) and the oracle server that is providing price feeds for synthetic assets (it is centralized).

We've recently settled on a system design that mitigates these weak links, effectively resulting in an open, unstoppable synthetic trading protocol.

We'll be deploying elements of this system as additions to the current system running on testnet over the next few weeks. Once tested and audited, we will move the system to the Ethereum mainnet.

Here's an overview:

* Trade execution occurs entirely on chain and clients interact directly with smart contracts.
* DAI, an algorithmic, censorship-resistant stablecoin, will serve as the base currency for the system.
* Prices for synthetics will be made available through an oracle network that anyone can participate in by staking some DAI. By design, front-running is impossible. Oracles are rewarded for providing accurate prices and good dispute behavior with a portion of excess liquidity from the Cap Liquidity Pool (CLP).
* As a CAP holder, you can vote and submit proposals to update system fees, maximum trade amounts, and more, as well as register new assets for trading and ban malicious oracle nodes. Cap's governance design is very similar to Compound's.
* CAP holders receive a portion of excess liquidity from the CLP through a buyback and burn mechanism of CAP on Uniswap, occurring on a weekly basis.
* The front-end client is hosted on IPFS and served through an eth.link or IPNS domain (not cap.finance).

We're proud to introduce this system which enables full community control and governance of Cap, without needing to rely on, or even requiring, a team.

We'll be releasing more details on this soon. Stay tuned!

If you have any questions or feedback, we'd love to hear from you on [Telegram](https://t.me/capfin).

