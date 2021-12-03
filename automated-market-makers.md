---
description: >-
  AMMs democratized cryptocurrency trading by doing away with order books and
  institutional market makers.
---

# Automated Market Makers

## **MARKETS**

Markets facilitate trade in a society by connecting the sellers to the buyers. Trading of goods, services, or information (assets collectively) happens in a purpose-built marketplace. For instance, a local community might have a farmers’ market to trade locally produced vegetables and fruits. Whilst a stock market like New York Stock Exchange (NYSE) allows global participants to trade in stocks. A traditional market comprises buyers, sellers, brokers-dealers, and market makers.

Let’s look at the fundamentals first.

_**Buyer**:_ A person or an organization buying, planning to buy, or agrees to buy assets.

_**Seller**:_ A person or an organization selling, planning to sell, or agrees to sell assets.

_**Broker-Dealer**:_ A person or an organization buying and/or selling on behalf of its customers or for their own. The person/organization acts as a _broker (or agent)_ when executing orders on behalf of the client and acts as a _dealer (or principal)_ when trades for their own account.

_**Bid:**_ Buyers make a bid, specifying the price they will pay and the quantity required.

_**Ask:**_ Sellers offer an ask price, specifying the price they will sell and the quantity available.

_**Bid-Ask Spread**_: The difference between the Ask and the Bid. For example, if the sellers’ ask is $55 and the buyers’ bid is $53, the bid-ask spread is $2. The bid-ask spread determines the market liquidity. For heavily traded assets, the bid-ask spread will be tighter (narrow). However, for assets with little demand or sparsely traded, the bid-ask spread may be high or even unknown.

_**Liquidity:**_ Refers to how easily and quickly assets are bought or sold _without_ affecting the asset's price. If there is a high volume of trade, the bid-ask spread should be narrow for the asset traded. Therefore, liquid. Contrarily, when there is a wide (or unknown) bid-ask spread, then the asset is illiquid.

_**Market Maker**:_ Market makers (MM) help keep the market functioning by actively buying and selling assets. MMs can be an individual or an organization providing liquidity to the market by transacting on both sides of the market (buy and sell). For example, the MM might offer a Bid for $20/stock and Ask for $20.05/stock. Market makers earn a profit through the bid-ask spread and carry a risk of price variations during Buy-Hold-Sell cycle. The common type of market maker are the brokerage houses.

_**Slippage**_: Slippage results from a change in bid-ask spread. There is a time delay between the trade request and execution in the market. During this time, if the bid-ask spread changes, then slippage occurs.

_**Order Book**:_ Most modern financial markets are order-driven (buy-sell) markets. At the heart of the trade is an order book; an electronic register of the list of buy and sell orders. A typical order book has three parts – buy orders, sell orders, and order history. The order book helps improve market transparency, help traders make informed decisions, and identifies participants and price of a trade.

_**Exchange**_: Exchange is a market where trading is conducted. For example, New York Stock Exchange (NYSE), London Stock Exchange (LSE), or the Cryptocurrency exchanges like Saddle, Binance, Coinbase, or Uniswap.

## **CRYPTOCURRENCY EXCHANGES**

A cryptocurrency exchange is a marketplace for trading cryptocurrencies. Broadly, two types of cryptocurrency exchanges exist:

_**Centralized Exchanges (CEX)**_: A cryptocurrency exchange owned and governed by a 3rd party. E.g., Binance, Coinbase, and Bitfinex.

_**Decentralized Exchanges (DEX)**_: A cryptocurrency exchange, unlike CEX, is not owned or governed by a 3rd party. A DEX acts as a peer-to-peer (P2P) platform, facilitating trade with no central party. E.g., [Saddle](https://saddle.exchange/#/), Uniswap, Sushiswap, and Mdex.

The DEX ecosystem is nascent and maturing. Despite few shortcomings, compared to CEX, decentralized exchanges grew in popularity. The allure of removing middlemen, lower fees, and decentralization pushed the adoption of DEX.

### **Order Book Challenges**

The early version of the cryptocurrency exchanges used the order book model, like traditional exchanges. The order book model works well where the trade volumes and liquidity are high, resulting in lower [slippages](https://docs.saddle.finance/saddle-faq#what-is-max-slippage). Leading cryptocurrencies, like Bitcoin and Ethereum, have high volumes of trade. While other cryptocurrencies and tokens, which don’t have high volumes, faced challenges with the order book model.

In the illustration below, the seller's Ask is $20.50 and the buyer's Bids are not closer to the Ask. This results in a liquidity challenge. Market makers, therefore, step in to keep the market functioning by actively buying and selling assets - i.e., transacting on both sides to keep the market functioning. The market makers carry the risk of a price variation during Buy-Hold-Sell cycle.

![](<.gitbook/assets/0 (4).png>)

The main issue is related to high slippages and volatility due to low volumes of trade. The absence of market makers round the clock further constrained the liquidity. Automated Market Makers (AMM), therefore, emerged as a solution to the order book challenge.

## **AUTOMATED MARKET MAKER (AMM)**

Market makers are essential in an exchange to provide liquidity, control spreads, and maintain slippages. Since cryptocurrency exchanges work 24x7, the need for automated market makers rose. AMMs democratized cryptocurrency trading by doing away with order books and institutional market makers. Instead, AMMs execute trade automatically using [algorithms ](https://docs.saddle.finance/saddle-faq#how-does-saddle-work)and [liquidity pools](https://docs.saddle.finance/saddle-faq#what-is-a-saddle-pool). Let’s understand a few basic concepts first.

_**Permissionless:**_ Unlike traditional exchanges, permission-less networks require no permission to join and interact with the blockchain network. Permission-less AMMs allow anyone with an internet connection to become a part of the market to trade.

_**Liquidity Pools**_: Instead of an order book, AMMs use liquidity pools to facilitate trade. Liquidity pool, a smart contract, is a fund of tokens (or coins). In AMMs, traders interact with the smart contracts, to enable liquidity and price discovery. Because of the permissionless nature, AMMs allow anyone to provide liquidity to the liquidity pool. The liquidity pool smart contract holds two or more tokens and allows anyone to deposit and withdraw funds from them, but only according to specific mathematical rules.

_**Liquidity Providers**_: Liquidity providers contribute assets (cryptocurrency tokens and coins) to liquidity pools. In exchange for providing the tokens, the LPs normally earn a fee. Now, when a trade executes on an AMM, the trade executes against the liquidity pool. This eliminates the need for an order book and for the buyer and seller to be present at that moment in time.

_**Algorithm**_: AMMs use an [algorithm ](https://docs.saddle.finance/automated-market-makers#amm-swap-algorithms)(mathematical formula) for pricing the assets, thus replacing the order book mechanism. There are variations of the pricing formula deployed currently, which we will cover later.

_**Yield Farming**_: [Yield farming](https://docs.saddle.finance/saddle-faq#what-is-yield-farming) is an incentive mechanism to put an individual’s cryptocurrency assets to work and generate high returns. Liquidity providers, in yield farming protocols, stake or lock up their assets to earn rewards and higher interests.

![](<.gitbook/assets/1 (2) (1).png>)

_**Impermanent Loss**_: Though the AMM model offers better stability and returns, there is a risk of impermanent loss – a temporary loss experienced by liquidity providers because of volatility in the liquidity pool assets. In simple terms, if the liquidity provider had held onto the asset, without providing it as a liquidity to the pool, the individuals would have had more money/value. But impermanent loss is a temporary situation as the AMMs regulate the price closer to market, eventually.

## **AMM SWAP ALGORITHMS**

Having understood what AMMs are, let’s now deconstruct them. You can think of an AMM as a friendly and obedient market maker bot, always willing to quote a price, no matter the time of the day or day of the week.

To quote you a price, the bot uses a mathematical formula (used interchangeably with pricing algorithm or swap algorithm) and works relentlessly in the background. The algorithm implemented varies from the simplex to the complex. We’ll look at the commonly used swap algorithms, including the [StableSwap algorithm](https://docs.saddle.finance/automated-market-makers#stableswap-algorithm) used by Saddle.

### **Constant Product Formula**

Constant product formula is probably the simplest and the earliest algorithm to come into the market. Uniswap popularized the mathematical formula:

**x \* y = k**

where **x** is the amount of Token#1 in the liquidity pool, **y** is the amount of Token#2 in the liquidity pool, and **k** is a fixed constant.

Let’s look at a few critical aspects from the example below. An ETH-USDT liquidity pool is set-up with 100 ETH and 300,000 USDT, provided by the liquidity providers. As the pool is set-up, the initial conditions are:

|                     |                    |                   |                      |
| ------------------- | ------------------ | ----------------- | -------------------- |
| **USDT: ETH PRICE** | **USDT Liquidity** | **ETH Liquidity** | **Constant Product** |
| 3000 : 1            | 300,000            | 100               | 30,000,000           |
| **Initial price**   | **x**              | **y**             | **k**                |

When a trader wants to swap the tokens in the pool, the formula will try to achieve the constant product equilibrium. For example, if a trader wants to swap USDT for 1 ETH, then to maintain a constant product of 30,000,000 the price quoted for USDT will be 3,030.30 (a premium of 1% over the initial setup price) and the liquid pool composition after the swap will be:

|                     |                    |                   |                      |
| ------------------- | ------------------ | ----------------- | -------------------- |
| **USDT: ETH PRICE** | **USDT Liquidity** | **ETH Liquidity** | **Constant Product** |
| 3030.30 : 1         | 303,030.30         | 99                | 30,000,000           |
| **1% premium**      | **x**              | **y**             | **k**                |

Likewise, if a trader wants to swap USDT for 5 ETH, the price quoted by the algorithm will be 3,157.89 (a premium of 5.3% over the initial setup price) and the liquid pool composition after the swap will be:

|                     |                    |                   |                      |
| ------------------- | ------------------ | ----------------- | -------------------- |
| **USDT: ETH PRICE** | **USDT Liquidity** | **ETH Liquidity** | **Constant Product** |
| 3157.89 : 1         | 315,789.47         | 95                | 30,000,000           |
| **5.26% premium**   | **x**              | **y**             | **k**                |

Uniswap first implemented the constant product formula and Balancer refined it with a generalized formula. But there is a challenge.

The constant product formula determines the price when someone trades against the liquidity pool. As we see from the chart below, we calculate the price as a ratio of the tokens in the pool. The pricing curve has a hyperbola when plotted against two tokens. When someone withdraws, say Token#1, the proportionate Token#2 to be deposited, to maintain the constant product, varies.

![](<.gitbook/assets/2 (7).png>)

Given the volatile nature of cryptocurrency, the market price of the tokens also fluctuates. The constant product formula _does not update_ the price of the tokens in the pool with the market movement. In certain cases, the price update is a simple [off-chain observation](https://docs.uniswap.org/protocol/V2/concepts/advanced-topics/pricing). This resulted in the risk of higher slippages.

Thanks to [arbitrageurs](https://docs.balancer.fi/core-concepts/protocol/pools#weighted-pools), once they find a cheaper price, they’ll move the funds around liquid pools for profit making. Eventually, the price in the liquidity pools starts stabilizing closer to the market price. This does not, however, eliminate the slippage challenge in full.

### **Constant Sum Formula**

To address the slippage issue, AMMs explored the constant sum formula as an option. Constant sum formula solves for the equation:

**x + y = k**

where **x** is the amount of Token#1 in the liquidity pool, **y** is the amount of Token#2 in the liquidity pool, and **k** is a fixed constant.

While the constant sum formula solves the slippage problem, it provides only _fixed liquidity_. For markets to function well, they need a constant supply of liquidity and hence this model didn’t suit the purpose well.

![](<.gitbook/assets/3 (2).png>)

### **Stableswap Algorithm**

The innovation into AMMs mathematical formula continued to find a solution to the slippage (constant product formula) and fixed liquidity (constant sum formula) problems. Hybrid mathematical models, combining the best of many models, rose to prominence. One such model is the Stableswap algorithm.

First introduced by [Curve](https://curve.fi/whitepaper), the Stableswap is a hybrid algorithm. The Stableswap hybrid combines both Constant Product and Constant Sum models, and the following chart shows the Stableswap algorithm in relation to constant product and constant sum invariants.

![](<.gitbook/assets/4 (1).png>)

- **Constant Sum:** When the liquidity pool portfolio is balanced, the algorithm functions as a Constant Sum formula; **x + y = k**. You can observe the StableSwap _**blue line**_ staying close to the Constant Sum _**red line**_, and the price is stable.
- **Constant Product:** As the liquidity pool portfolio becomes imbalanced, the StableSwap algorithm functions as a Constant Product formula; **x \* y = k**. You can observe the StableSwap _**blue line**_ now resembling the Constant Product _**purple line**_, and the price becoming expensive.

## **PEGGED-VALUE ASSETS**

Saddle liquidity pools implement the StableSwap mathematical formula to reduce slippage and keep the market liquid. Saddle facilitates trades of stablecoins, where the price is [pegged ](https://docs.saddle.finance/saddle-faq#pegged-value-assets)to an underlying asset, bringing in further stability. For example:

_**USDT**_: A stablecoin pegged 1:1 to the USD fiat currency as the underlying asset.

_**DAI**_: A stablecoin soft pegged to the USD algorithmically.

_**FRAX**_: A fractional-algorithmic stablecoin that is partially backed by collateral and partially stabilized algorithmically.

_**wBTC**_: An ERC20 token backed 1:1 by the actual Bitcoin.

_**alETH**_: An ERC20 token, but backed 4:1 by ETH.

### **Dynamic Pegs**

The Constant Product formula _does not update_ the price of the tokens in the pool with the market movement. The Stableswap formula motivates swaps around price ratio 1.0, well suited for stablecoins. Dynamic pegs are the next evolution of AMMs.

Dynamic pegs will bring the benefits of Stableswaps to cryptocurrency assets which aren’t pegged to another asset. By using an automatic price change mechanism, the algorithm will move the price based on real-time profit margin calculations, to adjust for slippages. Thus, benefiting both the traders and the AMMs.
