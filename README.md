# About Saddle

Saddle is an automated market maker \(AMM\) designed to enable efficient trading between pegged value crypto assets. Saddle is launching with a tokenized bitcoin pool, allowing users to trade between and provide liquidity for tBTC, WBTC, sBTC, and renBTC.

Saddle recently spun out of Thesis, the crypto venture studio behind projects like [tBTC](https://tbtc.network/), [Keep](https://keep.network/), and [Fold](https://foldapp.com/).

## Understanding pegged value crypto assets

### What are pegged value crypto assets?

Pegged value crypto assets are tokens that have their value pegged to an underlying asset by some means. For example, the value of a stablecoin or tokenized bitcoin is supposed to be $1 or 1 BTC, respectively.

However, pegged value crypto assets fix this value using different mechanisms. Some assets, like Synthetix sBTC or sUSD, maintain their peg synthetically \(in this case, via collateralization of SNX\). Other assets maintain their peg by being backed by and redeemable for the actual underlying asset, either permissionlessly \(e.g. tBTC\) or through a centralized custodian \(e.g. WBTC, USDC\).

These different approaches and the associated risks are why the prices of pegged value crypto assets of the same type can vary slightly.

### What’s the issue with pegged value crypto assets?

Trading among and in between these types of assets can be expensive and inefficient, resulting in lost capital due to high slippage and transaction fees.

### How does Saddle solve it?

Saddle solves the pegged value crypto asset trading problem by offering an AMM specifically tailored to allow users to trade in between these assets with minimal slippage.

## Saddle’s Solution

### Bitcoin as a First-class Citizen

Bitcoin is the largest cryptocurrency by market capitalization, and the amount of tokenized BTC on Ethereum has been exploding - the supply has increased [~135X in 2020](https://btconethereum.com/). Despite this growth, tokenized BTC is often not a priority when it comes to features and support. We believe bitcoin deserves to be treated as a first-class citizen in DeFi.

### Virtual Synth Support

Virtual Synths are a new Synthetix feature introduced in [SIP-89](https://sips.synthetix.io/sips/sip-89). SNX founder Kain Warwick provides a great overview of their potential in his post "[Virtual Synths and where to find them](https://blog.synthetix.io/virtual-synths/)". In short, Virtual Synths will enable large, low slippage trades between any asset supported by Saddle. We are actively working on this integration and will have more details to share in the near future. Virtual Synths are the key to achieving our mission of unlocking deep on-chain liquidity between pegged value crypto assets, and we aim to become the premier on/off-ramp for the Synthetix ecosystem.

### Incentivized LP Retention

DeFi protocols are still iterating on how to properly incentivize and retain liquidity providers \(LPs\). One common approach has been to add a fixed percentage fee to withdrawals \(e.g. Yearn Vaults\). However, this mechanism doesn’t reward long-term liquidity providers. Saddle fixes this by implementing a configurable withdrawal fee that linearly decays to 0 over one month. This fee will be disabled at launch until further notice. We are presently working on several other ways to incentivize LPs, stay tuned!

### Security

The security of user funds is our top priority. Saddle is built on [our new Solidity implementation](https://github.com/saddle-finance/saddle-contract) of the [StableSwap](https://www.curve.fi/stableswap-paper.pdf) algorithm. Deploying new code that deals with money requires extra care and scrutiny, which is why we conducted three back-to-back smart contract audits with [Certik](https://certik.foundation/), [Quantstamp](https://quantstamp.com/), and [Open Zeppelin](https://openzeppelin.com/). Read the audits [here](https://github.com/saddle-finance/saddle-audits). This is also why we are doing a [guarded launch](https://medium.com/electric-capital/derisking-defi-guarded-launches-2600ce730e0a) called Proof of Governance.

## Keeping up with Saddle

Find us on [Discord](https://discord.gg/hX8RZFBW9R), [Twitter](https://twitter.com/saddlefinance), [Telegram](https://t.me/saddle_finance), [Github](https://github.com/saddle-finance), and [Medium](https://medium.com/saddle).

