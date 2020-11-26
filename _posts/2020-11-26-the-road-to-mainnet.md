---
layout: post
title: The Road to Mainnet
---

Today we're excited to announce that Cap's final product iteration, decentralized regular and leveraged synthetic trading, is now on Ropsten.

Over the last few weeks we rebuilt fundamental parts of Cap's trading system to accommodate high leverage and various optimizations resulting in much cheaper gas fees. In this post we'll explore Cap's trading system as well as the oracle network that supports it. 

Let's start by submitting our first leveraged trade on the Ropsten testnet.

### Leveraged trading

We deployed a proof of concept UI to interact with Cap's new Ropsten contracts at [cap.eth.link](http://cap.eth.link). This client is hosted on IPFS and linked to an ENS domain.

Start by connecting your Metamask wallet. Make sure Ropsten is selected as the network to use.

If you don't have any Ropsten ETH yet, get some [here](https://faucet.dimensions.network/) or [here](https://faucet.metamask.io/). You'll need these to pay for gas.

Click on faucet in the UI to request some testnet DAI. Make sure to refresh your page after the faucet transaction is confirmed (this will be automated in later client updates). You should see 10000 DAI in your balance.

You're now ready to submit an order. As of this writing, Cap on testnet only supports BTC as a product. Governance can register new products for trading at any time.

Click on Long or Short, then type in BTC. Once the product is found, choose a margin amount (minimum 10 DAI) and leverage (up to 100). Say you set 200 margin at 50x leverage. That's a 200*50 = 10000 DAI position.

Click on Submit Order. If this is your first time submitting an order, the system will ask you to permit spending of your DAI. Once approved, you can then submit the actual trade.

Refresh your Positions and Events panels over the next minute or so. Your order should be submitted, and once the oracle network picks it up, it will show up in your open Positions.

You can then add margin to your position, or partially or fully close your position to take profit or losses.

Cap uses an isolated margin system, meaning the margin and profits and losses tied into one position have no effect on any other position, and a position's liquidation price is known ahead of time. It also means you can add margin to an individual position and adjust your leverage as you see fit.

### Liquidation

The fundamental challenge in designing a decentralized leveraged trading system is the concept of liquidation. Liquidation is the process of force closing positions that have lost more than their margin can cover.

In a decentralized system, it's difficult to monitor position profits and losses across the board, which makes it near impossible to determine which positions need liquidating. And since there's no centralized server, that means there's no centralized actor to trigger liquidation on the positions that need it.

Cap's system lets anybody act as a liquidator for any position. In exchange for successfully liquidating a position, a liquidator receives 10% of the margin tied up in that position. This liquidator reward, like almost every other aspect of the system, is adjustable by community governance.

### Non-leveraged trading

Click on Regular to enable non-leveraged synthetic trading. This is similar to how Cap worked prior to this update. You can buy or sell actual ERC-20 synthetic tokens with DAI, and withdraw them to your own wallet, or use them in other DeFi systems.

### Oracle network

When an order is submitted to Cap's contracts, it is picked up within a block or two by the oracle network. The oracle network provides a price for the order which is then executed in Cap's contracts.

The oracle network is a trusted, geographically distributed, redundant system (similar to Chainlink) that monitors pending orders in Cap's contracts and responds with real-time market prices.

To submit prices to Cap's smart contracts, the oracle network must pay gas since it is changing the blockchain's state. This gas is funded automatically by the CLP up to a set amount per year.

The oracle network can process up to 20 orders per block and currently supports real-time pricing for tens of thousands of global assets.

### Gas prices

One of the major innovations in Cap's new trading system is its low gas costs. Here's the gas consumption breakdown for some core features:

* Submit non-leveraged order, with DAI permit (once): 217586
* Submit non-leveraged order, without DAI permit (every other time): 162288
* Submit leveraged order, with DAI permit (once): 216882
* Submit leveraged order, without DAI permit (every other time): 161391

At current ETH prices this translates to $3-$5 per order, which is 70%+ cheaper than most other crypto synthetic protocols out there.

### CAP buyback and burn

CAP benefits from continuous upward pressure in price thanks to a buyback program backed by the Cap Liquidity Pool, which collects losses from and pays out profits to traders.

10% of CLP funds on a yearly basis are used to buy back and burn CAP on the CAP/DAI market on Uniswap. This figure represents the approximate excess liquidity and can be adjusted by governance at any time through a proposal.

buyBackAndBurn() is a CLP contract method that can be called by anyone at any time. It will automatically determine the amount of CAP to buy based on the last time it was called and the funds currently available in the CLP.

### Mainnet in sight

Over the next few weeks, we, along with the Cap community, will be using, testing, and improving Cap's trading system. Securing the contracts and improving the client UI experience are high priorities.

We hope to reach a high enough system fidelity level sometime in December, which would enable mainnet deployment.

### Feedback

Questions or feedback? Let us know on [Telegram](https://t.me/capfin).