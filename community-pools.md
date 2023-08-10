---
description: >-
  Community Pools are the user-generated, permissionless pools on Saddle
  Finance.
---

# Community Pools

## Community Pools: Definitions, Benefits, and Risks

### What are Community Pools?

Community Pools are (also known as Factory Pools, Permissionless Pools, and User-generated pools) are liquidity pools that users can create themselves. Users are allowed to choose the tokens within the pool and their respective weights. All the Community Pools created are then accessible on Saddle.

### What are the benefits of Community Pools?

Community Pools have several benefits compared to [Saddle Pools](https://docs.saddle.finance/saddle-pools):

- Community Pools are **permissionless**. Permissionless refers to an action that can be taken or a system that can be accessed without the approval of an intermediary. This means that anyone can create a Community Pool at any time.&#x20;
- Community Pools are **decentralized**. There is no gatekeeper. Anyone can list any token, without having to wait.&#x20;
- Community Pools can provide a **revenue stream**. Community Pools share fees with the Pool Creator, providing a potential new revenue stream to a protocol, trader, or hodler who creates the Community Pool. Read more [here](community-pools.md#what-percentage-of-pool-fees-go-to-the-pool-creator).

### What are the risks of Community Pools?

All the risks of Saddle Pools apply to Community Pools. Read more about the risks of Saddle Pools [here](https://docs.saddle.finance/saddle-pools#saddle-pool-risks).&#x20;

In addition, Community Pools present additional risks including:

- **Due diligence risk** : Saddle does not conduct due diligence or verify the safety of each Community Pool. Saddle does not reimburse for losses incurred in a Community Pool. It is important to conduct your own research on each Community Pool. Read all the documentation to understand the risks of Community Pools and their risks.
- **Token risk** : Liquidity Pools that are permissionless, like Community Pools, are key to decentralization, but they also present additional risks. Some users list fake tokens, hoping to trick others into buying the wrong asset. Saddle has no control over the tokens added in the Community Pool. That means it is very important to make sure that one is purchasing the correct asset before executing a trade. One must verify the token addresses one trades in a Community Pool.

### How does one stay safe in Community Pools?

- Understand all the tokens present in any Community Pool. This applies even if you are depositing USDC.
- Make sure the parameters are realistic. Get [support](community-pools.md#what-technical-support-is-available-to-pool-creators-who-create-community-pools-on-saddle) if needed.
- Ensure that a liquidator is running in the pool.&#x20;
- Check that the oracle is displaying the correct price.

## How to Create a Community Pool

### How do I create a Community Pool?

Community Pools can be created within a simple interface and by configuring a set of parameters for your asset.

1.  First, navigate to the Saddle dApp, select the “Pools” menu, and select “Create Pool.”

    <figure><img src=".gitbook/assets/Screen Shot 2022-10-12 at 12.08.52 PM.png" alt=""><figcaption><p>Click the Button "Create Pool" to create a Community Pool.</p></figcaption></figure>

2.  Next, Add the Pool Name and Pool Symbol.

    - The Pool Name will show up on the Pools page and also in the Withdraw / Deposit views. It is good practice for the pool name to be descriptive of what type of pool it is.
    - The Pool Symbol is the name that will display on the list of pools on the Saddle frontend. It is good practice for the Pool Symbol to indicate what tokens are in the pool.

    <figure><img src=".gitbook/assets/Screen Shot 2022-10-12 at 12.12.48 PM.png" alt=""><figcaption></figcaption></figure>

3.  Next, scroll down to choose the Pool Type and set the parameters for the Community Pool.

    - The three options for Pool Type are USD Metapool, BTC Metapool, and Base Pool.&#x20;
    - The three Parameters that Pool Creators can set are the Pool Fees, the Amplification Coefficient, and the Token contracts.

    <figure><img src=".gitbook/assets/Screen Shot 2022-10-06 at 11.34.18 PM.png" alt=""><figcaption><p>Parameters that a Pool Creator can set when creating a Community Pool.</p></figcaption></figure>

4.  When all the parameters are filled in, the `Create Community Pool` button will be activated. Click `Create Community Pool`. To see your pool, navigate to [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools). The Pool Symbol chosen for your Community Pool will show up on [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools) with the `Community` tag .
5.  After deploying a pool, you must seed initial liquidity. You can do this by navigating to the Community Pool on [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools) and clicking the `Deposit` button next to your Community Pool. This will bring you to the Add Liquidity page. Connect your wallet and add tokens to your Community Pool.

    <figure><img src=".gitbook/assets/Screen Shot 2022-10-06 at 11.46.09 PM.png" alt=""><figcaption><p>Button to deposit into a Community Pool.</p></figcaption></figure>

    <figure><img src=".gitbook/assets/Screen Shot 2022-10-06 at 11.44.43 PM.png" alt=""><figcaption><p>Page for adding liquidity to a Community Pool.</p></figcaption></figure>

### Does Saddle charge any fee for deploying a Community Pool on Saddle?

Saddle does not charge or take a fee for creating a Community Pool. There is no fee charged by Saddle associated with creating and deploying a Community Pool on Saddle.&#x20;

There is a gas fee associated with deploying a pool that must be paid by the Pool Creator. The gas fee will depend on the network at the time of creating the Community Pool.

### Are there any Listing criteria that a Community Pool must meet in order to be listed on Saddle’s frontend?

There are no listing criteria. If the addresses used are valid, the Community Pool will show up on [Saddle](https://saddle.exchange/#/pools), where Community Pools are ordered automatically by amount of TVL, with higher TVL Community Pools on top.

### What kinds of pools can be created using Saddle’s Community Pools?

Three kinds of pools can be created using Saddle’s Community Pools. &#x20;

- Base pools&#x20;
- BTC metapools&#x20;
- USD metapools

Read more about these different types of pools [here](https://docs.saddle.finance/saddle-pools#base-pool-and-metapool).

### What chains are Community Pools available on?

Community Pools are available to deploy on Ethereum Mainnet, Arbitrum, and Optimism.&#x20;

It’s Saddle’s goal to support Community Pools on every chain where the Saddle dApp is available.

### What parameters of Community Pools can users define?

There are 3 parameters that Creators of a Community Pool can define:&#x20;

- **The Pool Fee** : The Pool Fees are the [trading fees](https://docs.saddle.finance/glossary#saddle-fees) that are charged to traders making swaps in the pool. Pool Creators can set the Pool Fee as a value between 0.01% (minimum) – 1% (maximum).&#x20;
- **The Amplification Coefficient** : A value which can either compress or expand the range of low slippage swaps.
- **Token contracts** : Which tokens make up the pool.

### How do I LP into a Community Pool?

Go to [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools) and navigate to the Community Pool you want to provide liquidity to. Click `Deposit`.

### How do I withdraw from a Community Pool?

Go to [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools) and navigate to the Community Pool you want to provide liquidity to. Click `Withdraw`.

## Community Pools: FAQs

### Can the Saddle DAO make any admin changes to the parameters of a Community Pool?

- The parameters chosen by the Pool Creator cannot be changed. Other users can create separate pools with different parameters.&#x20;
- Saddle can’t change any of the parameters. Saddle can’t pause Community Pools.&#x20;
- Saddle can delist pools from Saddle’s registry, removing the Pools from frontend. The Community Pool would still be visible on other frontends.

### What tokens are supported by Community Pools? Are there any types of tokens that are not supported?

Any token that’s not rebasing is supported by Community Pools. Conversely, tokens that are rebasing are not supported by Community Pools.

### What percentage of Pool Fees go to the Pool Creator?

Admin fees will be split 50-50 between the Pool Creator and Saddle.&#x20;

Admin fees is charged as percentage of the charged swap fee. This can be changed anytime by the Pool Creator.&#x20;

Note that at 100% admin fee, LPs will receive NO swap fees.

Example: If a Pool Creator sets Pool Fee value to 0.04% valid range: \[0.01% \~ 1%] then:&#x20;

- 5/ 0.02% goes to LPs (users who deposited in the pool)&#x20;
- 2.5/ 0.01% goes to Pool Creator&#x20;
- 2.5/ 0.01% goes to to the Saddle multisig, with a 3/2 split between veSDL and Treasury

### How are Pool Fees disbursed to the Pool Creator?

When claimed, fees in each community pool will be split 50-50 between the creator of the pool and the Saddle Treasury.

Saddle will automatically trigger fee collection once the pool's admin fee has reached over certain threshold. If pool creators wish to, they can trigger it manually via calling `withdrawAdminFees()` function on etherscan page of the pool.

This link to the etherscan to the pool can be found in each pool's deposit or withdraw view.

### **What are the listing requirements for a Community Pool to be displayed on Saddle?**

There are no listing requirements. All Community Pools that are created will show up on [Saddle](https://saddle.exchange/#/pools).

### Is it possible to remove a Community Pool once deployed?

It is not possible for Saddle or anyone to destroy or remove a Community Pool once deployed. Saddle can remove a Community Pool from the registry (Saddle frontend). Users would still be able to use the Community Pool from their own frontend.

### What technical support is available to Pool Creators who create Community Pools on Saddle?

Saddle is to be used at your own risk. Admins have no special keys and cannot recover funds if sent improperly. However, a wide variety of resources are still available to help you use Saddle Community Pools. If you have questions, please make sure to reach out in the following channels.

- \#support forum on Saddle’s Discord: [https://discord.gg/qEtPn5pBvk](https://discord.gg/qEtPn5pBvk).
- Chatbot on [Saddle](https://saddle.exchange/#/).&#x20;
- Saddle’s Telegram chat: [https://t.me/saddle_finance](https://t.me/saddle_finance).

Saddle’s partnership team is available to provide bespoke technical support and marketing to Saddle’s partner protocols. Reach out to Partnerships Lead Christian Gonzalez-Capizzi on Telegram (@cxgonzalez) and on Discord (CXGonzalez#2321)
