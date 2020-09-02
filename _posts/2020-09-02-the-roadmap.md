---
layout: post
title: The Roadmap
---

This post lays out a 10 year roadmap for Cap. Our goal is to build open, decentralized financial services with CAP as the native token.

We consider this to be such an important mission because of its huge disruptive potential. For the first time in history, we have the opportunity to build unstoppable financial services governed by fair and open rules, as opposed to the current centralized and opaque financial system that underpins almost every aspect of our society.

Here's what we plan to do to achieve that vision.

### Perpetuals

The Cap ecosystem starts with [Cap Perpetuals](https://cap.finance), which we launched in August.

Perpetuals let you open leveraged long or short positions on certain markets using stablecoins such as DAI. Profits are backed by the Cap Liquidity Pool (CLP), which in turn receives trader losses. Yield generated by the CLP is used to buy back CAP.

The current iteration of Perpetuals is semi-decentralized. Things like price feeds and liquidations are managed by our server to ensure speed and predictability of execution. We believe that a semi-decentralized form of the Perpetuals product will be desirable for the foreseeable future, particularly for traders who are speed-sensitive.

A fully decentralized Perpetuals design is possible and planned. Price feeds are provided by independent oracles while liquidations are monitored and managed by anyone willing to do so in exchange for a fee. This design is not trivial and issues like oracle front-running, which can result in riskless profit, as well as informed trading flow, which can drain the CLP, will need to be dealt with accordingly.

Perpetuals generate sustainable revenue that allows us to go after higher risk markets as described below.

### Synthetics

Synthetics are crypto-backed instruments that track the value of an underlying asset, like a stock. They let you gain exposure to an asset without needing to own it, and without interacting with the traditional financial system, saving time and money.

Cap Synthetics are non-leveraged, withdrawable ERC-20 tokens that you can purchase using stablecoins. They are backed by the CLP and their price is determined by oracle feeds.

To purchase a synthetic, you send an amount of stablecoins to our Synthetics contract. The contract determines the price of the asset you're trying to buy based on its oracle feed and mints the equivalent amount of tokens to your address.

To sell a synthetic, you send your asset tokens to our Synthetics contract, which determines the amount of stablecoins to send to you based on the oracle feed. The tokens you send are then burned.

We plan to release a proof of concept for our Synthetics product some time in September. The goal is end-to-end decentralization. The backend logic is executed entirely in smart contracts and client side code is hosted on IPFS, accessible through an unstoppable .crypto domain.

### Exchange

A token exchange will be part of the Cap ecosystem. It will be decentralized and function similarly to Uniswap, with a few differences, including a more efficient market maker based on our technical whitepaper.

In short, Cap Exchange will have a market maker that will adapt its liquidity curve based on the type of assets being exchanged. For example, a volatile asset pair would have a more sensitive spread than a non volatile one, resulting in a superior experience for traders while protecting liquidity providers.

### Lending

Lending and borrowing are the pillars of the current financial system. Several protocols today operate overcollateralized lending on Ethereum, but we believe a much larger market exists in undercollateralized lending coupled with credit (reputation) and identity. 

Cap Lending will be built in conjunction with a decentralized reputation system that will allow lenders to evaluate borrowers from a risk perspective on a case by case basis. Decentralized, unsecured lending is not trivial but we believe we've come up with a design to make it work.

### More

Several other services will also be built under the Cap umbrella. Those include staking, asset management, prediction markets, identity, insurance, and gaming. Admittedly, many of the implementation details for these products are still TBD, but we trust we will figure them out in due time.

We also plan to build traditional infrastructure services that interact directly with smart contracts on the blockchain, including oracles, to support Cap's smart contracts without needing to rely on and pay for an external third party in the long run. Cap Oracles will be an independently run entity.

CAP is the native token underpinning the entire ecosystem. CAP holders will not only be entitled to the global yield generated by the system, but they will also be able to vote on system parameters and asset offerings, among other things. The point of Cap is to create a financial system governed by its users and the CAP token makes that possible.

Cap's values are:

* simplicity
* security
* transparency

We plan to build out Cap with those values in mind. Focusing on the core features that matter to most users. Continuously engaging with the community in a transparent manner. Getting high-impact smart contracts audited by competent third parties prior to wide usage. And more.

Cap is community driven. Join us on [Telegram](https://t.me/capfin).

