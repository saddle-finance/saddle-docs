---
description: SDL is the Saddle DAO governance token.
---

# SDL Token

Saddle has served as community and a developer first infrastructure entirely embracing open-source collaboration since our launch in Jan 2021. We are here today because of the many community members and liquidity providers who supported our journey over the past year.

As the Saddle protocol grows and develops, DAO governance is our next step in our community and LPs outreach.

**SDL is the Saddle DAO governance token.**

{% hint style="info" %}
Find SDL token code [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/SDL.sol) &#x20;
{% endhint %}

### **SDL ALLOCATION** <a href="#_toc87947029" id="_toc87947029"></a>

The max supply of 1 billion SDL has been minted at genesis and will become available over the course of 3 years. We split the initial SDL allocation between:

| **Allocation**           | **% of Tokens** | **# of Tokens** | **Vesting Period**                       |
| ------------------------ | --------------- | --------------- | ---------------------------------------- |
| Saddle community members | 51%             | 510,000,000 SDL | _See breakdown in the following section_ |
| Investors                | 22.5%           | 225,000,000 SDL | 2 years                                  |
| Team members             | 25.9%           | 259,000,000 SDL | 3 years                                  |
| Advisors                 | 0.6%            | 6,000,000 SDL   | 3 years                                  |

![SDL Token Allocation](<.gitbook/assets/0 (1)>)

{% hint style="info" %}
Find SDL token vesting code [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/Vesting.sol) and [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/RetroactiveVesting.sol)
{% endhint %}

### **SDL Community Token Allocation** <a href="#_toc87947030" id="_toc87947030"></a>

The Saddle community tokens (510,000,000 SDL) are further allocated as per the schedule below:

| **Allocation**                                                | **% of Tokens** | **# of Tokens**   | **Vesting Period** |     |
| ------------------------------------------------------------- | --------------- | ----------------- | ------------------ | --- |
| 1) Past liquidity providers and users, as distributed below:  | 15%             | 150,000,000 SDL   | 2 years            |     |
| _1.1) Historical LPs_                                         | _10.5%_         | _105,000,000 SDL_ | _2 years_          |     |
| _1.2) veCRV Holders_                                          | _3_%            | _30,000,000 SDL_  | _2 years_          |     |
| _1.3) Any address that swapped $100> using Saddle contracts_  | _0.5%_          | _5,000,000 SDL_   | _2 years_          |     |
| _1.4) Multisig signers_                                       | _0.5%_          | _5,000,000 SDL_   | _2 years_          |     |
| _1.5) Early depositors_                                       | _0.5%_          | _5,000,000 SDL_   | _2 years_          |     |
| 2) Liquidity mining                                           | 5%              | 50,000,000 SDL    | No vesting         |     |
| 3) Community incentives program (bounties4bandits) and grants | 1%              | 10,000,000 SDL    | No vesting         |     |
| 4) Governance treasury                                        | 30%             | 200,000,000 SDL   | 3 years            |     |

15% of SDL (150,000,000 SDL) can be claimed by past liquidity providers and users with 2-year vesting. This is broken down as follows:

- 10.5% pro rata to historical liquidity providers (105,000,000 SDL)
  - Cut-off date is 11/1/21
  - Tokens were distributed per block to historical liquidity providers by accounting for provided liquidity amounts in dollars as a percent of total TVL
  - Rewards were doubled during the one month [guarded launch period](https://docs.saddle.finance/saddle-faq#what-is-saddles-proof-of-governance)
- 3% split evenly across veCRV holders (30,000,000 SDL) as a token of thanks for the StableSwap maths (using the latest [EPS snapshot](https://github.com/ellipsis-finance/vecrv-airdrop/blob/master/distributions/distribution-2021-10-28.json))
- 0.5% split evenly across each address that has ever swapped using Saddle contracts (5,000,000 SDL)
  - Cutoff date is 10/1/21 (any addresses swapping with any Saddle contract before then is eligible)
  - Addresses swapping less than a total of $100 are excluded to prevent sybils
- 0.5% split evenly across multisig signers (5,000,000 SDL)
- 0.5% pro rata to early depositors - we’d like to appreciate and compensate these community members, a few of whom took risks and lost value.

The token is initially **non-transferable for a period of between 3 to 12 months**. After 3 months, governance may vote to enable transfers. After 12 months, they may be enabled by anyone. The token and vesting contracts have been audited by [Quantstamp](https://quantstamp.com), read the audit [here](https://github.com/saddle-finance/saddle-audits/blob/master/10-27-2021_Quantstamp_Token.pdf).

We are launching SDL as non-transferrable to allow community members to earn more and deter short-term profit-seekers and mercenaries.

All historical users and liquidity providers can claim their SDL now on [the Saddle dApp](http://saddle.exchange).

### **EARNING SDL TOKENS** <a href="#_toc87947031" id="_toc87947031"></a>

You can earn the Saddle tokens in 2 ways – by LPing in Saddle’s incentivized pools and by participating in the bounties4bandits (b4b) program.

### **Liquidity Mining** <a href="#_toc87947032" id="_toc87947032"></a>

5% of SDL (50,000,000 SDL) has been allocated to liquidity mining programs across [Ethereum](https://ethereum.org/en/), [Arbitrum](https://offchainlabs.com), and (later) [Optimism](https://www.optimism.io) which can be earned without any vesting. The initial liquidity mining program will run for 6 months and 2.23% (22,300,000 SDL) will be distributed as follows:

| **Pool**      | **Network**     | **% of Tokens** | **# of Tokens** |
| ------------- | --------------- | --------------- | --------------- |
| alETH         | Ethereum        | 0.50%           | 4,958,678       |
| BTC V2        | Ethereum        | 0.25%           | 2,479,339       |
| D4            | Ethereum        | 0.25%           | 2,479,339       |
| Stablecoin V2 | Ethereum        | 0.25%           | 2,479,339       |
| Stablecoin    | Arbitrum (L2)   | 0.50%           | 4,958,678       |
| _Stablecoin_  | _Optimism (L2)_ | _0.50%_         | _4,958,678_     |

Liquidity mining will begin on 11/18/21 12:00 AM UTC. The remaining 3.75% of tokens have been earmarked for future pools, to be decided upon by the community. Specific information on SDL incentives for each pool is available on the [Pools page on the dApp](https://saddle.exchange/#/pools).

### **bounties4bandits (b4b) Community Incentives Program** <a href="#_toc87947033" id="_toc87947033"></a>

0.75% (7,500,000 SDL) is allocated with no vesting to a community multisig for grants for community contributions through [bounties4bandits (b4b)](https://saddle.finance/#/b4b), a program run by our community members in collaboration with [Encode Club](https://www.encode.club). Encode Club is receiving a 0.25% grant over three years for their continued support.

\
b4b is Saddle’s hackathon / grants program for Saddle community members to get involved and get rewarded, with several technical and non-technical tracks. Learn more about b4b [here](https://saddle.finance/#/b4b).

### **GOVERNANCE TREASURY** <a href="#_toc87947034" id="_toc87947034"></a>

The remaining 30% of tokens (300,000,000 SDL) will vest to the governance treasury over 3 years. The community will decide how to distribute these tokens going forward through community initiatives, liquidity mining, and other programs.

![Governance Treasury](.gitbook/assets/1)

### **GOVERNANCE** <a href="#_toc87947035" id="_toc87947035"></a>

SDL token holders can vote on proposals. Initially, the proposals will be on [Snapshot](https://snapshot.org), which the current [community multisig](https://docs.saddle.finance/saddle-faq#who-controls-saddles-admin-keys) will then enact. [Discourse](https://www.saddle.community) will be the platform for discussion of the proposals.

We expect proposals in the next few months to migrate to fully on-chain governance using the [Compound Governor Bravo](https://compound.finance) and add additional token economics.

Sign up for an account on the [Saddle community Discourse](https://www.saddle.community) to participate in protocol governance.

---
