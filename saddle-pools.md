---
description: Saddle Pools are the liquidity pools in Saddle Finance.
---

# Saddle Pools

## **LIQUIDITY POOLS**

Traditional exchanges use order books to facilitate trade. The centrally managed order books represent the buy and sell orders placed by individuals, derive the price of an asset, and match buyers to sellers. The emergence of the decentralized finance (DeFi) ecosystem turned the concept of order book on its head with [Automated Market Makers](https://docs.saddle.finance/automated-market-makers) (AMM).

AMMs in DeFi use algorithms to price assets and facilitate trade. Staying true to the philosophy of DeFi, AMMs are permissionless, automatic, and available 24/7. Therefore, there are no buyers and sellers (in the traditional sense) in AMMs. Instead, AMMs use [liquidity pools](https://docs.saddle.finance/saddle-faq#what-is-a-saddle-pool) for the trade.

Liquidity pool, a smart contract, is a fund of tokens. The liquidity providers deposit the tokens into the pool. Anyone with an internet connection and holding tokens can become a [liquidity provider](https://docs.saddle.finance/saddle-faq#who-is-a-liquidity-provider) (LP). In exchange for providing the tokens, the LPs normally earn a fee. Now, when a trade executes on an AMM, the trade executes against the liquidity pool. This eliminates the need for an order book and for the buyer and seller to be present at that moment in time.

### **Fees**

Trading on a Saddle pool carries two fees – a trading fee and a gas fee.

_**Trading fee**:_ The trading fee applies to every trade and the prevailing fee is displayed in the pool information. Typically, the fee is 0.04%. However, the fee may vary depending on the pool.

_**Admin fee**:_ The admin fee is included as a % of the trading fee. Currently it is zero.

_**Gas fee**:_ The fee payable to Ethereum network to confirm the transactions. The [gas fee](https://www.gasnow.org) varies depending on the speed of confirmation time required and represented in gwei (1 gwei = 10`-9` ETH).

{% hint style="info" %}
Find Saddle's fee calculation code [here](https://github.com/saddle-finance/saddle-contract/blob/38328fba920abd10bfe3ac9fde98e7c9cc50af9a/contracts/Swap.sol#L81)
{% endhint %}

![](<.gitbook/assets/0 (7).png>)

### **Rewards**

Saddle [rewards ](https://docs.saddle.finance/saddle-incentives)the liquidity providers for their contribution to the liquidity pool. Depending on the liquidity pool, the rewards structure varies. There are many ways to earn rewards – interest from trading fees, interest from lending, and pool specific incentives. We have covered the details of rewards under the liquidity pool sections below.

{% hint style="info" %}
Find Saddle's reward calculation code [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/helper/MiniChefV2.sol)
{% endhint %}

### **Risks**

As with any investment, traditional or DeFi, providing liquidity to the pools carries a risk. Typically, the risks include risk of smart contracts, risks associated with the tokens/Stablecoins in the liquidity pools, and/or the risks associated with the AMMs. We outline the risks in the [Saddle pool risk](https://docs.saddle.finance/saddle-pools#saddle-pool-risks) section.

## **USING SADDLE POOLS**

Working with Saddle pools is easy. You can lend, borrow, and earn interest & rewards by using Saddle pools. By depositing assets into Saddle pools, you become a liquidity provider eligible to earn trading fees. At any time of your choice, you can withdraw your assets.

### **Deposit**

Depositing assets into a pool on Saddle allows users to take part in the protocol as liquidity providers and earn reward incentives. Go to [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools)

* **Step 1:** Choose the pool on the top navigation bar
* **Step 2:** Click on _Deposit_

![](<.gitbook/assets/1 (7).png>)

* **Step 3:** Enter the amount(s) you would like to deposit on one or more of the assets listed in the Saddle pool. (_Tip: deposit underweight assets to get an LP token bonus_).
* **Step 4:** Click _Advanced Options_ to select options like slippage and gas.

![](<.gitbook/assets/2 (10).png>)

* **Step 5:** Click _Deposit_ and review the details and confirm the transaction. _(Tip: If you are depositing into a_ [_Metapool_](https://docs.saddle.finance/saddle-faq#what-is-a-base-pool-and-metapool)_, you have the **option** of depositing individual assets or depositing LP tokens from the_ [_base pool_](https://docs.saddle.finance/saddle-faq#what-is-a-base-pool-and-metapool)_)_

![](.gitbook/assets/3.png)

* **Step 6:** After the transaction confirms, stake your LP tokens to earn rewards (details under pool section).
* **Step 7:** Keep track of your rewards!

{% embed url="https://www.youtube.com/watch?v=RCsBinGAZEg" %}

{% hint style="info" %}
Find Saddle's smart contract code [here](https://github.com/saddle-finance/saddle-contract/blob/38328fba920abd10bfe3ac9fde98e7c9cc50af9a/contracts/Swap.sol#L387)
{% endhint %}

### **Withdraw**

If at any point you want to withdraw your assets, head out to [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools)

**1. Unstaking LP Tokens**

If you have staked your LP tokens for rewards (applicable for select Saddle Pools only), you must unstake the tokens first before withdrawing your asset.

* **Step 1:** Go to the rewards dashboard as applicable in your case ([KEEP Rewards](https://dashboard.keep.network/liquidity), [ALCX Rewards](https://app.alchemix.fi/farms), [FRAX Rewards](https://app.frax.finance/staking))
* **Step 2:** Unstake your LP Tokens

**2. Withdraw Assets**

After unstaking your LP Tokens (where applicable), return to [Saddle Pools](https://saddle.exchange/#/pools) and follow the steps outlined below to withdraw your assets.

* **Step 1:** Choose the pool on the top navigation bar
* **Step 2:** Click on _Withdraw_

![](<.gitbook/assets/5 (2) (1).png>)

* **Step 3:** Enter the amount you’d like to withdraw from one or more of the assets listed in the Saddle pool. (_Tip: withdraw overweight assets to get a bonus_).
* **Step 4:** Click _Advanced Options_ to select options like slippage and gas.

![](<.gitbook/assets/6 (8) (7).png>)

* **Step 5:** Click _Withdraw_ and review the details and confirm the transaction.

{% hint style="info" %}
Find Saddle's smart contract code [here](https://github.com/saddle-finance/saddle-contract/blob/38328fba920abd10bfe3ac9fde98e7c9cc50af9a/contracts/Swap.sol#L314)
{% endhint %}

## **CHOOSING A SADDLE POOL**

[Stablecoins ](https://docs.saddle.finance/saddle-faq#what-are-stablecoins)are becoming popular because of the stability they bring to the volatile crypto world. Stablecoins also come in various flavors – backed by assets (e.g., fiat currency, gold), cryptocurrencies, and algorithmically stabilized.

Saddle supports a [wide range](https://docs.saddle.finance/saddle-faq#what-tokens-are-currently-supported-by-saddle) of Stablecoins, giving users the flexibility to choose and move between Stablecoins of their choice. Therefore, the list of Stablecoins supported by Saddle keeps growing. In this section, we will explain how you can choose various Stablecoin pools, the rewards and risks specific to the pools.

Broadly, there are three types of pools to select from – BTC, ETH, and USD.

![](<.gitbook/assets/7 (5).png>)

### **Base Pool & Metapool**

Saddle pools are of two types – base and metapools.

* _**Base pools**_ contain two or more tokens and implement the StableSwap algorithm.
* _**Metapools**_ contain one token to trade with another underlying Base pool. For example, in the sUSD Pool, we pool the single token sUSD alongside Stablecoin Pool V2 (DAI, USDC, USDT). Adding the single asset to the metapool, however, does not dilute the liquidity of the underlying base pool.

|              |                    |           |                          |                                                                                                                            |                                                                                                  |
| ------------ | ------------------ | --------- | ------------------------ | -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **CATEGORY** | **POOL**           | **TYPE**  | **TOKENS**               | **STATUS**                                                                                                                 | **REWARDS**                                                                                      |
| BTC          | BTC Pool           | Base Pool | wBTC, renBTC, sBTC, tBTC | Outdated - [Migrate](https://docs.saddle.finance/saddle-incentives#migrating-incentives-to-tbtc-metapool) to tBTC Metapool | <ul><li>N/A</li></ul>                                                                            |
| BTC          | BTC Pool V2        | Base Pool | wBTC, renBTC, sBTC       | Live                                                                                                                       | <ul><li>Trading fees</li></ul>                                                                   |
| BTC          | tBTC Pool          | Metapool  | tBTCv2, saddleBTC-V2     | Live                                                                                                                       | <ul><li>Trading fees</li><li>KEEP Incentives</li></ul>                                           |
| ETH          | alETH Pool         | Base Pool | WETH, alETH, sETH        | Live                                                                                                                       | <ul><li>Trading fees</li><li>ALCX incentives</li><li>Flash loan fees</li></ul>                   |
| ETH          | vETH2 Pool         | Base Pool | WETH, VETH2              | Paused                                                                                                                     | N/A                                                                                              |
| USD          | Stablecoin Pool    | Base Pool | DAI, USDC, USDT          | Outdated – [Migrate](https://medium.com/saddle/launching-v2-of-the-saddle-3pool-bc82f0bcd700) to V2                        | N/A                                                                                              |
| USD          | Stablecoin Pool V2 | Base Pool | DAI, USDC, USDT          | Live                                                                                                                       | <ul><li>Trading fees</li><li>Flash loan fees</li></ul>                                           |
| USD          | D4 Pool            | Base Pool | alUSD, FEI, FRAX, LUSD   | Live                                                                                                                       | <ul><li>Trading fees</li><li>Flash loan fees</li><li>TRIBE, FXS, LQTY, ALCX incentives</li></ul> |
| USD          | sUSD Pool          | Metapool  | sUSD, saddleUSD-V2       | Live                                                                                                                       | <ul><li>Trading fees</li><li>Flash loan fees</li></ul>                                           |
| USD          | wCUSD Pool         | Metapool  | wCUSD, saddleUSD-V2      | Live                                                                                                                       | <ul><li>Trading fees</li></ul>                                                                   |

{% hint style="info" %}
Find Saddle's deployed code base [here](https://github.com/saddle-finance/saddle-contract/tree/master/deployments)
{% endhint %}

### **BTC Pool**

The BTC pool currently supports four wrapped variants of Bitcoin, enabling Bitcoin users to take part in the Ethereum DeFi ecosystem.

* _wBTC_: Wrapped BTC is an ERC20 token backed 1:1 by the actual Bitcoin.
* _renBTC_: Like wBTC, renBTC is an ERC20 token backed 1:1 by Bitcoin. Ren also decentralizes the custody of the BTC.
* _tBTC_: Like Ren, tBTC is backed 1:1 by Bitcoin and truly decentralized.
* _sBTC_: sBTC differs from the rest, as Bitcoins does not back it. The value of sBTC is kept stable through an over-collateralization mechanism leveraging Synthetix SNX tokens.

![](.gitbook/assets/8.png)

**Rewards**

**Note: BTC Pool is outdated. Follow the** [**migration**](https://docs.saddle.finance/saddle-incentives#migrating-incentives-to-tbtc-metapool) **guide to move your assets and KEEP incentives to the new tBTC Metapool.**

Saddle rewards you in two ways for the BTC pool – trading fees and as KEEP incentives every time you provide liquidity to the BTC pool.

The Keep Network team has committed weekly reward incentives for liquidity providers. After the transaction confirms, stake your LP tokens on the [KEEP Liquidity Rewards Dashboard](https://dashboard.keep.network/liquidity) in the Saddle Pool to earn KEEP rewards. Check [KEEP](https://dashboard.keep.network/liquidity) to know the current APY for the deposits.

![](<.gitbook/assets/9 (1).png>)

### **BTC Pool V2**

The BTC pool V2 currently supports three wrapped variants of Bitcoin, enabling Bitcoin users to take part in the Ethereum DeFi ecosystem.

* _wBTC_: Wrapped BTC is an ERC20 token backed 1:1 by the actual Bitcoin.
* _renBTC_: Like wBTC, renBTC is an ERC20 token backed 1:1 by Bitcoin. Ren also decentralizes the custody of the BTC.
* _sBTC_: sBTC differs from the rest, as Bitcoins does not back it. The value of sBTC is kept stable through an over-collateralization mechanism leveraging Synthetix SNX tokens.

![](<.gitbook/assets/10 (8).png>)

**Rewards**

Saddle rewards you with trading fees for the BTC Pool V2.

### **tBTC Pool**

The Saddle tBTC Pool is a metapool. In this pool, we pooled the single token tBTCv2 alongside BTC Pool V2 (wBTC, renBTC, sBTC). Adding the single asset to the metapool, however, does not dilute the liquidity of the underlying base pool.

* _tBTCv2_: tBTC is backed 1:1 by Bitcoin and truly decentralized.
* _saddleBTC-V2_: A base pool (BTC Pool V2) on Saddle comprising the pegged assets wBTC, renBTC, and sBTC.

![](<.gitbook/assets/11 (2).png>)

**Rewards**

Saddle rewards you in two ways for the tBTC pool – trading fees and as KEEP incentives every time you provide liquidity to the tBTC pool.

After the transaction confirms, stake your LP tokens on the [KEEP Liquidity Rewards Dashboard](https://dashboard.keep.network/liquidity) in the Saddle Pool to earn KEEP rewards. Check [KEEP ](https://dashboard.keep.network/liquidity)to know the current APY for the deposits.

![](https://lh5.googleusercontent.com/YLb-mQ8N0Sw-CVM8LlqRAA32zU\_YIviHuvjQ8Kq-govkGMtixSItgPfRCi42Wm-KmvPEwe3PiDyeuwBsha\_KZ94Hn6etEku7K5ja5PYN91IyMa9CxQobaNQKHwcSkR9qnP5wNsQ)

### **alETH Pool**

The ETH pool on Saddle is of alETH – a synthetic ETH backed asset by Alchemix. alETH is a multi-pool currently supporting three variants of Ethereum, enabling seamless and cheap switch between pegged-value ETH assets (backed or wrapped).

* _WETH_: Wrapped ETH is an ERC20 token backed 1:1 by ETH, allowing trade directly with ALT coins.
* _alETH_: Like WETH, alETH is an ERC20 token, but backed 4:1 by ETH.
* _sETH_: sETH is a short position built through the dYdX protocol and can be traded like any ERC20 token. sETH is tied to USD-backed stablecoin DAI.

![](<.gitbook/assets/12 (3).png>)

**Rewards**

Saddle rewards you trading fees, flash loan fees, and ALCX tokens every time you provide liquidity to the alETH pool. After the transaction confirms, stake your LP tokens on the [Alchemix Staking Dashboard](https://app.alchemix.fi/farms) to earn rewards. Check [ALCX](https://app.alchemix.fi/farms) to know the current APY for the deposits.

![](<.gitbook/assets/13 (8) (4).png>)

### **Stablecoin Pool V2**

The Stablecoin pool contains three stablecoins, unlocking deep on-chain liquidity between pegged value crypto assets.

* _USDC_: USDC is an ERC20 token pegged 1:1 to the US dollars (USD)
* _USDT_: USDT, like USDC, is pegged 1:1 to the USD
* _DAI_: DAI is soft pegged to the USD algorithmically.

**Note:** Stablecoin Pool (v1) is outdated and V2 is live now. V2 provides a smoother and cheaper way to provide liquidity and swap the stablecoins. V2 also comes with optimized code (lower gas costs), metapool, [flash loan](https://docs.saddle.finance/howtoflashloan) support, and no more withdrawal fee.

Follow [this guide](https://medium.com/saddle/launching-v2-of-the-saddle-3pool-bc82f0bcd700) to migrate your liquidity to V2.

![](<.gitbook/assets/14 (6).png>)

**Rewards**

Saddle rewards you in two ways for the stablecoin pool - trading fees and flash loan fees. The Stablecoin Pool V2 live supports flash loans, which will generate additional returns for liquidity providers.

### **D4 Pool**

The Saddle D4 (decentralized) pool consists entirely of permissionless, decentralized stablecoins. Stablecoins like USDC, USDT, and Dai are not permissionless – centralized organizations manage them with varying degrees of transparency.

In contrast, the Saddle D4 pool, currently composed of four permissionless stablecoins, ensures users can take part with no restrictions or blacklisting.

* _alUSD_: A yield-backed synthetic stablecoin minted via Alchemix Finance, a DAO-governed synthetic asset platform.
* _FEI_: A scalable and decentralized stablecoin that leverages protocol-controlled value (PCV) for peg maintenance while maintaining highly liquid secondary markets.
* _FRAX_: A fractional-algorithmic stablecoin that is partially backed by collateral and partially stabilized algorithmically.
* _LUSD_: The USD-pegged stablecoin of the Liquity decentralized borrowing protocol.

![](<.gitbook/assets/15 (3).png>)

**Rewards**

Saddle rewards you in three ways for the D4 decentralized pool – trading fees, flash loan fees, and as four rewards (TRIBE, FXS, LQTY, and ALCX tokens) every time you provide liquidity to the D4 pool. After the transaction confirms, stake your LP tokens on the [Frax Finance](https://app.frax.finance/staking#Saddle\_alUSD\_FEI\_FRAX\_LUSD) dashboard to earn rewards. Check [Frax](https://app.frax.finance/staking#Saddle\_alUSD\_FEI\_FRAX\_LUSD) to know the current APR for the deposits.

![](<.gitbook/assets/16 (3).png>)

### **sUSD Pool**

The Saddle sUSD Pool is a metapool. In this pool, we pooled the single token sUSD alongside Stablecoin Pool V2 (DAI, USDC, USDT). Adding the single asset to the metapool, however, does not dilute the liquidity of the underlying base pool.

* _sUSD_: A synthetic stablecoin on the Synthetix platform, whose value tracks the US Dollar.
* _saddleUSD-V2_: A base pool (Stablecoin Pool V2) on Saddle comprising the stablecoins USDT, USDC, and DAI.

![](.gitbook/assets/17.png)

**Rewards**

Saddle rewards you with trading fees and flash loan fees for the sUSD pool.

### **wCUSD Pool**

The Saddle wCUSD Pool is a metapool. In this pool, we pooled the single token CUSD (Celo Dollars) alongside Stablecoin Pool V2 (DAI, USDC, USDT). Adding the single asset to the metapool, however, does not dilute the liquidity of the underlying base pool.

* _wCUSD_: Wrapped Celo Dollar (wCUSD) is an ERC20 token, representing a 1:1 share of Celo Dollar (CUSD).
* _saddleUSD-V2_: A base pool (Stablecoin Pool V2) on Saddle comprising the stablecoins USDT, USDC, and DAI.

![](<.gitbook/assets/18 (2).png>)

**Rewards**

Saddle rewards you with trading fees for the wCUSD pool.

## **SADDLE POOL RISKS**

Providing liquidity to Saddle is highly risky. The risk of this pool includes, but not limited to:

### **Technical Risks**

_**Smart contract risk:**_ Before using the protocol, we highly recommend [reading the code](https://github.com/saddle-finance/saddle-contract) and understanding the risks involved with being a Liquidity Provider (LP) and/or using the AMM to trade pegged value crypto assets.

_**Audit risk:**_ OpenZeppelin, Quantstamp, and Certik [audited](https://github.com/saddle-finance/saddle-audits) the Saddle smart contracts. However, security audits don’t eliminate all risks. Do not supply assets you cannot afford to lose to Saddle as a liquidity provider.

_**Systemic risk:**_ A 3/7 Gnosis Safe multisig controls Saddle's admin keys. The signers are Mariano Conti, Kain Warwick, DegenSpartan, Klim K, Damir Bandalo, scoopytrooples, and Aurelius. This multisig has capabilities to pause new deposits and trades in case of technical emergencies. Users will always be able to withdraw their funds regardless of new deposits being paused. The multisig can also change the swap/withdrawal fees and the per pool/account deposit limits.

_**Hacking/Protocol failure:**_ Even though blockchain technology is, theoretically, hack-proof, there have been instances of hacking either the protocol or surrounding ecosystem such as wallets, exchanges, and marketplaces.

_**Scalability:**_ The underlying blockchain network (Ethereum) suffers from network slowdown because of the high volume of transactions. While solutions are being tested out and deployed to improve the network throughput, the risk of slowdown of the Ethereum network, affecting transactions, remains.

_**Experimental technology:**_ No technology is perfect and prone to human errors and technical glitches, especially new and upcoming technologies such as blockchain and DeFi.

### **Market Risks**

_**Pegged value asset risk:**_ If one asset in the pool significantly depegs, it will effectively mean that it will leave pool liquidity providers holding only that asset.

_**Market Cap:**_ The crypto market fluctuates wildly. Though stablecoins are meant to address the volatility, there is always a risk of losing some principle or the assets backing the stablecoins might decline.

_**Liquidity:**_ Liquidity risk may happen because of a seller not finding a buyer or there is a mandatory lock-in period.

_**Pricing errors:**_ We constantly introduce new products and prices to offer innovative solutions to our customers. An error or a misinformed strategy may affect the returns.

_**Economic incentive failure:**_ As a relatively new product and technology, there is still a risk of widespread acceptance, and therefore demand. While extra incentives are offered and calibrated regularly, the risk of incentive mechanisms not encouraging the desired behavior exists.

_**Impermanent loss risk:**_ Impermanent loss occurs when the value of the funds staked to the AMM fluctuates drastically.

_**Margin slippage risks:**_ Slippage occurs when the execution price of a trade is different from its requested price. Though Saddle maintains minimal slippage, using the Stableswap algorithm, there is always a risk of slippage.

### **Counterparty Risks**

_**Asset-backed stablecoins:**_ The collaterals in reserve backing the stablecoins is a black box in some cases, especially, where the stablecoins are issued by centralized protocols.

_**Algorithmic stablecoins:**_ Certain algorithmic stablecoins have no collateral and are partially/fully collateralized by their native token. An insolvency risk of the native token collapsing exists with these digital assets.

_**Blacklisting**_: Centrally managed stablecoins are also subject to risks such as blacklisting accounts, and regulatory risks like mandatory KYC, or even erasing funds.

_**Oracle risk:**_ Many systems rely on Oracles (3rd party systems) for information such as market price. A risk of technical glitches or malicious attack exists with the Oracle feeds.

### **Other Risks**

_**Regulatory:**_ Cryptocurrencies and DeFis are unregulated in many countries. While governments and regulators are stepping in, the risk of regulatory framework changing and affecting the investments persists.

_**Taxation:**_ As a new and rapidly developing asset class, cryptocurrencies are subject to high Stablecoins are at the heart of Saddle DeFi ecosystem. Whilst all stablecoin investments are risky, some carry higher risks. Therefore, the risk of Saddle pools vary from pool to pool. In this section, uncertainty. Substantial risk exists regarding the tax treatment of investment in digital assets.

_**Black Swan:**_ A black swan event is a rare event - such as an attack on the collateral, unexpected price decrease, or a highly coordinated attack by malicious parties.

_**User abandonment:**_ DeFi and AMMs are complex technologies and concepts. A risk of users abandoning the protocol in favor of seemingly simpler systems exists.

### **Risks Per Pool**

Stablecoins are at the heart of the Saddle DeFi ecosystem. Whilst all stablecoin investments are risky, some carry higher risks. Therefore, the risk of Saddle pools varies from [pool to pool](https://docs.saddle.finance/asset-specific-risks). In this section, we’ve highlighted the _key risk indices_ for various pools.

### **Assets Reference**

This section provides a reference to the documentation for the various assets used in Saddle Pools.

|                      |                                  |                                                                                  |                                                                                     |                                                    |                                                                                                                                                         |                                                                                                |
| -------------------- | -------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **Asset**            | **Website**                      | **Whitepaper**                                                                   | **Document**                                                                        | **Source Code**                                    | **Audits**                                                                                                                                              | **Contract**                                                                                   |
| **alETH, alUSD**     | [WB](https://www.alchemix.fi)    | [WP](https://alchemix.fi/c76d1d663f6c8247b86a8fca83d5bd1b.pdf)                   | [DOC](https://alchemix-finance.gitbook.io/alchemix-finance/)                        | [SC](https://github.com/alchemix-finance)          | [AUD](https://alchemix.fi/a208baf6ca7e0d6b0116461f05e27cd9.pdf)                                                                                         | [CON](https://github.com/alchemix-finance/contract-addresses/blob/dev/alchemix-addresses.json) |
| **DAI**              | [WB](https://makerdao.com)       | [WP](https://makerdao.com/en/whitepaper/)                                        | [DOC](https://docs.makerdao.com)                                                    | [SC](https://github.com/makerdao)                  | [AUD](https://github.com/makerdao/audits)                                                                                                               | [CON](https://etherscan.io/address/0x6b175474e89094c44da98b954eedeac495271d0f)                 |
| **FEI**              | [WB](https://fei.money)          | [WP](https://docs.fei.money/whitepaper)                                          | [DOC](https://docs.fei.money)                                                       | [SC](https://github.com/fei-protocol)              | [AUD](https://docs.fei.money/audit)                                                                                                                     | [CON](https://docs.fei.money/protocol/contract-addresses)                                      |
| **FRAX**             | [WB](https://frax.finance)       | [WP](https://docs.frax.finance/overview)                                         | [DOC](https://docs.frax.finance)                                                    | [SC](https://github.com/FraxFinance/frax-solidity) | [AUD](https://certik.foundation/vendors/fraxfinance)                                                                                                    | [CON](https://docs.frax.finance/smart-contracts/frax)                                          |
| **LUSD**             | [WB](https://www.liquity.org)    | [WP](https://docsend.com/view/bwiczmy)                                           | [DOC](https://docs.liquity.org)                                                     | [SC](https://github.com/liquity/dev)               | [AUD](https://docs.liquity.org/documentation/resources#security-audits)                                                                                 | [CON](https://docs.liquity.org/documentation/resources#contract-addresses)                     |
| **renBTC**           | [WB](https://renproject.io)      | [WP](https://renproject.io/litepaper.pdf)                                        | [DOC](https://docs.renproject.io/developers)                                        | [SC](https://github.com/renproject)                | [AUD](https://github.com/renproject/ren/wiki/Audits)                                                                                                    | [CON](https://renproject.github.io/ren-client-docs/contracts/)                                 |
| **sBTC, sETH, sUSD** | [WB](https://synthetix.io)       | [WP](https://docs.synthetix.io/litepaper)                                        | [DOC](https://docs.synthetix.io)                                                    | [SC](https://github.com/Synthetixio)               | [AUD](https://docs.synthetix.io/contracts/audits/)                                                                                                      | [CON](https://docs.synthetix.io/addresses/)                                                    |
| **tBTC**             | [WB](https://tbtc.network)       | [WP](https://docs.keep.network/tbtc/index.pdf)                                   | [DOC](https://tbtc.network/developers/)                                             | [SC](https://github.com/keep-network/tbtc)         | [AUD](https://github.com/keep-network/tbtc/tree/a85cc4c6453ab88684c365f41335281c98a828d9#security)                                                      | -                                                                                              |
| **USDC**             | [WB](https://www.centre.io/usdc) | [WP](https://f.hubspotusercontent30.net/hubfs/9304636/PDF/centre-whitepaper.pdf) | [DOC](https://www.centre.io/developer-resources)                                    | [SC](https://github.com/centrehq)                  | -                                                                                                                                                       | [CON](https://etherscan.io/token/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48)                   |
| **USDT**             | [WB](https://tether.to)          | [WP](https://tether.to/wp-content/uploads/2016/06/TetherWhitePaper.pdf)          | [DOC](https://tether.to/knowledge-base/)                                            | [SC](https://github.com/shipshapecode/tether)      | [AUD](https://wallet.tether.to/transparency?\_\_cf\_chl\_jschl\_tk\_\_=pmd\_b52840356b4c3f57d84b3b0cdf1606bfa5688dab-1628925480-0-gqNtZGzNAeKjcnBszQh6) | [CON](https://etherscan.io/address/0xdac17f958d2ee523a2206206994597c13d831ec7)                 |
| **wBTC**             | [WB](https://wbtc.network)       | [WP](https://wbtc.network/assets/wrapped-tokens-whitepaper.pdf)                  | [DOC](https://github.com/WrappedBTC/bitcoin-token-smart-contracts/tree/master/docs) | [SC](https://github.com/WrappedBTC)                | [AUD](https://wbtc.network/dashboard/order-book)                                                                                                        | [CON](https://etherscan.io/address/0x2260fac5e5542a773aa44fbcfedf7c193bc2c599)                 |
| **WETH**             | [WB](https://weth.io)            | -                                                                                | [DOC](https://openbase.com/js/advanced-weth/documentation)                          | [SC](https://github.com/WETH10)                    | -                                                                                                                                                       | [CON](https://etherscan.io/address/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2)                 |

**Disclaimer:** These are links to external websites. Saddle Finance does not provide or maintain the external websites. We do not guarantee the accuracy, relevance, timeliness, and/or completeness of any information on the external websites.
