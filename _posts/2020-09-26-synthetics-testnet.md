---
layout: post
title: Synthetics testnet
---

Today we're launching the Cap Synthetics testnet: [https://synthetics.cap.finance].

Synthetics lets you buy and sell assets, like stocks, using stablecoins. We're launching on the Ropsten testnet with DAI as the stablecoin and AAPL as the asset.

### Usage

Before starting, make sure you have some testnet ETH in your wallet. You can get those from the [Metamask faucet](https://faucet.metamask.io/).

Then, you want to get some testnet DAI. After connecting your Metamask wallet and setting your network to Ropsten, click on "faucet" to get 10,000 DAI.

Next, set an amount you want to buy, say 300 DAI worth of AAPL. Click on Submit then approve your transaction in Metamask.

Your order will be queued. Our oracles will pick it up for processing within a couple of minutes. If the market is closed (for example on weekends for stocks) your order will likely remain in the queue until the market opens.

Once your order is processed, AAPL tokens will appear in your account. To see your AAPL token balance in Metamask, click on the address hash next to "Account (AAPL)".

You just bought AAPL with DAI in a completely decentralized manner. 

You can now transfer your AAPL tokens to any Ethereum address or sell them back at a later time.

### IPFS

The Cap Synthetics client is hosted on IPFS, a decentralized content network, and communicates exclusively with on-chain contracts. It can be accessed by anyone in a decentralized manner. synthetics.cap.finance is a convenient subdomain set up to point to the IPFS content.

### Open-source

Our Synthetics product is open-source:

* Client: https://github.com/capfina/synthetics-client
* Contracts: https://github.com/capfina/synthetics
* Oracle contracts: https://github.com/capfina/oracle

### Feedback

We expect to run the Synthetics testnet for a few weeks, ironing out potential bugs and expanding the asset offering, before migrating to mainnet. If you use the Synthetics testnet, we'd appreciate your feedback. Join us on [Telegram](https://t.me/capfin).