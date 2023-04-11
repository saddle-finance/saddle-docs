---
description: >-
  Frequently asked questions on Saddle Finance, Liquidity Pools, Pegged Assets,
  Rewards and Incentives.
---

# Saddle FAQ

## **GENERAL**

Frequently asked questions and answers regarding Saddle Finance. Still have questions? [Join our Discord](https://discord.gg/hX8RZFBW9R).

### **What is Saddle?**

Saddle is a decentralized automated market maker ([AMM](https://docs.saddle.finance/automated-market-makers)) on the Ethereum blockchain, optimized for trading [pegged value crypto assets](https://docs.saddle.finance/saddle-faq#what-are-pegged-value-crypto-assets-pegged-assets) with [minimal slippage](https://docs.saddle.finance/saddle-faq#what-is-a-slippage). Saddle enables cheap, efficient, swift, and low-slippage swaps for traders and high-yield pools for LPs. We believe in [collaboration](https://docs.saddle.finance/build-with-saddle), in building Saddle as a DeFi lego block, in helping DeFi teams bring AMMs to any blockchain.

### **Why Saddle?**

_**Saddle stands for DeFi**_: We commit ourselves to [open-source software](https://github.com/saddle-finance) and collaboration to fulfil the promise of DeFi, of financial Lego blocks.

_**Saddle is safe & legit**_: Saddle protocol is audited and secured by leading blockchain security firms like Certik, Quantstamp, and OpenZeppelin. Read the audits [here](https://github.com/saddle-finance/saddle-audits).

_**Saddle is collaborative and fun to work with**_: We root our ethos in the desire to [support ](https://docs.saddle.finance/build-with-saddle)the DeFi ecosystem and partner with like-minded protocols.

### **Who built Saddle?**

Saddle is built by DeFi natives with prior years of developer experience at Web2 companies like Uber, Amazon, and Square. As regular DeFi users ourselves, we’ve seen first-hand how important an active and vibrant community is for a project’s success. We know Web2, but we know Web3 better.

You might have interacted with our founder [Sunil](https://www.linkedin.com/in/sunilsrivatsa/) (aka [devops199fan](https://twitter.com/devops199fan)) in the YFI community (he’s a multisig signer), or used tools created by members of our team, like [yieldfarming.info](https://yieldfarming.info) by [John](https://www.linkedin.com/in/jongseunglim/) (aka [Weeb_Mcgee](https://twitter.com/Weeb_Mcgee)).

### **Where can I find Saddle's logo or brand assets?**

You can download Saddle's logo, guidelines, and brand assets from [here](https://drive.google.com/drive/folders/13rTY6x24crioqOgyGCE6zJo0197AMVtD?usp=share_link).

### **How does Saddle work?**

Saddle is an automated market maker (AMM) enabling trading between pegged value crypto assets. Saddle liquidity pools implement the StableSwap mathematical formula to reduce slippage and keep the market liquid. First introduced by [Curve](https://curve.fi/whitepaper), Stableswap is a hybrid algorithm. The Stableswap hybrid combines both Constant Product and Constant Sum models.

For more on AMMs and Stableswap check out the [AMM section](https://docs.saddle.finance/automated-market-makers).

{% hint style="info" %}
Find Saddle's StableSwap implementation code [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/Swap.sol)
{% endhint %}

### **Does Saddle have a token?**

Yes, Saddle's token is the SDL token, you can learn more about it in the [SDL Token section](sdl-token.md).

{% hint style="info" %}
Find SDL token code [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/SDL.sol)
{% endhint %}

### Where can I trade SDL?

SDL is non-transferrable for 3-12 months following launch (depending on governance). During the lockup period, SDL is not tradable.

{% hint style="info" %}
Find SDL token vesting code [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/Vesting.sol) and [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/RetroactiveVesting.sol)
{% endhint %}

### **What is the price of SDL?**

SDL is non-transferrable for 3-12 months following launch (depending on governance). During the lockup period, SDL is not tradable, so it does not have a price.

### **Who can use Saddle?**

Anyone and everyone. All you need to use Saddle is an internet connection and a ERC-20 compatible wallet like [Metamask](https://metamask.io).

### **How do I use Saddle?**

With Saddle, there are two general actions users can take: [swap assets](https://saddle.exchange/#/) or [provide liquidity](https://saddle.exchange/#/pools).

- _**Swapping**_ between two assets on Saddle gives users efficient trading and low slippage.

{% embed url="https://www.youtube.com/embed/8XE5ErpfhQo?feature=oembed" %}

- _**Providing liquidity**_ by depositing assets into a pool on Saddle allows users to take part in the protocol as liquidity providers and earn reward incentives.

{% embed url="https://www.youtube.com/embed/RCsBinGAZEg?feature=oembed" %}

Head to the [Saddle d](https://saddle.exchange)[App](https://saddle.exchange) and start using it now!

### **Are there alternate front ends for Saddle protocol?**

There are several frontends available:

| **FRONT END** | **LINK**                                                                     |
| ------------- | ---------------------------------------------------------------------------- |
| Main dApp     | [https://saddle.exchange/](https://saddle.exchange)                          |
| ENS           | [https://saddlefinance.eth.link/](https://saddlefinance.eth.link)            |
| Fleek Mirror  | [https://saddlefinance.on.fleek.co/](https://saddlefinance.on.fleek.co)      |
| IPNS          | [https://ipfs.io/ipns/saddle.exchange](https://ipfs.io/ipns/saddle.exchange) |

You can also use any of the following aggregators:

| **AGGREGATOR** | **LINK**                                      |
| -------------- | --------------------------------------------- |
| 1inch          | [https://app.1inch.io/](https://app.1inch.io) |
| Matcha         | [https://matcha.xyz/](https://matcha.xyz)     |
| Paraswap       | [https://paraswap.io/](https://paraswap.io)   |

You can also run the frontend locally using the GitHub repo:

| **LOCAL**             | **LINK**                                                                                               |
| --------------------- | ------------------------------------------------------------------------------------------------------ |
| GitHub Front End Repo | [https://github.com/saddle-finance/saddle-frontend](https://github.com/saddle-finance/saddle-frontend) |

### **What are the fees for using Saddle?**

Trading on a Saddle pool carries two fees – a trading fee and a gas fee.

_**Trading fee**:_ The trading fee applies to every trade and the prevailing fee is displayed in the pool information. Typically, the fee is 0.04%. However, the fee may vary depending on the pool.

_**Admin fee**:_ The admin fee is included as a % of the trading fee. Currently it is zero.

_**Gas fee**:_ The fee payable to Ethereum network to confirm the transactions. The gas fee varies depending on the speed of confirmation time required and represented in gwei (1 gwei = 10-9 ETH).

![Example of Saddle Fees](<.gitbook/assets/0 (1) (1) (1) (1) (3) (2).png>)

**Note:** There is no fee to withdraw your liquidity from Saddle pools. Initial versions of our contracts contained a withdrawal fee feature, but we have removed this from all future pools.

{% hint style="info" %}
Find Saddle's fee calculation code [here](https://github.com/saddle-finance/saddle-contract/blob/38328fba920abd10bfe3ac9fde98e7c9cc50af9a/contracts/Swap.sol#L81)
{% endhint %}

### **Is Saddle safe?**

Saddle has been [audited](https://docs.saddle.finance/smart-contract-audit) by Certik, Quantstamp, and OpenZeppelin. We have passed security auditing on all Saddle smart contracts, from the following auditors.

| **AUDITOR**                             | **PROTOCOL AUDIT**                                                                              | **VIRTUAL SWAP AUDIT**                                                                                      |
| --------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| [Certik](https://certik.io)             | [PASSED](https://github.com/saddle-finance/saddle-audits/blob/master/10-29-2020_Certik.pdf)     | N/A                                                                                                         |
| [Quantstamp](https://quantstamp.com)    | [PASSED](https://github.com/saddle-finance/saddle-audits/blob/master/12-09-2020_Quantstamp.pdf) | [PASSED](https://github.com/saddle-finance/saddle-audits/blob/master/03-31-2021_Quantstamp_VirtualSwap.pdf) |
| [OpenZepplin](https://openzeppelin.com) | [PASSED](https://blog.openzeppelin.com/saddle-contracts-audit/)                                 | N/A                                                                                                         |

_**Disclaimer**:_ Investing in cryptocurrencies is risky. Using Saddle as an exchange should be significantly less risky, but keep in mind there are still risks. Refer to the [risks section](https://docs.saddle.finance/asset-specific-risks) for more details.

### **Who controls Saddle's admin keys?**

A [Gnosis Safe](https://gnosis-safe.io) multisig secures Saddle’s admin keys. Gnosis is a trusted platform to manage digital assets in Ethereum. A [3/7 Gnosis Safe multisig](https://etherscan.io/address/0x3F8E527aF4e0c6e763e8f368AC679c44C45626aE) secures Saddle's admin keys. The signers are:

| **NAME**                                             | **ENS**           | **ADDRESS**                                |
| ---------------------------------------------------- | ----------------- | ------------------------------------------ |
| [Mariano Conti](https://twitter.com/nanexcool)       | -                 | 0x6F2A8Ee9452ba7d336b3fba03caC27f7818AeAD6 |
| [Weston Nelson](https://twitter.com/westonnelson)    | -                 | 0xD131F1BcDd547e067Af447dD3C36C99d6be9FdEB |
| [DegenSpartan](https://twitter.com/DegenSpartan)     | degenspartan.eth  | 0x4E60bE84870FE6AE350B563A121042396Abe1eaF |
| [Klim K](https://twitter.com/milkyklim)              | yfi.milkyklim.eth | 0x0cec743b8ce4ef8802cac0e5df18a180ed8402a7 |
| [Damir Bandalo](https://twitter.com/damirbandalo)    | -                 | 0xa83838221278f22ee5bAe3E523f34D42b066D67D |
| [Aurelius](https://twitter.com/AureliusBTC)          | aurelius0x.eth    | 0x0AF91FA049A7e1894F480bFE5bBa20142C6c29a9 |
| [Scoopy Trooples](https://twitter.com/scupytrooples) | -                 | 0xf872703F1C8f93fA186869Bac83BAC5A0c87C3c8 |
| [Sam Kazemain](https://twitter.com/samkazemian)      | -                 | 0x17e06ce6914E3969f7BD37D8b2a563890cA1c96e |

This 3/7 multisig has capabilities to pause new deposits and trades in case of technical emergencies. Users will always be able to withdraw their funds regardless of new deposits being paused. The multisig can also change the swap/withdrawal fees and the per pool/account deposit limits.

### **What smart contracts does the community multisig control?**

The community multisig currently owns all pool/metapool, team/investor vesting, and MiniChef rewards contracts.

For a full list of contract addresses, please reference the [Contract Addresses docs](https://docs.saddle.finance/contracts).

### **Does the Saddle protocol use any oracles?**

No, the Saddle protocol does not use any oracles as all computation is a function of the current pool balance/composition.

### **Is the Saddle protocol susceptible to front running?**

The Saddle protocol does not contain any front running mitigations as they are not possible to include in the protocol itself.

We encourage users to use the [Flashbots Protect RPC](https://docs.flashbots.net/flashbots-protect/rpc/quick-start/) to protect themselves from front running.

### **What institutional investments did Saddle get?**

Refer to the [Our Investors](https://docs.saddle.finance/build-with-saddle#our-investors) section in Build with Saddle. The section contains a list of the institutional investors supporting Saddle.

### **Did you copy Curve?**

Our original vision was to use Synthetix as a bridge across asset pools to facilitate large, low-slippage trades (alla virtual swap). In the ideal scenario, we would have just built on top of Curve’s [StableSwap](https://curve.fi/whitepaper), but they had a restrictive license, so we had to reimplement it.

From the beginning, we’ve been open about using the StableSwap algorithm. StableSwap is a [Hybrid Function Market Maker](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3722714) based on the Constant Product Market Maker (implemented by Uniswap) and Constant Sum Market Maker. While the StableSwap algorithm was indeed developed by a member of the Curve team, it is nonetheless published in the public domain.

The comparison of Curve and Saddle is rooted in the algorithm used. Saddle’s technical implementation (and perhaps equally important, our ethos) is different.

### **Why support Saddle over Curve?**

**Principally**, Saddle is built on the values of open-source and collaboration, while Curve operates on a restrictive license. We welcome anyone who wants to build on top of Saddle or bring stablecoin / pegged asset DEX/AMM to another chain. Check out [Build with Saddle](https://docs.saddle.finance/build-with-saddle) on ways to collaborate.

**Technically**, Saddle is implemented in Solidity, while Curve is implemented using Vyper. Here’s a [research paper](https://www.researchgate.net/publication/334626679_Data_Protection_with_Ethereum_Blockchain) comparing the two languages.

{% hint style="info" %}
Find the forked projects of Saddle [here](https://github.com/saddle-finance/saddle-contract/network/members)
{% endhint %}

### **How do I work with Saddle?**

Check out [Build with Saddle](https://docs.saddle.finance/build-with-saddle) on ways to collaborate.

### **What is Saddle’s "Proof of Governance"?**

Saddle launched with Proof of Governance (PoG) to protect our users with certain limits and discourage sybil attacks. Initially, there will be a pool TVL cap of 150 BTC and a per-address deposit limit of 1 BTC. These limits were raised every 1-2 weeks.

**Note:** The guarded launch has been successful and as of 22nd February 2021, we have disabled the guard ([Etherscan transaction](https://etherscan.io/tx/0xedc38ea0b5f1cc740c6659cdecdc5b379bcd77b1eae59709d41e9811b92a4d66)). Anyone can become a liquidity provider in Saddle's pools.

For LPs to qualify for PoG, an address must have demonstrated active network participation in one of the following ways:

- On-chain voting or delegation (MKR, COMP, YFI, YAM, CRV, UNI, UMA, Moloch DAO)
- Off-chain voting on Snapshot (all protocols)
- Staking SNX and minting sUSD (>$20)

The cutoff date for all activity was 1st October 2020, except for UNI, which was 1st January 2021.

A full list of eligible addresses is available [here](https://github.com/saddle-finance/saddle-allowlist-addresses). PoG was temporary and has been phased out.

We implemented this guarded launch to establish a more controlled environment that will allow us to ensure a stable launch and remain responsible with users’ funds. Our aim above all else is to ensure the application performs to its expectations, users’ funds remain safe, and our community of supporters, developers, and users remain confident in our ability to launch successfully and fairly.

### **How can I keep up-to-date about Saddle?**

| **FOLLOW FOR LATEST SADDLE UPDATES** |                                                                        |
| ------------------------------------ | ---------------------------------------------------------------------- |
| Saddle Blog                          | [https://blog.saddle.finance/](https://blog.saddle.finance)            |
| Discord                              | [https://discord.gg/hX8RZFBW9R](https://discord.gg/hX8RZFBW9R)         |
| Twitter                              | [https://twitter.com/saddlefinance](https://twitter.com/saddlefinance) |
| GitHub                               | [https://github.com/saddle-finance](https://github.com/saddle-finance) |
| Telegram                             | [https://t.me/saddle_finance](https://t.me/saddle_finance)             |

### **How do I report a bug?**

Our goal is to provide you with the safest Saddle protocol. We encourage the community to help us find bugs or vulnerabilities in the protocol. The bounty reward is up to **US$ 50,000**. Report your findings via any one of these channels.

| REPORT HERE                    | LINK                                                                       |
| ------------------------------ | -------------------------------------------------------------------------- |
| Discord (**#support** channel) | [https://discord.gg/hX8RZFBW9R](https://discord.gg/hX8RZFBW9R)             |
| Telegram                       | [https://t.me/saddle_finance](https://t.me/saddle_finance)                 |
| Email                          | [security@saddle.finance](mailto:security@saddle.finance)                  |
| Immunify Bug Bounty            | [https://immunefi.com/bounty/saddle/](https://immunefi.com/bounty/saddle/) |

The [Terms and Conditions](https://immunefi.com/bounty/saddle/) cover your participation in the Bug Bounty Program. By submitting any vulnerabilities to Saddle Finance or otherwise participating in the Program in any manner, you accept these Terms.

## **SADDLE TOKEN (SDL)**

Frequently asked questions and answers regarding Saddle governance token. Still have questions? [Join our Discord](https://discord.gg/hX8RZFBW9R).

### **What is** SDL token used for?

SDL is the governance token for Saddle Finance. It is also used to reward and incentivize the Saddle community. Read all about the governance process [here](https://docs.saddle.finance/sdl-token#_toc87947035).

### How many SDL tokens are available?

The max supply of 1 billion SDL has been minted at genesis and will become available over the course of 2-3 years. Check out the [tokenomics section](https://docs.saddle.finance/sdl-token#_toc87947029) for the allocation and vesting details.

{% hint style="info" %}
Find SDL token code [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/SDL.sol)
{% endhint %}

### How do I get SDL tokens?

The token is initially non-transferable for a period of between 3 to 12 months. During this lockup period, the only way to earn SDL is by LPing in Saddle’s incentivized pools or by participating in the bounties4bandits (b4b) program. Learn more [here](https://docs.saddle.finance/sdl-token#_toc87947031).

Once the lockup period ends, you'll be able to buy SDL on an exchange.

### Are there time locks on the SDL tokens?

There are two time locks on the SDL Token:

1. A non-transfer period of 3 to 12 months
2. A vesting period of 2 to 3 years

The reason for time lock is to allow community members to earn more and deter short-term profit-seekers and mercenaries. More details [here](https://docs.saddle.finance/sdl-token).

### Are there time locks on any Saddle smart contracts?

No, all contracts that have admin functionalities are owned by the community multisig and do not have any time locks so the multisig can act quickly in case of an emergency.

### When does SDL token begin to vest?

If you received SDL tokens in the airdrop, they have already began to vest. The vesting period is 2-3 years, further details are available [here](https://docs.saddle.finance/sdl-token#_toc87947030).

{% hint style="info" %}
Find SDL token vesting code [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/Vesting.sol) and [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/RetroactiveVesting.sol)
{% endhint %}

### Is there a deadline to claim SDL tokens after the vesting period?

After the vesting period ends, users have 1 year to claim the SDL tokens. After 1 year, all unclaimed goes to the protocol treasury.

### When can I trade SDL tokens?

SDL tokens are initially non-transferable / non-tradable. Wallets that received the airdrop can vote with their tokens, but they cannot transfer between wallets or different users. If governance does not vote to make SDL transferable early (vote can happen as early as 3 months from now), then 12 months after token launch, SDL will automatically unlock. That means before the end of 2022, the SDL token will be unlocked and operate as typical (transferable) ERC-20.

### How do I claim my SDL?

Go to [saddle.exchange](https://saddle.exchange) (set your network to Ethereum mainnet) and click the SDL icon (top right) to open the claim UI to view and claim there.

![Open the SDL claim UI by clicking the SDL icon on the top right](<.gitbook/assets/image (2).png>)

### Why can't I claim my SDL on Arbitrum?

As of time of writing, **SDL is only claimable on mainnet.** The claim UI on Arbitrum is just meant to be a preview of your SDL rewards. They will be claimable once SDL is supported on the network (estimated Q1, 2022).

## **PEGGED VALUE ASSETS**

Frequently asked questions and answers regarding Saddle pegged value assets and tokens. Still have questions? [Join our Discord](https://discord.gg/hX8RZFBW9R).

### **What are Pegged Value Crypto Assets (Pegged Assets) ?**

Pegged value crypto assets (pegged assets) are tokens having their value pegged to an underlying asset. For example, the value of a stablecoin or tokenized bitcoin is supposed to be $1 or 1 BTC, respectively.

Pegged assets fix this value using different mechanisms:

- Some assets, like Synthetix sBTC or sUSD, maintain their peg synthetically (in this case, via collateralization of Synthetix’s SNX tokens)
- Other assets maintain their peg by being backed by and redeemable for the actual underlying asset, either permissionlessly (e.g., tBTC) or through a centralized custodian (e.g., WBTC, USDC).

Because of the different approaches and the associated risks, the prices of pegged assets of the same type may vary slightly.

### **What are Stablecoins?**

Stablecoins are cryptocurrencies whose value is pegged to another asset class to stabilize its price. The pegged asset can be a fiat currency like US$, or a real-world commodity like gold. Based on the pegging mechanism, stablecoins can be divided into several groups:

- Fiat-collateralized stablecoins – E.g., USDC, USDT, BUSD
- Commodity-collateralized stablecoins – E.g., DGX (backed by Gold), SRC (Real Estate)
- Crypto-collateralized stablecoins – E.g., DAI
- Algorithmic stablecoins – E.g., FRAX, AMPL

### **What is Tokenized Bitcoin?**

Tokenized bitcoin is BTC “sent” from the Bitcoin blockchain to the Ethereum blockchain. BTC is held in a deposit contract which “mints” a token on Ethereum. The minted Bitcoin token on Ethereum has the same value as the regular BTC and can be used to the full capability of an ERC-20 token.

Some examples of tokenized bitcoin include tBTC, renBTC, wBTC, and sBTC.

### **What are Wrapped Tokens?**

Blockchain networks differ in functionality and inter-operability of tokens is a challenge. [Wrapped](https://wrapped.com) tokens serve as a bridge between different blockchains.

_**Wrapping**_ (minting) is done by sending an asset to the custodian's deposit address and by submitting a wrapping request.

_**Unwrapping**_ (burning) an asset is done by submitting a request to the custodian. Once unwrapped, the custodian will send the equivalent underlying asset (minus applicable fees) to the user's account.

Some examples of wrapped tokens include wBTC, wETH, and wCUSD.

### **What are Synthetic Tokens (Synths)?**

Synthetix is a protocol for issuing and trading synthetic assets on the Ethereum blockchain. [Synths](https://www.synthetix.io/synths) are _ERC-20 tokens_, providing exposure to a range of assets. Each synth tracks the price of an external asset (fiat currency, cryptocurrency, commodities, etc). For example:

- sBTC synth tracks the price of Bitcoin (BTC) through price feeds supplied by an oracle.
- sUSD synth tracks the price of a single US Dollar (USD). This synth is always valued at $1 in the debt repayment mechanism of Synthetix.
- sCHF tracks the price of the Swiss Franc (CHF) through price feeds supplied by an oracle.

Synths provide exposure to an asset (at a clear price) without holding the asset. With synths, traders can get exposure to assets which don’t exist on-chain.

### **What are Virtual Synths?**

Virtual synths are an additional feature introduced by Synthetix. vSynths [allow](https://sips.synthetix.io/sips/sip-89/) the proceeds of unsettled exchanges to be transferable by tokenizing them. This helps Synthetix overcome the composability challenge. Learn more about [vSynths](https://blog.saddle.finance/low-slippage-trades-across-saddle-btc-eth-and-usd-pools-via-virtual-swap/).

### **What tokens are currently supported by Saddle?**

Currently, these are the pegged assets we support. Our support for pegged value crypto assets keeps growing. Please visit [https://saddle.exchange/](https://saddle.exchange) to check the tokens supported.

| **Pegged Asset** | **Website**                                              |
| ---------------- | -------------------------------------------------------- |
| alETH, alUSD     | [https://www.alchemix.fi/](https://www.alchemix.fi)      |
| DAI              | [https://makerdao.com/](https://makerdao.com)            |
| FEI              | [https://fei.money/](https://fei.money)                  |
| FRAX             | [https://frax.finance/](https://frax.finance)            |
| LUSD             | [https://www.liquity.org/](https://www.liquity.org)      |
| renBTC           | [https://renproject.io/](https://renproject.io)          |
| sBTC, sETH, sUSD | [https://synthetix.io/](https://synthetix.io)            |
| tBTC             | [https://tbtc.network/](https://tbtc.network)            |
| USDC             | [https://www.centre.io/usdc](https://www.centre.io/usdc) |
| USDT             | [https://tether.to/](https://tether.to)                  |
| wBTC             | [https://wbtc.network/](https://wbtc.network)            |
| wCUSD            | [https://celo.org/](https://celo.org)                    |
| WETH             | [https://weth.io/](https://weth.io)                      |

### **Will Saddle support other assets? When?**

Absolutely yes. Our mission is to unlock deep on-chain liquidity between pegged value crypto assets. We keep adding [partners ](https://docs.saddle.finance/build-with-saddle)and assets to realise our mission.

**Follow us**, if you haven’t already, for the latest updates on new assets and pools.

| [**BLOG**](https://blog.saddle.finance) | [**DISCORD**](https://discord.gg/hX8RZFBW9R) | [**TWITTER**](https://twitter.com/saddlefinance) | [**GITHUB**](https://github.com/saddle-finance) | [**TELEGRAM**](https://t.me/saddle_finance) |
| --------------------------------------- | -------------------------------------------- | ------------------------------------------------ | ----------------------------------------------- | ------------------------------------------- |

**Collaborate with us** if you are working on an exciting DeFi project. Check out the [Build with Saddle](https://docs.saddle.finance/build-with-saddle) section for details.

### **What are the risks with Pegged Value Crypto Assets?**

Investing in cryptocurrencies is risky. The cryptocurrency assets in the various Saddle protocols are an integral part of the Saddle ecosystem. Any risks to the assets have a cascading effect on Saddle. Before we accept a cryptocurrency for the liquidity pools, we evaluate the [underlying risks](https://docs.saddle.finance/asset-specific-risks) for the assets and operations of the asset. If one or more risks are significant, we don’t accept the cryptocurrency for the Saddle pools. The three main risk evaluation parameters are:

- Smart-contract risks
- Counter-party risks
- Market risks

Check out the [asset specific risk](https://docs.saddle.finance/asset-specific-risks) section to know more.

## **LIQUIDITY POOLS & SWAPS**

Frequently asked questions and answers regarding Saddle Liquidity Pools and Saddle Swaps. Still have questions? [Join our Discord](https://discord.gg/hX8RZFBW9R).

### **What is a Decentralized Exchange (DEX)?**

Saddle is a decentralized exchange. A cryptocurrency exchange is a marketplace for trading cryptocurrencies. Broadly, two types of cryptocurrency exchanges exist:

- _**Centralized Exchanges (CEX)**_: A cryptocurrency exchange owned and governed by a 3rd party. E.g., Binance, Coinbase, and Bitfinex.
- _**Decentralized Exchanges (DEX)**_: A cryptocurrency exchange, unlike CEX, is not owned or governed by a 3rd party. A DEX acts as a peer-to-peer (P2P) platform, facilitating trade with no central party. E.g., Saddle, Uniswap, Sushiswap, and Mdex.

### **What is an Automated Market Maker?**

Market makers are essential in an exchange to provide liquidity, control spreads, and maintain slippages. Since cryptocurrency exchanges work 24x7, the need for automated market makers rose. [AMMs ](https://docs.saddle.finance/automated-market-makers)democratized cryptocurrency trading by doing away with order books and institutional market makers. Instead, AMMs execute trade automatically using algorithms and liquidity pools.

### **What is the Constant Product Formula?**

[Constant product formula](https://docs.saddle.finance/automated-market-makers#constant-product-formula) is probably the simplest and the earliest AMM algorithm to come into the market. Uniswap popularized the mathematical formula:

```
                                          x * y = k
```

where **x** is the amount of Token#1 in the liquidity pool, **y** is the amount of Token#2 in the liquidity pool, and **k** is a fixed constant.

Given the volatile nature of cryptocurrency, the market price of the tokens also fluctuates. The constant product formula _does not update_ the price of the tokens in the pool with the market movement. This resulted in the risk of higher slippages.

### **What is the Constant Sum Formula?**

To address the slippage issue, AMMs explored the constant sum formula as an option. [Constant sum formula](https://docs.saddle.finance/automated-market-makers#constant-sum-formula) solves for the equation:

```
                                      x + y = k
```

where **x** is the amount of Token#1 in the liquidity pool, **y** is the amount of Token#2 in the liquidity pool, and **k** is a fixed constant.

While the constant sum formula solves the slippage problem, it provides only _fixed liquidity_. For markets to function well, they need a constant supply of liquidity and hence this model didn’t suit the purpose well.

### **What is the StableSwap Formula?**

First introduced by [Curve](https://curve.fi/whitepaper), the Stableswap is a hybrid algorithm. The [Stableswap ](https://docs.saddle.finance/automated-market-makers#stableswap-algorithm)hybrid combines both Constant Product and Constant Sum models:

- **Constant Sum:** When the liquidity pool portfolio is balanced, the algorithm functions as a Constant Sum formula; **x + y = k**.
- **Constant Product:** As the liquidity pool portfolio becomes imbalanced, the StableSwap algorithm functions as a Constant Product formula; **x \* y = k**.

{% hint style="info" %}
Find Saddle's StableSwap implementation code [here](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/Swap.sol)
{% endhint %}

### **What are Dynamic Pegs?**

The Constant Product formula _does not update_ the price of the tokens in the pool with the market movement. The Stableswap formula motivates swaps around price ratio 1.0, well suited for stablecoins. Dynamic pegs are the next evolution of AMMs.

Dynamic pegs will bring the benefits of Stableswaps to cryptocurrency assets, which aren’t pegged to another asset. By using an automatic price change mechanism, the algorithm will move the price based on real-time profit margin calculations to adjust for slippages. Thus, benefiting both the traders and the AMMs.

### **What is a Saddle Pool?**

Instead of an order book, AMMs use [liquidity pools](https://docs.saddle.finance/saddle-pools) to facilitate trade. Liquidity pool, a smart contract, is a fund of tokens (or coins).

In AMMs, traders interact with the smart contracts, to enable liquidity and price discovery. Because of the permissionless nature, AMMs allow anyone to provide liquidity to the liquidity pool. The liquidity pool smart contract holds two or more tokens and allows anyone to deposit and withdraw funds from them, but only according to specific mathematical rules.

### **Who is a Liquidity Provider?**

Liquidity providers (LPs) contribute assets (cryptocurrency tokens and coins) to liquidity pools.

In exchange for providing the tokens, the LPs normally earn a [fee](https://docs.saddle.finance/saddle-incentives). Now, when a trade executes on an AMM, the trade executes against the liquidity pool. This eliminates the need for an order book and for the buyer and seller to be present at that moment in time.

### **What is a Base Pool and Metapool?**

Saddle pools are of two types – base and metapools.

- _**Base pools**_ contain two or more tokens and implement the StableSwap algorithm.
- _**Metapools**_ contain one token to trade with another underlying Base pool. Metapools provide the flexibility for liquidity providers to get exposure to the metapool asset for additional rewards. For example, in the sUSD Pool, we pool the single token sUSD alongside Stablecoin Pool V2 (DAI, USDC, USDT). Adding the single asset to the metapool, however, does not dilute the liquidity of the underlying base pool.

### **How to provide Liquidity to a Metapool?**

You can provide liquidity to a metapool in two ways - as individual assets or as LP tokens from the base pool .

- **Step 1:** Go to [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools)
- **Step 2:** Choose the metapool from the list of pools available

![](<.gitbook/assets/3 (1) (1) (1) (1) (1).png>)

- **Step 3:** Click on _Deposit_

**Option 1 :** Deposit individual assets

![](<.gitbook/assets/4 (1) (1) (1) (1) (1).png>)

**Option 2** : Deposit LP tokens from the base pool

![](<.gitbook/assets/5 (1) (1) (1).png>)

### **What is Front-Running?**

While synths are great, they came with a limitation. Many decentralized exchanges (DEX) suffer from [front-running](https://blog.saddle.finance/low-slippage-trades-across-saddle-btc-eth-and-usd-pools-via-virtual-swap/). Because of constraints on Ethereum, there is a latency and cost in sourcing and updating the real-world asset price for the synths. Front-runners can see the difference between price of the asset in the real-world and on-chain. They see an arbitrage opportunity and over-pay for Ethereum gas fee to prioritize their orders in the queue, before the on-chain price reflects the real-world.

### **What is Composability?**

In DeFi, composability is the ability of open-source protocols to interact and combine creatively to form new products and services. There are two key aspects for composability to work:

- _**Standardization**_: The ability of DeFi protocols to connect and communicate in a standardized and open way.
- _**Atomicity**_: The need for the DeFi protocols to connect instantly within a single transaction.

To overcome the front-running challenge, a [time delay](https://blog.synthetix.io/how-fee-reclamation-rebates-work/) was introduced before a trader gets the underlying asset. While the solution was successful in addressing the front-running issue, introducing rebate and reclamation presented significant friction because of a second transaction required to settle the exchange. The need for two transactions breaks down the property of composability (atomicity in particular).

### **What are Virtual Synths (vSynths)?**

Virtual synths ([vSynth](https://blog.saddle.finance/low-slippage-trades-across-saddle-btc-eth-and-usd-pools-via-virtual-swap/)) were introduced to address the composability issue. Virtual synths are an additional feature introduced by Synthetix. vSynths [allow](https://sips.synthetix.io/sips/sip-89/) the proceeds of unsettled exchanges to be transferable by tokenizing them. This helps Synthetix overcome the composability challenge.

### **What is Virtual Swap?**

Virtual swaps are a new feature in Saddle pools leveraging Synthetix’s vSynths. This version 2 is an upgrade over the siloed version 1 synth pools. With implementing vSynth logic in Saddle’s AMM, it’s possible to use synths as _bridges between pools_.

**Saddle Synths: Version 1**

![](<.gitbook/assets/6 (3) (1) (1) (1) (1).png>)

**Saddle Synths: Version 2**

![](<.gitbook/assets/7 (1) (1) (1) (2).png>)

### **Where can I find Saddle’s Contract Addresses?**

The Saddle’s Contract Addresses are listed [here](https://docs.saddle.finance/contracts).

## **WORKING WITH SADDLE POOLS**

Frequently asked questions and answers regarding working with Saddle pools, fees, and technical details. Still have questions? [Join our Discord](https://discord.gg/hX8RZFBW9R).

### **Can I** withdraw from a paused Saddle pool?

You can withdraw your assets from the paused pool. When withdrawing, you need to withdraw proportionally all assets of the pool (combo).

Withdrawing a single asset is fundamentally a swap and therefore not allowed in the paused pools.

### **Why is the pool paused?**

A pool can be paused for a variety of reasons, including, but not limited to:

- One (or more) of the assets in a pool is [depegged](https://docs.saddle.finance/saddle-pools#market-risks)
- One (or more) of the assets has a [vulnerability ](https://docs.saddle.finance/saddle-pools#technical-risks)that's open for exploitation
- Smart contract [vulnerability](https://blog.saddle.finance/metapool-exploit-fix-is-live/)
- Suspicious activity going on (e.g., malicious bots)

**Note**: The pause function of a pool can be triggered only by the [multisig](https://docs.saddle.finance/smart-contract-audit#saddle-admin-keys-security).

### **What is Slippage?**

Slippage is the difference between the expected price of a trade and the execution price. This happens as there is a time delay between the trade request and execution in the market. Slippage can occur at any time but is amplified during periods of high volatility and with large volume trades.

In case of large trades, we recommend the use of aggregators like [1inch](https://1inch.io), [Matcha](https://matcha.xyz), or [Paraswap](https://paraswap.io) to limit the slippage.

### **What is Max Slippage?**

With max slippage setting, you can specify the maximum % of price movement you can accept for the trade. Your order will not execute if the slippage is beyond your maximum specified. The default for Saddle is 0.1%, but you can set it to any % you want.

![](<.gitbook/assets/8 (2) (1) (1) (1) (2).png>)

### **What is Price Impact?**

Price impact is the difference between the current market price and estimated execution price due to order size.

### **What is A parameter (Amplification Coefficient)?**

The StableSwap algorithm is a hybrid of Constant Product and Constant Sum formula. To simplify, for the purposes of [understanding](https://serenityfund.medium.com/company-watch-curves-formula-for-stablecoins-swap-and-the-magic-amplification-coefficient-d998ed1e184b), you can consider a StableSwap algorithm as:

**StableSwap = ( Constant Sum \* A ) + Constant Product**

A parameter, or amplification coefficient, is a configurable setting which determines how flat the liquidity curve for each pool is.

When:

- **A is small or 0**: The StableSwap algorithm functions as a Constant Product function
- **A is large or infinite**: The StableSwap algorithm functions as a Constant Sum function

For example, consider A = 1 vs. A = 10:

![A Parameter](<.gitbook/assets/9 (3) (1) (1) (1).png>)

The A parameter gives the flexibility to the fund managers to balance the pool stability by changing the amplification coefficient. Pools with more volatile assets will use lower A values.

{% hint style="info" %}
Find Saddle's implementation of A parameter [here](https://github.com/saddle-finance/saddle-contract/blob/38328fba920abd10bfe3ac9fde98e7c9cc50af9a/contracts/AmplificationUtils.sol)
{% endhint %}

### **What is the Gas Fee?**

[Gas](https://www.gasnow.org) refers to the unit that measures the amount of computational effort required to execute specific operations on the [Ethereum network](https://ethereum.org/en/developers/docs/gas/). Since each Ethereum transaction requires computational resources to execute, each transaction requires a fee. Gas refers to the fee required to successfully conduct a transaction on Ethereum.

Gas fees are paid in Ethereum's native currency, ether (ETH). Gas prices are denoted in gwei, which itself is a denomination of ETH - each gwei is equal to 0.000000001 ETH (10-9 ETH). For example, instead of saying that your gas costs 0.000000001 ether, you can say your gas costs 1 gwei. The word 'gwei' itself means 'giga-wei', and it is equal to 1,000,000,000 wei.

![](<.gitbook/assets/10 (1) (1) (1) (1) (1) (2).png>)

### **Why is Gas so expensive?**

Ethereum network is a popular destination for most decentralized apps (dApps). The popularity has led to enormous activity of Ethereum which results in high gas fees, i.e., higher transaction (gas) fees to miners. The good news is the [London Upgrade](https://eips.ethereum.org/EIPS/eip-1559) of Ethereum alters the way transaction fees are calculated, ideally smoothing them out and making them less volatile. There are also [Layer-2 solutions](https://ethereum.org/en/developers/docs/scaling/layer-2-rollups/) being actively explored to reduce the load on Ethereum network.

Additionally, here are a few [other ways](https://blog.makerdao.com/four-ways-defi-users-can-pay-less-in-ethereum-gas-fees/) to keep control over the Gas fees:

- Combine related transactions to save on gas
- Plan ahead and process your transactions when Ethereum network is not at its peak
- Choose a transaction speed (slow or fast) to minimize the gas fee

### **Where can I see the TVL and Stats for Saddle’s pools?**

The total value locked (TVL) details and stats are available alongside the Saddle Pools.

![](<.gitbook/assets/11 (1) (1) (1) (1).png>)

For more stats and analytics, you can check out the [DeFi analytics tools](https://docs.saddle.finance/saddle-protocol-stats).

### **Should I deposit into a pool if the assets are imbalanced?**

Yes, you may deposit into the pool if the assets are imbalanced. In fact, if you deposit underweight assets, you’ll get bonus LP tokens.

### **How do I withdraw the liquidity I provided?**

If at any point you want to withdraw your assets, head out to [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools)

- **Step 1:** Choose the pool on the top navigation bar
- **Step 2:** Click on _Withdraw_

![](<.gitbook/assets/12 (1) (1) (1) (3) (1) (5).png>)

- **Step 3:** Enter the amount you’d like to withdraw from one or more of the assets listed in the Saddle pool.
- **Step 4:** Click _Advanced Options_ to select options like slippage and gas.

![](<.gitbook/assets/13 (1) (1) (1) (3) (1) (6).png>)

- **Step 5:** Click _Withdraw_ and review the details and confirm the transaction.

### **What risks are there to depositing in Saddle’s pools?**

As with any investment, traditional or DeFi, providing liquidity to the pools carries a risk. Typically, the risks include risk of smart contracts, risks associated with the tokens/Stablecoins in the liquidity pools, and/or the risks associated with the AMMs. We outline the risks in the Saddle pool risk [section](https://docs.saddle.finance/saddle-pools#saddle-pool-risks).

### **Why is my approval/transaction stuck?**

The first thing you need to do when a transaction’s [stuck](https://medium.com/@jgm.orinoco/releasing-stuck-ethereum-transactions-1390149f297d) is to _not send any new transaction_. All new transactions will also get stuck until the pending old transactions are confirmed. Then you have the option to speed up or cancel the stuck transaction. The options for speeding up or cancelling are dependent on the wallet you use.

- Metamask : [Instructions](https://metamask.zendesk.com/hc/en-us/articles/360015489251-How-to-Speed-Up-or-Cancel-a-Pending-Transaction)
- Coinbase : [Instructions](https://help.coinbase.com/en/wallet/sending-and-receiving/adjusting-miner-fees)
- Trust Wallet: [Instructions](https://www.publish0x.com/the-crypt/quick-guide-to-fixing-stuck-ethereum-transactions-xgdvgkv)

**Note:** If you don’t find the options to speed up or cancel in your wallet, be sure to check with the wallet provider. In the event your wallet provider doesn’t support the speed or cancel feature, here are a few alternate options ([MEW](https://kb.myetherwallet.com/en/transactions/checking-or-replacing-a-tx-after-sending/), [MYCRYPTO](https://support.mycrypto.com/how-to/sending/checking-or-replacing-a-transaction-after-it-has-been-sent)) to explore.

### **How can I see my liquidity provider fees?**

The liquidity providers fees come in two forms - trading fees and flash loan fees (where applicable). You can see the fees in the trading window of the pools.

![](<.gitbook/assets/14 (1) (1) (1) (2).png>)

For real-time view on the trading fees over a period, you can check out the stats here: [https://www.tokenterminal.com/terminal/projects/saddle-finance](https://www.tokenterminal.com/terminal/projects/saddle-finance)

## **SADDLE REWARDS & INCENTIVES**

Frequently asked questions and answers regarding Saddle rewards and incentives. Still have questions? [Join our Discord](https://discord.gg/hX8RZFBW9R).

### **What is Yield Farming?**

[Yield farming](https://docs.saddle.finance/yield-farming-tools) is an incentive mechanism to put an individual’s cryptocurrency assets to work and generate high returns. Liquidity providers, in yield farming protocols, stake or lock up their assets to earn rewards and higher interests.

### **What are Saddle’s liquidity provider rewards?**

Saddle rewards the liquidity providers for their contribution to the liquidity pool. Depending on the liquidity pool, the rewards structure varies. There are many ways to earn rewards – interest from trading fees, interest from lending, and pool specific incentives. Refer to the [incentives ](https://docs.saddle.finance/saddle-incentives)section for details.

### **What are LP Tokens?**

Liquidity provider tokens (LP tokens) are tokens issued to liquidity providers. LP tokens are used to track individual contributions (proportional share of liquidity) to the overall liquidity pool.

### **What is the difference between APR and APY?**

Both [APY and APR](https://docs.saddle.finance/saddle-incentives#apy-and-apr) refer to yield or interest rates.

- **Annual Percentage Yield (APY):** APY refers to the amount of interest a liquidity provider earns over one year. APY is like an interest rate, but the biggest benefit of APY is the _compounding_.
- **Annual Percentage Rate (APR):** APR does not factor compounding and represents the annual interest rate.

Let’s take a scenario of 1% interest each month. Therefore,

| **APR at 1% interest per month**               | **APY at 1% interest per month**                  |
| ---------------------------------------------- | ------------------------------------------------- |
| APR = Periodic Rate x No. of Periods in a Year | APY = (1 + Periodic Rate) `Number of periods` – 1 |
| APR = 1% X 12 months                           | APY = (1+1%)`12` -1                               |
| 12.00%                                         | 12.68%                                            |

### **How much will I earn for LPing Saddle’s pools?**

Depending on the liquidity pool, the rewards structure varies. Refer to the [incentives ](https://docs.saddle.finance/saddle-incentives)section for details.

### **What additional rewards can I get for LPing Saddle’s pools?**

Depending on the liquidity pool, the rewards structure varies. Refer to the [incentives ](https://docs.saddle.finance/saddle-incentives)section for details.

### **Where do I go to Stake/Unstake?**

Depending on the liquidity pool, the staking/unstaking process varies. The typical process is as shown below:

![](<.gitbook/assets/1 (6) (1) (1) (3) (1) (3).png>)

| **Saddle Pool** | **Rewards**                 | **Link**                                                                     |
| --------------- | --------------------------- | ---------------------------------------------------------------------------- |
| BTC Pool        | KEEP Rewards                | [KEEP Liquidity Rewards Dashboard](https://dashboard.keep.network/liquidity) |
| alETH Pool      | ALCX Rewards                | [Alchemix Staking Dashboard](https://app.alchemix.fi/farms)                  |
| D4 Pool         | ALCX/FXS/LQTY/TRIBE Rewards | [FRAX Staking Dashboard](about:blank)                                        |

For further details, refer to the [incentives ](https://docs.saddle.finance/saddle-incentives)section.
