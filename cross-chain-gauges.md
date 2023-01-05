---
description: >-
  Cross chain gauges are a set of contracts that enable bridging of SDL from the
  mainnet to corresponding sidechains for liquidity incentivization purposes.
---

# Cross Chain Gauges

### What are Cross Chain Gauges?

* Cross chain gauges are a set of contracts that enable bridging of SDL from the mainnet to corresponding sidechains for liquidity incentivization purposes
  * This is based on the voting data and veSDL balance from the mainnet.&#x20;
  * The use of cross chain gauges allows Saddle to combine all sidechain/L2 rewards into the same gauge voting mechanism currently used on the mainnet.
  * Cross chain gauges work in pairs of RootGauge/ChildGauge contracts.&#x20;
    * A RootGauge contract on the mainnet has the same address as a ChildGauge contract on a sidechain.&#x20;
    * Users stake sidechain LP tokens via the ChildGauge on a sidechain, and then vote for the corresponding RootGauge on the mainnet.

### What are the benefits of Cross Chain Gauges?

* For the protocol:
  * Easier tracking of rewards. Retire minichefs.
  * Rewards are automatically bridged whenever they are needed. Less management required.
* For our users:
  * No more Snapshot votes for minichef weights.
  * Users will be able to vote on Mainnet with their veSDL balance and their vote carries over. (Same benefit of on-chain gauge voting.)

### Cross Chain Gauges – Risks

* What are the risks of using Cross Chain Gauges?
  * The system is dependent on the associated bridges for each chain. If a bridge becomes unavailable, the admin can take action to prevent issues.
* What are some preventative measures in place in case of exploits?
  * There is a 7-day buffer period per every epoch during which the admin (saddle multisig) can take action to prevent any issues before distribution of SDL is started.
* Some contracts are not fully audited.&#x20;
  * ArbitrumBridger.sol, OptimismBridger.sol
    * Logic using respective official bridges for bridging to each network.
  * ChildOracle.sol
    * Receives and stores veSDL user data on each side chain
  * RootOracle.sol
    * Pushes veSDL user data to each side chain
  * AnyCallTranslator.sol
    * Responsible for talking to AnyCallv6
  * RewardForwarder.sol
    * Permissionless external reward forwarder for gauges
* How can I stay safe when using Cross Chain Gauges?
  * When voting for a RootGauge/ChildGauge, be sure to double check the name and/or address to ensure you are voting for the correct gauge. This will help prevent any potential errors or misunderstandings.
  * If you notice any irregular distribution/bridging, please reach out to us on Discord.

### Cross Chain Gauges – How-To

*   How do I stake my LP tokens in a gauge on a side chain?

    * Via Farms page or within each pool’s deposit/withdraw page.

    <figure><img src="https://lh6.googleusercontent.com/PDUZYowvkZPKqdT8im6lQxSAoz83Kd3cMg5AmzxZR6nA7qgoQ_9siu7V80FOW-R9UuA2_LDhi14_bAhoGsnDig-m_liHxznmjEa_787PD6jGgoiRVVHQOucuQ-JLc1D_n8r1gOKjDKRGFzNnsFBAeUKW3LSsKpld5XEkQoxdadxF1qgaOK9Fmhv0LQr0zg" alt=""><figcaption></figcaption></figure>
*   How do I vote for a gauge on a side chain?

    * All votes must happen on Mainnet where veSDL exists.
    * Vote options will contain root gauges that have corresponding child gauges on side chains.
    * You can vote for the corresponding root gauge.

    <figure><img src="https://lh6.googleusercontent.com/DVfnC6Hy74qbAWw1K7VlBdVZ8JurvI8IK-qxbfdRZxjpSfJNrLZGj-wYSujP_FKEOwTVBjHsA0rDhsh_UtXEARoVodqO4A54cwcaYSndVjk_i5bgTFHjNZyFhHTYKQsg8GhITo0xx-aLz-1hE6Bzg8F0AFQBVzWoK9Jq4JA2n-vsst0vQxM8EiqxuorSKA" alt=""><figcaption></figcaption></figure>
*   How do I claim SDL for a child gauge?

    * Via Farms page or modal on top right.

    <figure><img src="https://lh3.googleusercontent.com/xYv5mLroGW-4OGFtvRno-e73s-qet1caaOAjysBN8F27sdLZv9eX1WYa3JUgQ9mNqjQuLaWd09ZUF3sHRbUHzNpHPWc-uJO6N71Kf5eBLvndRp08esxYKVVPrlRgvFqazKLpvRGNcaq-kMjqS6nxHeyLzSg34QbB2g42fL8WIAvQKeZg46C8CmLZHqaDjg" alt=""><figcaption></figcaption></figure>

### Cross Chain Gauges – FAQs

* How frequently are the rewards bridged to sidechains?
  * At least every 7 days. The rewards for side chains will wait in mainnet until the current epoch is over. Then once the new epoch starts, the waiting SDL can be bridged.
  * An epoch is a 7-day period that begins on Wednesday at UTC 00:00. Minter typically distributes SDL based on the votes up to the previous epoch. In the case of cross chain gauges, there is a buffer of another epoch before rewards are bridged to the side chains for distribution.
* How long does bridging take after the end of the epoch?
  * Depends on each bridge service, but can expect an average of 10-20 minutes.
* Do users have to do anything special to trigger the emission?
  * On each sidechain, the first claim action per epoch will be used for triggering bridging.
  * Thus, if you claim too early in each epoch, your SDL may be delayed due to bridging&#x20;
  * After the launch, the Saddle team will run an automated script every week to ensure the bridging is triggered w/o user action
* I claimed my pending SDL on a sidechain but nothing happened. What’s going on?
  * If you are the first account to claim SDL in that epoch, your call will be used to trigger the bridging SDL from mainnet. You can wait for the bridging to finish and make the claim transaction again to receive the pending SDL.
