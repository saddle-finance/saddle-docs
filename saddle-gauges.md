---
description: Explanation of useage and purpose of Saddle gauges
---

# Saddle Liquidity Gauges

The liquidity gauge system manages the distribution of rewards to liquidity providers based on user voting through Saddle voting escrow. Each pool will have its own liquidity gauge. Rewards will be distributed to users in proportion to how many LP tokens are locked. Holders of the veSDL token can vote on reward allocation through a weekly snapshot vote. This vote determines the weight of rewards on a per-pool basis. The veSDL token is given to users who lock their $SDL tokens for a set lock period into the Saddle protocol. In addition to gauge weight voting, users can lock their veSDL to recieve a boost in the rewards on their LP positions. By default gauge rewards will give out SDL but in the future this will also include gauge/pool specfic rewards.

## **SDL Holders**

_**Locking SDL**:_ A holder of $SDL can lock their token balance and recieve an amount of veSDL in proportion to the length of this lock. This is the Saddle vote escrowed token which allows one to vote on liquidity gauge reward weights through snapshot. Unlocking can be done at any point, however doing so before the lock is complete will result in a penalty to the $SDL balance in proportion to how much time of the lock there was left.

_**Boosting Gauge Rewards**:_ Locking $SDL is incentivised for liquidity providers as their recieved rewards of their lp positions will be **boosted** (up to 2.5x) depending on their held amount of veSDL. To determine the amount of SDL one must lock to receieve this maxmium boost a calculator such as [this one](https://dao.curve.fi/minter/calc) can be used. The amount needed to acheive this reward multiplier will scale with the amount of veSDL locked in the contract, so users will have to monitor their needed balance of locked tokens to recieve their desired boost every week.

## **veSDL Holders**

_**Snapshot Voting**:_ Users can use their veSDL balance to vote to participate in the weekly snapshot vote to determine the weight of rewards distributed to. One can allocate their vote to one or more liquidity gauges.

_**Vote Delegation**:_ Holders of veSDL will have the option to delegate their token balance to another address to handle the voting process for them. In the future this will enable a bribe system.

