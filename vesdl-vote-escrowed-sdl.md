# veSDL (vote escrowed) SDL

## Definitions

- **SDL token** - transferable, used for incentives via emission&#x20;
- **Vote escrow SDL (veSDL)** - non-transferable, locked up by depositing SDL into the voting escrow contract, period from 1 week to 4 years&#x20;
- **Gauge** - the smart contract controlling how much SDL incentives are emitted to each pool; veSDL holders can vote which pool to allocate SDL incentives to on a weekly basis&#x20;
- **User checkpoint** - a user checkpoint in the veSDL mechanism is any time when you interact with veSDL: locking SDL (depositing into a gauge), unlocking SDL (withdrawing from a gauge) or claiming rewards.

## Summary&#x20;

### Introduction&#x20;

With the SDL token unlock comes the implementation of “vote escrow” tokenomics, step 1 in our tokenomics roadmap. But what does this change enable SDL holders to do?

Up until now, Saddle has incentivized LPs by offering SDL (and occasionally other partner) tokens as a reward for their deposited liquidity. But there’s a problem: token emission rates for these incentives are fixed. What if market conditions change? Enter veSDL.

### What is veSDL?

veSDL and gauges work together to give users a mechanism to vote for the pool to which they want SDL rewards allocated. Users can get veSDL by locking their SDL in the Vote Escrow contract from 1 week to 4 years. The longer the lock, the more veSDL and voting power they receive from locking each SDL

Instead of holders making a tradeoff between fixed, potentially higher SDL emissions and being LPs for tokens they like more, vote escrow tokenomics allows SDL holders to lock their SDL for a period of time for veSDL, or “vote escrowed” SDL. The longer they lock, the higher the veSDL:SDL exchange rate to incentivize long-term community participation. Once users have veSDL they can vote in weekly _gauge weight voting_.

<figure><img src=".gitbook/assets/SDL and veSDL_short-02(smaller res) (1).jpg" alt=""><figcaption><p>Difference between SDL and veSDL.</p></figcaption></figure>

### Gauge weight voting&#x20;

The weekly gauge weight vote determines how Saddle’s weekly SDL emissions get distributed in the following week. As outlined in [SIP-24](https://snapshot.org/#/saddlefinance.eth/proposal/0xe2a3e49dd86ef9f3e778486371b727b5e1ac8a1bc36326f431d5de63c8b287ca), **30M tokens of the SDL supply will be emitted over the first 6 months post token unlock**. That means 30M SDL / 6 months = 1.25m SDL will be emitted in liquidity mining incentives per week. After 6 months, a new Saddle Improvement Proposal will go to governance to change the weekly emissions rate to a tapering schedule.

This means that SDL users will be able to lock up their SDL for veSDL, vote in weekly gauge votes to determine where SDL incentives get emitted the following week, and collectively choose how attractive each pool is for the broader DeFi community.

### Boosts and trading fees&#x20;

When users lock up SDL, they also receive personal SDL emission boosts (i.e. “boosties”) for the pools they’re personally LPs for.

By default, all users (those without veSDL) get 1x the reward rate. Those with veSDL will receive a boost of 1-2.5x the base reward rate, based on the amount of veSDL the user has relative to their LP size.

Also note that users’ boosties are recalculated automatically every 2 weeks. Each individual's boost rate is recalculated any time they interact with a gauge or veSDL (i.e. user checkpoint)

Finally, recall that Saddle collects a 0.04% trading fee on most trades. 50% of the trading fee goes to liquidity providers in the form of whatever tokens they are providing. The other 50% gets divided in two ways: 60% goes to veSDL token holders in the form of a Sushiswap SDL/ETH LP token; the other 40% goes to Saddle's treasury in the form of USDC.

## Benefits

### **Boosties**&#x20;

When users lock up SDL for veSDL, the pools they’re providing liquidity to will benefit from boosted SDL emissions for that particular user.&#x20;

### **Weekly gauge weight voting**&#x20;

Every week the weights of the Saddle gauge go to vote. This controls the distribution of SDL liquidity mining incentives across all of Saddle’s pools included in the gauge system. veSDL holders are able to participate in this weekly vote to route SDL incentives to whichever pool they choose. This could be a pool they’re already a part of, or a pool they’re being bribed to support, resulting in additional rewards for veSDL holders.&#x20;

### **Voting on SIPs / governance proposals**&#x20;

Once veSDL goes live, all Snapshot voting will be transitioned from SDL held to veSDL held. Which means veSDL holders will have the benefit of being able to participate in Saddle’s governance and helping to direct the growth of the protocol&#x20;

### **Bribes**&#x20;

veSDL holders have the potential to receive airdrops from protocols whose tokens are part of Saddle’s liquidity pools in exchange for voting to increase the gauge weight of those pools those protocol’s token is a part of. Users benefit from airdrops in exchange for their votes, protocols benefit from there being added incentives for users to provide liquidity with their token. Everyone wins. Take a look at [pitch.money](https://pitch.money/) for an example.

## How-to-Guide

### How to lock/unlock SDL <> veSDL&#x20;

In order to maximize your SDL rewards for LPing (up to 2.5x!), you’ll need some veSDL. Head to the veSDL page on saddle.exchange to lock your SDL and receive veSDL.

#### To lock SDL into veSDL:

1. Input into SDL Lock section how much SDL you want to lock
2. Input into calendar how long you want to lock up your SDL for&#x20;
   - Minimum is 1 week (1 SDL locked for 1 week = 0.0048 veSDL)&#x20;
   - Maximum is 4 years (1 SDL locked for 4 years = 1 veSDL)
3. Click \[Create Lock] button, approve + execute transaction in your wallet&#x20;
   - If you already have some SDL locked, the UI will show \[Adjust Lock] button instead.&#x20;
   - In this case, you can add more SDL which will have the same unlock as your existing lock&#x20;
   - You can also increase the unlock time without adding more SDL
   - Depending on how much additional SDL you want to lock into veSDL, the UI will show how much additional veSDL you will receive.&#x20;
   - Note it is not possible to lock SDL for a shorter duration than your current veSDL lock duration

![](https://lh5.googleusercontent.com/Qc-DM7uFwIKqEW69u2oGy2Wvxk_9vnxyB2CmEmKQwW1hjrAxRn8AbvOwzGvxEC4ydkBhBzNRcQL3yhATMcFPZKTbW2NIQMLS5tGVpU8mjMQ09kUpLYXIZwT_w63kWSflm3cKy8HmycrN2VKEiA)

#### To unlock veSDL back into SDL:&#x20;

1. Go to veSDL Unlock section and click \[Unlock] button, approve + execute transaction in your wallet&#x20;
   - Note that unlocking veSDL before lockup expiry date will have a penalty. The amount is prorated linearly; so the closer you get to your unlock date, the smaller the penalty for unlocking early.

![](https://lh3.googleusercontent.com/HcPbhXTgF99TsbPF1sgMqEzHUHsm_ecK2KmfU7C_304ep3Da2oFt1Lz6pkSnByukH3elGwvR0Q2FUPbzcRVnSXgsgoOzRlFb8VtadUoIpjzK9xPph-mwjnXvM209FFTtL0dIbIsYaBCdGXjMag)

### How to calculate how much veSDL you need to max out reward boosts (boosties)&#x20;

The amount of veSDL you need to hold in order to max out SDL rewards will vary depending on a number of factors.&#x20;

The best way to max out your boosties is by using the veToken calculator.

1. Head to the veSDL page on saddle.exchange&#x20;
2. Click “veToken calculator” text at the end of the SDL Lock section

To calculate max boost (2.5x),&#x20;

1. Under Max boost calculator, select which pool to calculate for (see image below)&#x20;
2. Input how much liquidity you’re planning to deposit&#x20;
3. See results directly below&#x20;

To calculate your current boost&#x20;

1. Under My boost calculator, input your veSDL amount (if you have veSDL, it will be auto-populated with your veSDL holdings)&#x20;
2. See results directly below&#x20;

Note that the amount of veSDL needed to maintain maximum boost changes depending on pool size and amount of veSDL pool LPs hold. In order to maintain max boosties, we recommend locking 20-50% more SDL than what the Max boost calculator shows.

![](<.gitbook/assets/image (4).png>)

### How to vote in gauge for allocating SDL rewards&#x20;

As a veSDL holder, you have the power to vote on which Saddle pools will emit SDL incentives (and how much incentives) on a weekly basis.

For the first 6 months following launch of veSDL, a total of 30M SDL in incentives will be emitted. Your vote will help determine which pools those incentives are emitted to, and thus which pool LPs will receive more SDL for their contributions to pool liquidity. (Note that in the first week, SDL incentives will be distributed proportionally to each pool based on TVL on Mainnet. Pools on alt L1s and L2s will continue to emit rewards via MiniChef and will be added to the gauge system at a later date)

Voting is done via Snapshot, so it will be free / gasless!

To vote, simply head to the veSDL page on saddle.exchange, and under the Gauge Vote section, click the \[Vote] button for the current week. (Or head to [Saddle’s Snapshot](https://snapshot.org/#/saddlefinance.eth) directly to vote).

**First vote (for Week 2) will start on Friday 06/24/2022.**

![](https://lh3.googleusercontent.com/biKzFSWey8uy9nRRqIejvRCQVIo2aTE0e3iIJt8Advrz-6XOs_-HjS78UY9Y-upVd1bGAWSgRH-jMCp-_YpIOjC6rTNxTAlQ85EqOfLPJzglApCFqD7f31dqDUgg85cPrXjmovq8FhiYrW634A)

### Understanding your voting power (i.e. how much veSDL you’re actually holding) based on lock time

The longer you lock your assets, the stronger your voting power.&#x20;

The elements that influence your voting power are the amount of tokens locked and the period of time: simply put, your voting power = the quantity of SDL locked \* number of weeks locked. For example: Locking 1 SDLfor 4 years gives right to 1 veSDL; locking for 1 year equates to 0.25 veSDL; locking for 1 week equates to 0.0048 veSDL&#x20;

As a result, those who commit to holding veSDL for a longer period of time have more voting power (and boosties).&#x20;

Note that your voting power decays over time, so as your lock duration for SDL decreases, so does your voting power.

## veSDL FAQ

#### **When is the first vote? / When does SDL emissions start via the gauges?**&#x20;

The gauge will start SDL reward emissions on 06/23/2022 at 8PM EST.

First vote (for Week 2) will start the following day on 06/24/2022.

During the first week (06/23/2022 - 06/30/2022), \~63.5% of SDL emissions will be allocated proportionally to each Saddle pool based on TVL, on Mainnet only. Pools on alt L1s and L2s will continue to emit rewards via MiniChef and will be added to the gauge system at a later date. The remaining 36.5% of SDL emissions are allocated to the SDL/ETH SushiSwap gauge.

#### What is vote locking, vote escrow, or veSDL?

When you provide liquidity to Saddle, you earn part of the fees of the pool you provided liquidity to and SDL tokens as a bonus. This works as an incentive for providing liquidity.&#x20;

If you lock those SDL tokens you received – for a period that goes from 1 to 4 years – you receive a certain amount of veSDL – Vote Escrowed SDL.&#x20;

You can use veSDL to:&#x20;

- Boost your rewards in different SDL pools;&#x20;
- Get voting rights on which pool receives SDL emissions;&#x20;
- Vote on Snapshot on Saddle governance proposals.&#x20;

Moreover:&#x20;

- The longer the locking period, the greater the voting power of the hodler;&#x20;
- veSDL cannot be transferred – the only way you have to get veSDL is by locking SDL

#### What is the vote locking boost (boosties)?&#x20;

When you lock SDL, you also earn a boost on your provided liquidity – up to 2.5x. The goal of boosties is to incentivize users to participate in governance by rewarding them with a bigger share of the daily SDL inflation.

#### How are boosties calculated?&#x20;

There are a few factors the impact your reward boost: The quantity of SDL tokens locked – the higher the amount, the higher the reward; The locking period; Pool liquidity and your proportional ownership of LP tokens; Many factors impact how much veSDL you need to have locked to max out your reward boost for pools you’re LPing in: To calculate how much boost you currently have, see guide [here](vesdl-vote-escrowed-sdl.md#how-to-calculate-how-much-vesdl-you-need-to-max-out-reward-boosts-boosties).

#### How often does my veSDL voting power change?&#x20;

Your voting power decreases over time, but your boost will take notice of your decreasing voting power every 2 weeks and at user checkpoints. Everyone's boost rate is recalculated automatically every 2 weeks. Each individual's boost rate is also recalculated any time they interact with a gauge or veSDL (i.e. if there’s a user checkpoint).

#### How do boosties work if I LP in multiple Saddle pools?&#x20;

Depending on how much veSDL you hold, boosties are automatically applied to every Saddle pool you’re LPing for. However, depending on a number of other [factors](vesdl-vote-escrowed-sdl.md#how-are-boosties-calculated), you may need to lock up more SDL in order to maximize your rewards for the most competitive pools you’re LPing in.

#### Can I vote for multiple pools?&#x20;

Yes. For clarification:&#x20;

- Voting with veSDL -> determines which pool receives SDL reward emissions&#x20;
  - When use you use your veSDL to vote for a pool/gauge, you are determining which pool is receiving SDL reward allocations&#x20;
- Holding veSDL -> your LP in Saddle pools get boosted rewards&#x20;
  - Independently, based on how much veSDL you hold, your LP in Saddle pools will get boosted rewards automatically&#x20;

Note that voting doesn't remove or deplete your veSDL. You can both vote and get boosties with your full veSDL.

#### How do I get veSDL?&#x20;

Purchase SDL on SushiSwap if you don’t own any SDL, then visit the veSDL page at saddle.exchange/#/veSDL and lock your SDL to get veSDL. For more details, visit the guide on How to [lock/unlock SDL <> veSDL](vesdl-vote-escrowed-sdl.md#how-to-lock-unlock-sdl-less-than-greater-than-vesdl).

#### Can I buy, sell, or transfer veSDL?&#x20;

No, veSDL is non-transferrable. See previous FAQ for how to get veSDL.

#### How do I unlock my veSDL?&#x20;

Visit saddle.exchange/#/veSDL to unlock your veSDL:&#x20;

- Option 1: waiting until your vote lock expires and unlocking penalty-free&#x20;
- Option 2: unlock SDL whenever you want at the cost of paying a penalty.&#x20;
  - The penalty is calculated by taking the minimum between .75 and (time left until unlock) / 4 years.&#x20;
  - _For example if you have 2 year left on your lock, the penalty is min(.75, 1/2) = 0.5. So the penalty is 50%._&#x20;
  - Penalties are distributed to the remaining lockers pro-rata.

#### **How do I apply boosties?**&#x20;

If you are creating a new lock (i.e. locking SDL into veSDL for the first time), your boosties will be applied automatically.&#x20;

If you are adding to your lock (i.e. locking more SDL when you already hold veSDL), you’ll need a checkpoint action (i.e. any interaction with the gauge system counts; so claiming or depositing or withdrawing) in order to update your boost.&#x20;

- When you lock more SDL, it will not apply the boost on existing gauges automatically.&#x20;
- When you stake or withdraw LP tokens to/from a gauge it will apply the latest boost based on your veSDL and LP deposit size.&#x20;
- When you claim rewards, your boost value is based on prior veSDL balance when you last interacted with the gauge, but with current total LP supply in the gauge. Then it’ll update your boost based on current veSDL for future calls.&#x20;
- If you lock more SDL and don’t claim, you will maintain the initial boost. However, by the time you claim, the total reward rate may have been reduced (rate reduction is possible every 2 weeks). Claiming will use the latest reward rate with prior boost value. Thus you may receive less overall compared to claiming every 2 weeks.

[Click here](vesdl-vote-escrowed-sdl.md#how-to-guide) for a guide on how locking and boosting your SDL rewards works.

#### Will users that hold veSDL on other chains be able to participate in governance?&#x20;

SDL can only be locked into veSDL on mainnet and is non-transferable once locked. Users holding SDL on other chains will need to bridge to mainnet to lock and participate in governance.
