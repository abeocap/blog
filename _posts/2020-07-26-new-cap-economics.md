---
layout: post
title: New CAP Economics
---

This post may be obsolete. Please check the latest blog post or our [Telegram](https://t.me/capfin).

---

A new token economic model for Cap is proposed below. It is based on [Telegram](https://t.me/capfin) conversations among community members.

### Summary

Only **100 CAP** are minted every week.
* 40 CAP are sold to raise funds for the Cap Liquidity Pool (CLP)
* 20 CAP are distributed to stakers
* 20 CAP are distributed as volume incentives to traders
* 20 CAP go to the team

Excess CLP liquidity (which includes yield) is used to buy back and burn CAP.

This model applies positive pressure on CAP in three ways:
* scarcity (low inflation)
* staking (lock up CAP in exchange for rewards)
* buyback and burn (use yield to increase price and reduce supply)

![](/assets/images/cap-flow.png)

### New Minting Schedule

100,000 CAP have already been minted and in large part bought up by the community. 9.9M CAP remain unminted. Of those:

* 9,600,000 CAP are minted gradually at a fixed rate of 100 CAP per week for 96,000 weeks (approx. 1,840 years). The last CAP is minted in the year 3860.

* 300,000 CAP are reserved for special incentives, onboarding strategic partners, and emergency use. These remain unminted unless a good use is found, at the team's discretion or through voting by CAP holders.

### Weekly Sale

40 CAP are sold on a first-come first-served basis every Sunday at 00:00 UTC. The price for each CAP is fixed at the prevailing market rate at that time, with no slippage or fees to buy.

Proceeds from the sale are transferred to the CLP. The sale lasts for a maximum of 1 hour and any unsold CAP are burned.

### Staking

20 CAP are distributed to stakers. The lockup period is 30 days, after which you can withdraw your CAP (plus rewards) during a 12-hour window, after which a new 30-day lockup period begins, and so on.

Rewards are distributed based on your share of the staking pool. If you have 10 CAP staked and there are 100 CAP in the staking pool, your share of the pool is 10% and you receive 20 CAP x 10% = 2 CAP in weekly rewards.

A share multiplier exists that gradually increases during your first 180 days of staking. For the first lockup period, it is equal to 1. For the second, it is 1.1. For the third, 1.2. And so on until it reaches 1.5 for the sixth lockup period. It remains at 1.5 for any staking beyond the first 180 days.

### Volume Incentive

20 CAP are distributed to traders. Traders are the source of all yield, so it's important to incentivize them correctly.

Rewards are distributed based on your share of the total trading volume. If your trading volume for a given week is $1M and the total volume is $10M, then you receive 10% of the volume incentive, i.e. 20 CAP x 10% = 2 CAP.

### Buyback and Burn

Excess liquidity in the CLP is used to buy back and burn CAP. This occurs every Wednesday at 00:00 UTC.

Excess liquidity is defined as any amount in the CLP above 25% of the average weekly Open Interest. Excess liquidity includes yield but also any funds raised that are not needed to cover expected trader returns.

If there is no excess liquidity available, no buyback occurs.

### Socialized Profit Correction

The biggest risk for the CLP is informed traders. An insider on a given stock can make large profits at the expense of LPs, essentially draining the pool. Since Cap is (eventually) fully decentralized and anonymous, there is no way to detect this behavior or limit trade size.

To address such scenarios, we're introducing Socialized Profit Correction (SPC) which is a mechanism to protect LPs in case of outsized profit taking by traders. SPC sets the maximum daily drawdown on the CLP at 10%. Any loss beyond that is socialized by adjusting profits made by winning traders.

As an example, let's say the CLP size is $1M and traders make +$105,000 in aggregate return on a given day. That is $5,000 beyond the CLP's maximum drawdown. A trader who makes $1,050 on that day (representing 1% of the total profit) sees their profit adjusted by 1% x $5,000 = $50. Their settled profit for the day becomes $1,000 instead of $1,050.

### Feedback

You can discuss this proposal on [Telegram](https://t.me/capfin). Figures relating to staking, buybacks, and more will be tuned over time until the right balance of incentives is found.