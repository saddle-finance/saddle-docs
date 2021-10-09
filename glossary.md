---
description: Terms and definitions used across Saddle.
---

# Glossary

This Glossary consists of terms and definitions used across Saddle. The objective of this section is to build a common vocabulary for ease of reference and knowledge.

## **MARKET**

_**Buyer**:_ A person or an organization buying, planning to buy, or agrees to buy assets.

_**Seller**:_ A person or an organization selling, planning to sell, or agrees to sell assets.

_**Broker-Dealer**:_ A person or an organization buying and/or selling on behalf of its customers or for their own. The person/organization acts as a _broker \(or agent\)_ when executing orders on behalf of the client and acts as a _dealer \(or principal\)_ when trades for their own account.

_**Supply & Demand:**_ Supply and demand form the foundation for markets. Supply and demand directly affect the price of the traded asset. Buyers typically look for the lowest price and sellers the highest. Markets are where buyers and sellers strive to achieve a proper balance \(exceptional situations excluded\).

_**Bid:**_ Buyers make a bid, specifying the price they will pay and the quantity required.

_**Ask:**_ Sellers offer an ask price, specifying the price they will sell and the quantity available.

_**Bid-Ask Spread**_: The difference between the Ask and the Bid. For example, if the sellers’ ask is $55 and the buyers’ bid is $53, the bid-ask spread is $2. The bid-ask spread determines the market liquidity. For heavily traded assets, the bid-ask spread will be tighter \(narrow\). However, for assets with little demand or sparsely traded, the bid-ask spread may be high or even unknown.

_**Liquidity:**_ Refers to how easily and quickly assets are bought or sold _without_ affecting the asset's price. If there is a high volume of trade, the bid-ask spread should be narrow for the asset traded. Therefore, liquid. Contrarily, when there is a wide \(or unknown\) bid-ask spread, then the asset is illiquid.

_**Market Maker**:_ Market makers \(MM\) help keep the market functioning by actively buying and selling assets. MMs can be an individual or an organization providing liquidity to the market by transacting on both sides of the market \(buy and sell\). For example, the MM might offer a Bid for $20/stock and Ask for $20.05/stock. Market makers earn a profit through the bid-ask spread and carry a risk of price variations during Buy-Hold-Sell cycle. The common type of market maker are the brokerage houses.

_**Slippage**_: Slippage is the difference between the expected price of a trade and the execution price. This happens as there is a time delay between the trade request and execution in the market. Slippage results from a change in bid-ask spread. During this time, if the bid-ask spread changes, then slippage occurs. Slippage can occur at any time but is amplified during periods of high volatility and with large volume trades.

_**Order Book**:_ Most modern financial markets are order-driven \(buy-sell\) markets. At the heart of the trade is an order book; an electronic register of the list of buy and sell orders. A typical order book has three parts – buy orders, sell orders, and order history. The order book helps improve market transparency, help traders make informed decisions, and identifies participants and price of a trade.

_**Exchange**_: Exchange is a market where trading is conducted. For example, New York Stock Exchange \(NYSE\), London Stock Exchange \(LSE\), or the Cryptocurrency exchanges like Saddle, Binance, Coinbase, or Uniswap.

## **CRYPTOCURRENCY EXCHANGE**

_**Cryptocurrency Exchange**_: A cryptocurrency exchange is a marketplace for trading cryptocurrencies. Broadly, two types of cryptocurrency exchanges exist:

_**Centralized Exchanges \(CEX\)**_: A cryptocurrency exchange owned and governed by a 3rd party. E.g., Binance, Coinbase, and Bitfinex.

_**Decentralized Exchanges \(DEX\)**_: A cryptocurrency exchange, unlike CEX, is not owned or governed by a 3rd party. A DEX acts as a peer-to-peer \(P2P\) platform, facilitating trade with no central party. E.g., Saddle, Uniswap, Sushiswap, and Mdex.

_**Automated Market Makers \(AMM\)**_: Market makers are essential in an exchange to provide liquidity, control spreads, and maintain slippages. Since cryptocurrency exchanges work 24x7, the need for automated market makers rose. AMMs democratized cryptocurrency trading by doing away with order books and institutional market makers. Instead, AMMs execute trade automatically using algorithms and liquidity pools.

_**Permissionless:**_ Unlike traditional exchanges, permissionless networks require no permission to join and interact with the blockchain network. Permissionless AMMs allow anyone with an internet connection to become a part of the market to trade.

_**Liquidity Pools**_: Instead of an order book, AMMs use liquidity pools to facilitate trade. Liquidity pool, a smart contract, is a fund of tokens \(or coins\). In AMMs, traders interact with the smart contracts, to enable liquidity and price discovery. Because of the permissionless nature, AMMs allow anyone to provide liquidity to the liquidity pool. The liquidity pool smart contract holds two or more tokens and allows anyone to deposit and withdraw funds from them, but only according to specific mathematical rules.

_**Liquidity Providers**_: Liquidity providers contribute assets \(cryptocurrency tokens and coins\) to liquidity pools. In exchange for providing the tokens, the LPs normally earn a fee. Now, when a trade executes on an AMM, the trade executes against the liquidity pool. This eliminates the need for an order book and for the buyer and seller to be present at that moment in time.

_**Yield Farming**_: Yield farming is an incentive mechanism to put an individual’s cryptocurrency assets to work and generate high returns. Liquidity providers, in yield farming protocols, stake or lock up their assets to earn rewards and higher interests.

_**Constant Product Formula**_: Constant product formula is probably the simplest and the earliest algorithm to come into the market. Uniswap popularized the mathematical formula: x \* y = k, where x is the amount of Token\#1 in the liquidity pool, y is the amount of Token\#2 in the liquidity pool, and k is a fixed constant.

_**Constant Sum Formula:**_ Constant sum formula solves for the equation: x + y = k, where **x** is the amount of Token\#1 in the liquidity pool, **y** is the amount of Token\#2 in the liquidity pool, and **k** is a fixed constant.

_**StableSwap:**_ First introduced by [Curve](https://curve.fi/whitepaper), the Stableswap is a hybrid algorithm. The Stableswap hybrid combines both Constant Product and Constant Sum models. When the liquidity pool portfolio is balanced, the algorithm functions as a Constant Sum formula; **x + y = k**. As the liquidity pool portfolio becomes imbalanced, the StableSwap algorithm functions as a Constant Product formula; **x \* y = k**.

## **PEGGED-VALUE ASSETS**

_**Pegged-Value Assets**_: Saddle facilitates trades of pegged-value assets, where the price is pegged to an underlying asset, bringing in stability to the price in an otherwise volatile cryptocurrency market.

_**Stablecoin:**_ Stablecoins \(e.g., USDT, USDC, DAI\) are a good example of pegged value assets. The value of the stablecoin is fixed to an asset such as a fiat currency \(e.g., 1 DAI = 1 US$\).

_**Dynamic Pegs**_: Dynamic pegs are the next evolution of AMMs. Dynamic pegs will bring the benefits of Stableswaps to cryptocurrency assets which aren’t pegged to another asset. By using an automatic price change mechanism, the algorithm will move the price based on real-time profit margin calculations, to adjust for slippages.

### Pegged-Value Assets in Saddle Pools

_**alETH**_: alETH is an ERC20 token, backed 4:1 by ETH.

_**alUSD**_: A yield-backed synthetic stablecoin minted via Alchemix Finance, a DAO-governed synthetic asset platform.

_**DAI**_: DAI is soft pegged to the USD algorithmically.

_**FEI**_: A scalable and decentralized stablecoin that leverages protocol-controlled value \(PCV\) for peg maintenance while maintaining highly liquid secondary markets.

_**FRAX**_: A fractional-algorithmic stablecoin that is partially backed by collateral and partially stabilized algorithmically.

_**LUSD**_: The USD-pegged stablecoin of the Liquity decentralized borrowing protocol.

_**renBTC**_: renBTC is an ERC20 token backed 1:1 by Bitcoin. Ren also decentralizes the custody of the BTC.

_**sBTC**_: sBTC differs from the rest, as Bitcoins does not back it. The value of sBTC is kept stable through an over-collateralization mechanism leveraging Synthetix SNX tokens.

_**sETH**_: sETH is a short position built through the dYdX protocol and can be traded like any ERC20 token. sETH is tied to USD-backed stablecoin DAI.

_**sUSD**_: A synthetic stablecoin on the Synthetix platform, whose value tracks the US Dollar.

_**tBTC**_: tBTC is backed 1:1 by Bitcoin and truly decentralized.

_**USDC**_: USDC is an ERC20 token pegged 1:1 to the US dollars \(USD\)

_**USDT**_: USDT, like USDC, is pegged 1:1 to the USD.

_**wBTC**_: Wrapped BTC is an ERC20 token backed 1:1 by the actual Bitcoin.

_**wCUSD:**_ Wrapped Celo Dollars is an ERC20 token representing a 1:1 share of Celo Dollar.

_**WETH**_: Wrapped ETH is an ERC20 token backed 1:1 by ETH, allowing trade directly with ALT coins.

## **SADDLE POOL**

_**Saddle Pools**_: Saddle Pools are the liquidity pools in Saddle Finance. Saddle pools are of two types – base and metapools.

_**Base pools:**_ Base pools contain two or more tokens and Saddle base pools implement the StableSwap algorithm.

_**Metapools:**_ These pools contain one token to trade with another underlying Base pool. For example, in the sUSD Pool, we pool the single token sUSD alongside Stablecoin Pool V2 \(DAI, USDC, USDT\). Adding the single asset to the metapool, however, does not dilute the liquidity of the underlying base pool.

_**BTC Pool**_: Saddle BTC pool currently supports four wrapped variants of Bitcoin, enabling Bitcoin users to take part in the Ethereum DeFi ecosystem.

_**alETH Pool**_: The ETH pool on Saddle is of alETH – a synthetic ETH backed asset by Alchemix. alETH is a multi-pool currently supporting three variants of Ethereum, enabling seamless and cheap switch between pegged-value ETH assets \(backed or wrapped\).

_**Stablecoin Pool V2**_: The Stablecoin pool contains three stablecoins, unlocking deep on-chain liquidity between pegged value crypto assets.

_**D4 Pool**_: The Saddle D4 \(decentralized\) pool consists entirely of permissionless, decentralized stablecoins. Stablecoins like USDC, USDT, and Dai are not permissionless – centralized organizations manage them with varying degrees of transparency.

_**sUSD Pool**_: The Saddle sUSD Pool is a metapool. In this pool, we pooled the single token sUSD alongside Stablecoin Pool V2 \(DAI, USDC, USDT\). Adding the single asset to the metapool, however, does not dilute the liquidity of the underlying base pool.

_**saddleUSD-V2**_: A base pool \(Stablecoin Pool V2\) on Saddle comprising the stablecoins USDT, USDC, and DAI.

_**wCUSD Pool**_: A metapool. In this pool, we pooled the single token wCUSD alongside Stablecoin Pool V2 \(DAI, USDC, USDT\).

## **SADDLE VIRTUAL SWAPS**

_**Virtual swaps V1**_: A key property of synths is we can exchange them with extremely low slippage. For example, to bridge USD, ETH, and BTC pools, synths can act as a common asset. We can exchange the synths with infinite liquidity, allowing them to act as a _liquid bridge_ between any pool that contains sUSD, sBTC, or sETH. The issue is, Synthetix’s fee reclamation and rebate mechanism [prevents](https://research.synthetix.io/t/virtual-synths-sip/202) atomic transactions \(to mitigate front running of oracle price updates\) for a Synth &lt;&gt; Synth exchange, breaking composability.

_**Virtual swaps V2**_: Virtual swaps \(Saddle Synths V2\) are a new feature in Saddle pools leveraging Synthetix’s vSynths. With the implementation of vSynth logic in Saddle’s AMM, it’s possible to use synths as _bridges between pools_. The advantages of Virtual swaps V2 over V1 are the support for atomic transactions - aggregators can now be used without breaking the transaction flow. _**Note:** Currently, Virtual Swaps V2 are not live yet._

_**Synths**_: Synths differ from asset backed cryptocurrencies like stablecoins. For instance, US Dollars back DAI stablecoin. If you own 1 DAI, then in a way you own US$ 1. But owning sBTC synth doesn’t mean you own the equivalent Bitcoin. Rather, the owner only has the exposure to the BTC price. Synthetix works on an _over-collateralization_ model; each synth is collateralized by more value than it represents to absorb any sharp price changes.

_**Front-Running**_: While synths are great, they came with a limitation. Front-running. Many decentralized exchanges \(DEX\) suffer from front-running. Because of constraints on Ethereum, there is a latency and cost in sourcing and updating the real-world asset price for the synths. [Front-runners](https://en.wikipedia.org/wiki/Front_running) can see the difference between price of the asset in the real-world and on-chain. They see an arbitrage opportunity and over-pay for Ethereum gas fee to prioritize their orders in the queue, before the on-chain price reflects the real-world.

_**Composability**_: In DeFi, composability is the ability of open-source protocols to interact and combine creatively to form new products and services. There are two key aspects for composability to work Standardization and Atomicity.

_**Standardization**_: The ability of DeFi protocols to connect and communicate in a standardized and open way.

_**Atomicity**_: The need for the DeFi protocols to connect instantly within a single transaction.

## **SADDLE FEES**

_**Trading fee**:_ The trading fee applies to every trade and the prevailing fee is displayed in the pool information. Typically, the fee is 0.04%. However, the fee may vary depending on the pool.

_**Admin fee**:_ The admin fee is calculated as a % of the trading fee.

_**Gas fee**:_ The fee payable to Ethereum network to confirm the transactions. The gas fee varies depending on the speed of confirmation time required and represented in gwei \(1 gwei = 10`-9` ETH\).

_**Flash Loan Fees**_: Some of the Saddle pools support flash loans. The flash loan fees, typically 0.08%, are a part of the trading fees earned by liquidity providers.

## **INCENTIVES**

_**Earned Fees**_: Any earnings of Trading Fees and/or Flash Loan Fees from providing liquidity to the Saddle pools.

_**Incentives**_: The incentives from the Saddle protocol and/or partners protocols. For e.g., KEEP, ALCX. _Note: Currently there are no Saddle protocol specific incentives._

_**Rewards**_: Refers collectively to both earned fees and incentives.

_**Annual Percentage Yield \(APY\)**_**:** APY refers to the amount of interest a liquidity provider earns over one year. APY is like an interest rate, but the biggest benefit of APY is the _compounding_.

_**Annual Percentage Rate \(APR\)**_**:** APR does not factor compounding and represents the annual interest rate.

_**LP Tokens**_: Liquidity provider tokens or LP tokens are tokens issued to liquidity providers. LP tokens are used to track individual contributions \(proportional share of liquidity\) to the overall liquidity pool. For example, if you provide liquidity to Saddle BTC Pool V2, you’ll receive _**saddleBTC-V2**_ LP tokens.

_**Staking LP Tokens**_: Staking is the process of locking LP tokens in a cryptocurrency wallet to support the operations of the crypto network. By staking LP tokens, stakers gain rewards from the network.

_**KEEP Rewards**_: Once you provide liquidity to the BTC pool, you will receive KEEP LP tokens representing your share of the liquidity pool. You can further stake the KEEP LP tokens to earn rewards.

_**ALCX Rewards**_: Once you provide liquidity to the alETH pool, you will receive ALCX LP tokens representing your share of the liquidity pool. You can further stake the ALCX LP tokens to earn rewards.

_**ALCX/FXS/LQTY/TRIBE Rewards**_: Once you provide liquidity to the D4 pool, you will receive four LP tokens \(ALCX/FXS/LQTY/TRIBE\) representing your share of the liquidity pool. You can further stake the LP tokens to earn rewards.
