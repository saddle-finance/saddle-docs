---
description: >-
  Saddle rewards the liquidity providers for their contribution to the liquidity
  pools.
---

# Saddle Incentives

## **SADDLE REWARDS**

Saddle _does not_ have a token currently and offers no Saddle specific incentives. However, we offer incentives from other protocols. The [liquidity providers](https://docs.saddle.finance/saddle-faq#who-is-a-liquidity-provider) are rewarded for their contribution to the liquidity pool. Depending on the liquidity pool, the rewards structure varies.

### **Terminologies**

The terminologies used across Saddle are:

**Earned Fees**: Any earnings of _**Trading Fees**_ and/or _**Flash Loan Fees**_ from providing liquidity to the Saddle pools.

**Incentives**: The incentives from the _**Saddle protocol and/or partners protocols**_. For e.g., KEEP, ALCX. _Note:_ Currently there are no Saddle protocol specific incentives.

**Rewards**: Refers collectively to both _**earned fees and incentives**_.

### **APY & APR**

Before we cover the pool specific rewards, let’s understand the difference between APY and APR.

**Annual Percentage Yield (APY):** APY refers to the amount of interest a liquidity provider earns over one year. APY is like an interest rate, but the biggest benefit of APY is the _compounding_.

**Annual Percentage Rate (APR):** APR does not factor compounding and represents the annual interest rate.

Let’s take a scenario of 1% interest each month. Therefore,

|                                                |                                                   |
| ---------------------------------------------- | ------------------------------------------------- |
| **APR at 1% interest per month**               | **APY at 1% interest per month**                  |
| APR = Periodic Rate x No. of Periods in a Year | APY = (1 + Periodic Rate) `Number of periods` – 1 |
| APR = 1% X 12 months                           | APY = (1+1%)`12`-1                                |
| 12.00%                                         | 12.68%                                            |

### **Saddle APY & Reward APR**

In Saddle both APY and APR are available as rewards to the liquidity providers. The prevailing rates are available in the [pool details](https://docs.saddle.finance/saddle-pools).

![](<.gitbook/assets/0 (2).png>)

**APY pay-out**: In Saddle, APY is calculated based on the last 24 hour volume. In the event of no volume, then you will observe “-” in the Saddle dApp frontend. The trading fees compound automatically for every transaction and are paid when the liquidity providers withdraw their funds.

**APR pay-out**: Saddle partners provide the pool specific APR incentives. Refer to the pool specific section for details.

### **Staking LP Tokens**

The _typical_ process to take part in the reward program is to stake the LP tokens. Refer to the pool specific sections to know more about the reward program provided by our partners.

![](<.gitbook/assets/1 (6).png>)

## **BTC Pool**

Saddle rewards you in two ways for the BTC pool – trading fees and as KEEP incentives when you provide liquidity to the BTC pool and stake the LP tokens respectively.

![](<.gitbook/assets/2 (4) (1).png>)

### **Trading Fees**

When you provide liquidity to the BTC pool, we will show you the APY you are eligible to receive. The trading fees compound automatically for every transaction and are paid when the liquidity providers withdraw their funds.

### **KEEP Incentives**

**Note: BTC Pool is outdated. Follow the **[**migration**](https://docs.saddle.finance/saddle-incentives#migrating-incentives-to-tbtc-metapool)** guide to move your assets and KEEP incentives to the new tBTC Metapool.**

Once you provide liquidity to the BTC pool, you will receive KEEP tokens representing your share of the liquidity pool. Follow these steps to stake the KEEP LP tokens to earn rewards. Check [KEEP](https://dashboard.keep.network/liquidity) dashboard to know the current interest rates for the deposits.

* **Step 1:** Go to [KEEP Liquidity Rewards Dashboard](https://dashboard.keep.network/liquidity)
* **Step 2:** Connect your wallet

![](<.gitbook/assets/3 (10).png>)

* **Step 3:** Scroll down and select **TBTC V2 + SADDLE** pool
* **Step 4:** Enter the amount of KEEP tokens to stake and click DEPOSIT

![](<.gitbook/assets/4 (9).png>)

* **Step 5:** Start earning incentives

### **Migrating incentives to tBTC Metapool**

The tBTC metapool is now [live](https://saddle.exchange/#/pools/tbtc/deposit). The assets from BTC Pool v1 are now split across BTC Pool V2 and tBTC Metapool.

![](<.gitbook/assets/5 (10).png>)

The KEEP incentives will have to be moved from BTC Pool (v1) to the tBTC metapool. The migration is _**not an automatic process**_ and will have to be done manually, as outlined here.

**1. Unstaking KEEP Incentives**

* **Step 1:** Go to [KEEP Liquidity Rewards Dashboard](https://dashboard.keep.network/liquidity)
* **Step 2:** Connect your wallet
* **Step 3:** Scroll down and select **TBTC V2 + SADDLE** pool
* **Step 4:** Click WITHDRAW ALL to unstake your KEEP rewards

**2. Withdraw assets from BTC Pool (v1)**

* **Step 1:** Go to [BTC Pool Withdraw](https://saddle.exchange/#/pools/btc/withdraw)
* **Step 2:** Enter the amount you wish to withdraw
* **Step 3:** Choose slippage and gas
* **Step 4:** Click Withdraw

**3. Option 1 : Deposit assets into directly into tBTC Metapool**

* **Step 1:** Go to [tBTC Pool Deposit](https://saddle.exchange/#/pools/tbtc/deposit)
* **Step 2:** Enter the amount you wish to deposit
* **Step 3:** Choose slippage and gas
* **Step 4:** Click Deposit
* **Step 5:** After the transaction confirms, stake your LP tokens to earn rewards

**3. Option 2 : Deposit assets into BTC Pool V2 and then into tBTC Metapool**

* **Step 1:** Go to [BTC Pool V2 Deposit](https://saddle.exchange/#/pools/btcv2/deposit)
* **Step 2:** Enter the amount you wish to deposit
* **Step 3:** Choose slippage and gas
* **Step 4:** Click Deposit
* **Step 5:** Receive LP Tokens (saddleBTC-V2)
* **Step 6:** Go to [tBTC Pool Deposit](https://saddle.exchange/#/pools/tbtc/deposit)
* **Step 7:** Click on **Deposit Wrapped**

![](<.gitbook/assets/6 (1).png>)

* **Step 8:** Enter the amount you wish to deposit
* **Step 9:** Choose slippage and gas
* **Step 10:** Click Deposit
* **Step 11:** After the transaction confirms, stake your LP tokens to earn rewards

**4. Staking LP tokens to earn incentives**

**Note 1**: tBTC has been upgraded to v2, learn more about it [here](https://blog.keep.network/keep-proposal-overview-shifting-incentives-towards-coverage-pools-and-tbtc-v2-6517a37625c2).

**Note 2:** At the time of writing this, the staking UI for v2 tBTC on KEEP is not yet live, you can follow this [guide](https://forum.keep.network/t/how-to-stake-saddle-tbtc-lps-with-etherscan/335) to stake using Etherscan.

## **alETH Pool**

Saddle rewards you trading fees, flash loan fees , and alETH LP tokens every time you provide liquidity to the alETH pool and stake the LP tokens respectively.

![](<.gitbook/assets/7 (8) (5).png>)

### **Trading Fees**

When you provide liquidity to the alETH pool, we will show you the APY you are eligible to receive. The trading fees compound automatically for every transaction and are paid when the liquidity providers withdraw their funds.

### **Flash Loan Fees**

The alETH pool also supports flash loans, which will generate additional returns for liquidity providers. When you provide liquidity to the alETH pool, we will show you the APY you are eligible to receive. The flash loan fees are included in the trading fees.

### **ALCX Incentives**

Once you provide liquidity to the alETH pool, you will receive alETH Saddle LP tokens representing your share of the liquidity pool. Follow these steps to stake the ALCX LP tokens to earn incentives. Check [Alchemix Staking Dashboard](https://app.alchemix.fi/farms) to know the current interest rates for the deposits.

* **Step 1:** Go to [Alchemix Staking Dashboard](https://app.alchemix.fi/farms)
* **Step 2:** Click on **Connect** to connect to your wallet

![](<.gitbook/assets/8 (1).png>)

* **Step 3:** Once the wallet is connected, click on **alETH Saddle LP Pool**

![](<.gitbook/assets/9 (5).png>)

* **Step 4:** Enter the amount of LP token you wish to stake and click approve

![](<.gitbook/assets/10 (5).png>)

* **Step 5:** Start earning incentives

## **Stablecoin Pool V2**

Saddle rewards you in two ways for the stablecoin pool - trading fees and flash loan fees. The Stablecoin Pool V2 live supports flash loans, which will generate additional returns for liquidity providers.

![](<.gitbook/assets/11 (9).png>)

**Note:** Stablecoin Pool (v1) is outdated and V2 is live now. V2 provides a smoother and cheaper way to provide liquidity and swap the stablecoins. V2 also comes with optimized code (lower gas costs), meta pool, [flash loan](https://docs.saddle.finance/howtoflashloan) support, and no more withdrawal fee. Follow [this guide](https://medium.com/saddle/launching-v2-of-the-saddle-3pool-bc82f0bcd700) to migrate your liquidity to V2.

### **Trading Fees**

When you provide liquidity to the Stablecoin V2 pool, we will show you the APY you are eligible to receive. The trading fees compound automatically for every transaction and are paid when the liquidity providers withdraw their funds.

### **Flash Loan Fees**

The Stablecoin V2 pool also supports flash loans, which will generate additional returns for liquidity providers. When you provide liquidity to the pool, we will show you the APY you are eligible to receive. The flash loan fees are included in the trading fees.

## **D4 Pool**

Saddle rewards you in three ways for the D4 decentralized pool – trading fees, flash loan fees , and four incentives (TRIBE, FXS, LQTY, and ALCX tokens) every time you provide liquidity to the D4 pool.

![](<.gitbook/assets/12 (8).png>)

### **Trading Fees**

When you provide liquidity to the D4 pool, we will show you the APY you are eligible to receive. The trading fees compound automatically for every transaction and are paid when the liquidity providers withdraw their funds.

### **Flash Loan Fees**

The D4 pool also supports flash loans, which will generate additional returns for liquidity providers. When you provide liquidity to the D4 pool, we will show you the APY you are eligible to receive. The flash loan fees are included in the trading fees.

### **ALCX/FXS/LQTY/TRIBE Incentives**

Once you provide liquidity to the D4 pool, you will receive four LP tokens (ALCX, FXS, LQTY, and TRIBE) representing your share of the liquidity pool. Follow these steps to stake the LP tokens to earn incentives. Even though you have four tokens, you’ll only need to use [FRAX Staking Dashboard](https://app.frax.finance/staking). The current interest rates for the deposits are available in the dashboard.

* **Step 1:** Go to [FRAX Staking Dashboard](about:blank)
* **Step 2:** Choose on **Staking** **🡪 Saddle alUSD/FEI/FRAX/USD**

![](<.gitbook/assets/13 (3).png>)

* **Step 3**: Scroll down and click on **Connect Wallet**

![](<.gitbook/assets/14 (3).png>)

* **Step 4**: Choose the **Amount** to stake, **Days** to stake, and click on **Stake**

![](<.gitbook/assets/15 (1).png>)

* **Step 5:** Start earning incentives

## **sUSD Metapool**

Saddle rewards you with trading fees when you provide liquidity to the sUSD metapool. If you observe “-” in the Saddle dApp frontend, it means there has not been any trading volume over the last 24 hours to calculate the APY.

## **BTC Pool V2**

Saddle BTC pool V2 is [live](https://blog.saddle.finance/launching-v2-of-the-saddle-btc-pool/). Saddle rewards you with trading fees when you provide liquidity to the BTC Pool V2. For migrating incentives from BTC Pool v1, follow this [guide](https://docs.saddle.finance/saddle-incentives#migrating-incentives-to-tbtc-metapool).

## **tBTC Metapool**

Saddle tBTC Metapool is [live](https://saddle.exchange/#/pools/tbtc/deposit). For details on rewards and migrating rewards, refer to the [BTC Pool section](https://docs.saddle.finance/saddle-incentives#migrating-incentives-to-tbtc-metapool).

Saddle rewards you in two ways for the tBTC Metapool – trading fees and as KEEP incentives when you provide liquidity to the tBTC Metapool and stake the LP tokens respectively.

![](https://lh5.googleusercontent.com/W-HDdIeYNYYsblQtJJkozIhLcPcDSCgQ5Nu6Ojf9hi7ssPLIg-eMtQEOm1j4TyxTqBQAPVpjYGa0Pk7qWL2ePNGag6pP\_z2aCdB9mUSxSpMHK1PdSKEfUhhTP3I4pIfVtFwUi60)

### **Trading Fees**

When you provide liquidity to the tBTC metapool, we will show you the APY you are eligible to receive. The trading fees compound automatically for every transaction and are paid when the liquidity providers withdraw their funds.

### **KEEP Incentives**

Once you provide liquidity to the BTC pool, you will receive KEEP tokens representing your share of the liquidity pool. Follow these steps to stake the KEEP LP tokens to earn rewards. Check [KEEP](https://dashboard.keep.network/liquidity) dashboard to know the current interest rates for the deposits.

**Step 1: **Go to [KEEP Liquidity Rewards Dashboard](https://dashboard.keep.network/liquidity)

**Step 2: **Connect your wallet

![](https://lh5.googleusercontent.com/5NMf0iiwGiO7CUv6WK4Eq8AOng9meiuA5166qw3Uoz-fya0dwxu2S\_Q6nsFBekGwz6OqFTLeYQ9Kf7GIqfd7tDQ6eVb\_jHxPRe5KTXMX00pAwpPaME8ALiC8WQnNLq3HhLNYFEQ)

**Step 3: **Scroll down and select **TBTC V2 + SADDLE **pool

**Step 4: **Enter the amount of KEEP tokens to stake and click DEPOSIT

![](https://lh6.googleusercontent.com/38cpxpgO33vDyL26QTsGfRcwM1F884LQuzuTULstnyHOozsptRvyy-SY35MIEq-GNbS3v2X-JVq8tTRH9P8Zz7k-Dh-l\_v4l2WLHzlk3Ucelxw3N1k5TzxyUuHQoKIBKo3S\_6yY)

**Step 5: **Start earning incentives

**Note: If you are migrating from BTC Pool, you must manually migrate your KEEP rewards. Check out the migration **[**guide**](https://docs.saddle.finance/saddle-incentives#migrating-incentives-to-tbtc-metapool)**.**

## **wCUSD Metapool**

Saddle rewards you with trading fees when you provide liquidity to the wCUSD metapool. If you observe “-” in the Saddle dApp frontend, it means there has not been any trading volume over the last 24 hours to calculate the APY.

\*\*\*\*
