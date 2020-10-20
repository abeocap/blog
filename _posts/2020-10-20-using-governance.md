---
layout: post
title: Using Governance
---

In this post we'll explore how to use Cap's governance contracts to submit proposals that can be voted on by CAP holders.

Proposals are executable code that can be used to register new assets, update parameters, and upgrade the system in pretty much any way imaginable.

Cap has been fully deployed on Ropsten. To interact with the governance contract, use Etherscan [Read as Proxy](https://ropsten.etherscan.io/address/0x5a037422532492e8a69b5afbffc21c68a9c4031e#readProxyContract) to make contract calls and [Write as Proxy](https://ropsten.etherscan.io/address/0x5a037422532492e8a69b5afbffc21c68a9c4031e#writeProxyContract) to send transactions.

You'll need to connect your Ethereum web wallet (e.g. Metamask) and get some ETH and CAP on Ropsten:

* ETH: [https://faucet.metamask.io/](https://faucet.metamask.io/). You'll need these to fund transactions with gas.
* CAP: Use the [Faucet Request](https://ropsten.etherscan.io/address/0x755d13Fd88B238fC6F585a67c54aDbd88133bb5C#writeProxyContract) method. You'll need these to cast votes on proposals.

### Submit a proposal

The easiest way to submit a new proposal is to use the scripts in the governance code repo. Eventually, someone will build a UI for this to make it more end-user friendly.

Start by cloning the repo:

`git clone git@github.com:capfina/governance.git`

then

```
# make sure you're using node 12
nvm use

# npm install
npm i
```

You're now ready to submit a new proposal, formatted as a JSON file:

```
{
	"title": "Example Title",
	"description": "Example Description",
	"discoverabilityPeriod": "1",
	"transactions": []
}
```

In this example, we'll submit a proposal to register two new assets on Cap: TSLA (Tesla stock) and NFLX (Netflix stock), with a max amount per trade of 50,000 DAI and a total outstanding supply worth 5,000,000 DAI.

```
{
  title: 'Register Asset',
  description: 'registers asset',
  discoverabilityPeriod: '1',
  transactions: [
    {
      type: 'method',
      contract: '0x75C764B7A673e2877eA3178E63B958dD67eCFab4',
      method: 'registerAsset',
      params: [
        { name: 'name', type: 'string', value: 'Tesla' },
        { name: 'symbol', type: 'string', value: 'TSLA' },
        { name: 'maxAmount', type: 'uint256', value: '50000000000000000000000' },
        { name: 'maxSupply', type: 'uint256', value: '5000000000000000000000000' }
      ]
    },
    {
      type: 'method',
      contract: '0x75C764B7A673e2877eA3178E63B958dD67eCFab4',
      method: 'registerAsset',
      params: [
        { name: 'name', type: 'string', value: 'Netflix' },
        { name: 'symbol', type: 'string', value: 'NLFX' },
        { name: 'maxAmount', type: 'uint256', value: '50000000000000000000000' },
        { name: 'maxSupply', type: 'uint256', value: '5000000000000000000000000' }
      ]
    }
  ]
}
```

Save the above into a .json file. Then run

`./scripts/submit-proposal.js <path_to_json_proposal_file>`

Your proposal has now been submitted! People will soon be able to vote on it.

### Vote

To vote on a proposal, go to the governance contract's [Etherscan page](https://ropsten.etherscan.io/address/0x5a037422532492e8a69b5afbffc21c68a9c4031e#writeProxyContract).

If you haven't yet staked your CAP, use the stakeToVote method to do so. Staked CAP are locked during voting, and will remain so until you call the releaseStaked method.

Once your CAP have been staked, use the castVote method with the proposalId you're voting on (this is provided when you submit the proposal) along with your support, which should be `true` (for) or `false` (against).

Your vote is now counted!

Once the voting period is over, the proposal is either cancelled (if not enough people support it) or becomes executable.

### Executing a proposal

A proposal that receives more for votes than against votes, and a total of more than 4,000 votes, becomes executable.

Anyone can execute it by using the executeProposal method on the [governance contract](https://ropsten.etherscan.io/address/0x5a037422532492e8a69b5afbffc21c68a9c4031e#writeProxyContract). Enter 0 as payableAmount and the proposalId.

That's it! Your proposed changes are now active in the system.

### Feedback

Questions or feedback? Let us know on [Telegram](https://t.me/capfin).