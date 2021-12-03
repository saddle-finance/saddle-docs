---
description: >-
  Before we accept a cryptocurrency for the Saddle pools, we evaluate the
  underlying risks for the assets and operations of the asset.
---

# Asset Specific Risks

Investing in cryptocurrencies varies in risk. The cryptocurrency assets in the various Saddle protocols are an integral part of the Saddle ecosystem. Any risks to the assets may negatively impact the pool.

Before we accept a cryptocurrency for the liquidity pools, we evaluate the underlying risks for the assets and operations of the asset. If one or more risks are significant, we don’t accept the cryptocurrency for the Saddle pools. The three main risk evaluation parameters are:

_**Smart-contract risks**_: DeFi is a complicated network interconnected through hundreds of smart contracts created by various 3rd parties. Typically, smart contracts undergo code reviews, security audits, and bug bounty programs - yet that doesn’t absolve the contracts of any technical glitches and bugs entirely. When Saddle evaluates a cryptocurrency asset for our liquidity pools, we focus on the maturity, besides many other parameters, of the smart contract. The **age** of the smart contract and the community **adoption** (specifically the number of transactions) is a powerful indicator of the smart contract robustness.

_**Counter-party risks**_: Counterparty risk relates to a 3rd party defaulting on its contractual obligation. Though open blockchain networks and DeFi are designed with the goal of eliminating counterparty risks, some cryptocurrency assets carry the counterparty risk because of their design. Digital assets tied to real-world assets, dependent on external Oracles for information, and centralized are few examples of counterparty risk. At Saddle, we qualitatively evaluate counterparty risks from a **trust** and **governance** point of view.

_**Market risks**_: We primarily relate fluctuations and liquidity to the market risks of cryptocurrencies. Stablecoins and pegged-value assets, which make up the Saddle pools, address the volatility to an extent. However, if one asset in the pool significantly depegs, it will effectively mean that it will leave pool liquidity providers holding only that asset. Liquidity risk may happen because of a seller not finding a buyer or there is a mandatory lock-in period.

In this section, we will examine the risks for each asset in the Saddle pools composition. The information provided is as of the 3rd week of **Aug 2021**.

|                        |                               |                  |                |             |              |            |
| ---------------------- | ----------------------------- | ---------------- | -------------- | ----------- | ------------ | ---------- |
| **Asset**              | **Age**                       | **Transactions** | **Governance** | **Holders** | **MCAP ($)** | **Supply** |
| **BTC Pool**           |                               |                  |                |             |              |            |
| renBTC                 | > 1 year                      | 10k - 100k       | Decentralized  | 1k - 5k     | $100m - $1b  | < 500k     |
| sBTC                   | > 2 years                     | 10k - 100k       | Decentralized  | 1k - 5k     | $100m - $1b  | < 500k     |
| tBTC                   | > 1 year                      | < 10,000         | Decentralized  | < 1,000     | $10m - 50m   | < 500k     |
| wBTC                   | > 2 years                     | 100k - 500k      | Decentralized  | 10k - 100k  | > $5b        | < 500k     |
| **alETH Pool**         |                               |                  |                |             |              |            |
| alETH                  | < 1 year                      | 10k - 100k       | Decentralized  | < 1,000     | N/A          | N/A        |
| sETH                   | > 2 years                     | 10k - 100k       | Decentralized  | 1k - 5k     | $100m - $1b  | < 500k     |
| WETH                   | > 2 years                     | > 1m             | Decentralized  | 100k - 1m   | > $1b        | 1m - 10m   |
| **Stablecoin Pool V2** |                               |                  |                |             |              |            |
| DAI                    | > 1 year                      | > 10m            | Decentralized  | 100k - 1m   | > $5b        | > 5b       |
| USDC                   | > 2 years                     | > 10m            | Centralized    | > 1m        | > $5b        | > 5b       |
| USDT                   | > 2 years                     | > 10m            | Centralized    | > 1m        | > $5b        | > 5b       |
| **D4 Pool**            |                               |                  |                |             |              |            |
| alUSD                  | < 1 year                      | < 10,000         | Decentralized  | < 1,000     | $100m - $1b  | 100m - 1b  |
| FEI                    | < 1 year                      | 10k - 100k       | Decentralized  | 1k - 5k     | $100m - $1b  | 100m - 1b  |
| FRAX                   | < 1 year                      | 100k - 500k      | Decentralized  | 1k - 5k     | $100m - $1b  | N/A        |
| LUSD                   | < 1 year                      | 100k - 500k      | Decentralized  | 1k - 5k     | $100m - $1b  | N/A        |
| **sUSD Pool**          |                               |                  |                |             |              |            |
| sUSD                   | > 2 years                     | 500k - 1m        | Decentralized  | 10k - 100k  | $100m - $1b  | 100m - 1b  |
| saddleUSD-V2           | _Refer to Stablecoin Pool V2_ |                  |                |             |              |            |
| **wCUSD Pool**         |                               |                  |                |             |              |            |
| wCUSD                  | < 1 year                      | < 10,000         | Decentralized  | < 1,000     | $1m - $10m   | 500k - 1m  |
| saddleUSD-V2           | _Refer to Stablecoin Pool V2_ |                  |                |             |              |            |

## **alETH**

alETH is a synthetic ETH backed asset by Alchemix Finance. alETH is an ERC20 token, backed 4:1 by ETH.

_**Smart-contract risks**_: The alETH smart [contract](https://etherscan.io/token/0x0100546F2cD4C9D97f798fFC9755E47865FF7Ee6) was launched in June 2021, making it a relatively _young contract_. The number of transactions since launch stands at 2,852. The total [amount](https://explorer.bitquery.io/ethereum/token/0x0100546f2cd4c9d97f798ffc9755e47865ff7ee6) transacted is \~76,131 alETH, with a median of \~1.25 alETH.

_**Counter-party risks**_: Alchemix Finance is a future-yield-backed synthetic asset platform and community [DAO](https://alchemix-finance.gitbook.io/alchemix-finance/alchemix-dao). The vision is for a full on-chain governance, giving complete control to the community for several protocol parameters. There are 128 token [holders](https://etherscan.io/token/0x0100546F2cD4C9D97f798fFC9755E47865FF7Ee6#balances) at the time of writing.

_**Market risks**_: alETH is backed by ETH in the 4:1 ratio. At present, the [market](https://forum.alchemix.fi/public/d/173-aip-15-raise-the-aleth-debt-cap-and-end-alusd-only-rewards) capitalization for alETH is over US$ 41 million.

_**Notable incidents**_: The following incidents and/or bugs were observed relating to the protocol:

- [Incident Report – 06162021](https://forum.alchemix.fi/public/d/137-incident-report-06162021) relating to a bug.

## **alUSD**

alUSD is a yield-backed synthetic stablecoin minted via Alchemix Finance. Users deposit DAI stablecoin to mint alUSD which tokenizes upto 50% of the DAI deposited.

_**Smart-contract risks**_: The alUSD smart [contract](https://etherscan.io/address/0xbc6da0fe9ad5f3b0d58160288917aa56653660e9) was launched in February 2021, making it a _young contract_. The number of transactions since launch stands at 2,852. The total [amount](https://explorer.bitquery.io/ethereum/token/0xBC6DA0FE9aD5f3b0d58160288917AA56653660E9) transacted is \~ 9,599,359,702 alUSD, with a median of \~ 9,650 alUSD.

_**Counter-party risks**_: Alchemix Finance is a future-yield-backed synthetic asset platform and community [DAO](https://alchemix-finance.gitbook.io/alchemix-finance/alchemix-dao). The vision is for a full on-chain governance, giving complete control to the community for several protocol parameters. There are 1,280 token [holders](https://etherscan.io/token/tokenholderchart/0xBC6DA0FE9aD5f3b0d58160288917AA56653660E9) at the time of writing.

_**Market risks**_: alUSD is yield-backed by depositing the DAI stablecoin. At present, the [market](https://www.coingecko.com/en/coins/alchemix-usd) capitalization for alUSD is $251,612,072 and a circulation coin supply of 252,895,826.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- None at the time of writing.

## **DAI**

DAI is a stablecoin or ERC-20 token backed by different digital currencies deposited into its smart contract vaults. DAI attempts to maintain a 1:1 peg to USD.

_**Smart-contract risks**_: The DAI smart [contract](https://etherscan.io/token/0x6b175474e89094c44da98b954eedeac495271d0f) was launched in November 2019 (prior to Nov 2019, it was active as SAI starting December 2017), making it a _mature_ _contract_. The number of transactions since launch stands at over 11 million. The total [amount](https://explorer.bitquery.io/ethereum/token/0x6b175474e89094c44da98b954eedeac495271d0f) transacted is over 580 million DAI, with a median of \~ 998 DAI.

_**Counter-party risks**_: MakerDAO develops and maintains the software that powers the DAI stablecoin system. MKR holders [govern](https://makerdao.com/en/governance/) the Maker Protocol, which includes adjusting policy for the Dai stablecoin, choosing new collateral types, and improving governance itself. There are 380,957 token [holders](https://etherscan.io/token/tokenholderchart/0x6b175474e89094c44da98b954eedeac495271d0f) at the time of writing.

_**Market risks**_: Users can generate DAI as debt by depositing equivalent collateral in a smart contract governed vault. At present, the [market](https://www.coingecko.com/en/coins/dai) capitalization for alUSD is over $5.7 billion and a circulation coin supply exceeding 5.7 billion.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- Maker’s price feed oracle [stuck](https://defipulse.com/blog/defi-status-report-black-thursday/) resulting in a MKR debt [auction](https://blog.makerdao.com/mkr-debt-auction-announcement-and-details/).

## **FEI**

FEI is a scalable and decentralized stablecoin that leverages protocol-controlled value (PCV) for peg maintenance while maintaining highly liquid secondary markets.

_**Smart-contract risks**_: The FEI smart [contract](https://etherscan.io/token/0x956f47f50a910163d8bf957cf5846d573e7f87ca) was launched in April 2021, making it a _relatively_ _young contract_. The number of transactions since launch stands at 113,670. The total [amount](https://explorer.bitquery.io/ethereum/token/0xBC6DA0FE9aD5f3b0d58160288917AA56653660E9) transacted is over 401 million FEI, with a median of \~ 21,253 FEI.

_**Counter-party risks**_: FEI is a fully decentralized design and minimal dependence on any centralized assets or protocols on Ethereum. Fei Protocol has a DAO called the Fei [DAO](https://docs.fei.money/governance/fei-dao) from the start. There are 3,880 token [holders](https://etherscan.io/token/tokenholderchart/0x956f47f50a910163d8bf957cf5846d573e7f87ca) at the time of writing.

_**Market risks**_: Fei is a direct incentive stablecoin which is undercollateralized and fully decentralized, with the goal to maintain a liquid market in which ETH/FEI trades closely to the ETH/USD price. At present, the [market](https://www.coingecko.com/en/coins/fei-protocol) capitalization for FEI is $ 415,899,906 and a circulation coin supply of 417,462,622.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- FEI pool becoming [unusable](https://cointelegraph.com/news/fei-protocol-struggles-with-a-bug-as-holders-are-mostly-unable-to-sell-the-token) for a time.
- Bonding curve [bug](https://medium.com/fei-protocol/fei-bonding-curve-bug-post-mortem-98d2c6f271e9).

## **FRAX**

FRAX is a fractional-algorithmic stablecoin that is partially backed by collateral and partially stabilized algorithmically.

_**Smart-contract risks**_: The FRAX smart [contract](https://etherscan.io/token/0x853d955acef822db058eb8505911ed77f175b99e) was launched in December 2020, making it a _mature contract_. The number of transactions since launch stands well over 107,000. The total [amount](https://explorer.bitquery.io/ethereum/token/0x853d955acef822db058eb8505911ed77f175b99e) transacted is over 5.4 billion FRAX, with a median of \~ 15,988 FRAX.

_**Counter-party risks**_: The end goal of the Frax protocol is to provide a highly scalable, decentralized, algorithmic money in place of fixed-supply digital assets like BTC. The Frax [governance](https://docs.frax.finance/smart-contracts/governance) module is forked from Compound, with FXS acting as the voting token in the system. There are 1,615 token [holders](https://etherscan.io/token/tokenholderchart/0x853d955acef822db058eb8505911ed77f175b99e) at the time of writing.

_**Market risks**_: Frax is open-source, permissionless, and entirely on-chain. At present, the [market](https://www.coingecko.com/en/coins/frax) capitalization for FRAX is more than $300 million.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- None at the time of writing.

## **LUSD**

LUSD is a collateral-backed stablecoin with a hard price floor of $1 USD. Users of the Liquity protocol (the issuers of LUSD) lock ETH for LUSD stablecoin. There’s only a one-time borrowing fee applicable.

_**Smart-contract risks**_: The LUSD smart [contract](https://etherscan.io/token/0x5f98805A4E8be255a32880FDeC7F6728C6568bA0) was launched in April 2021, making it a _relatively_ _young contract_. The number of transactions since launch stands at 104,550. The total [amount](https://explorer.bitquery.io/ethereum/token/0x5f98805A4E8be255a32880FDeC7F6728C6568bA0) transacted is over 17,311,656,894 LUSD, with a median of \~ 3,536 LUSD.

_**Counter-party risks**_: Liquity is a decentralized borrowing protocol that allows interest-free loans against Ether as a collateral. Liquity as a protocol is non-custodial, immutable, and [governance-free](https://docs.liquity.org/documentation/community-resources#podcasts). There are 2,778 token [holders](https://etherscan.io/token/tokenholderchart/0x5f98805A4E8be255a32880FDeC7F6728C6568bA0) at the time of writing.

_**Market risks**_: The loans are secured by a Stability Pool containing LUSD. At present, the [market](https://www.coingecko.com/en/coins/liquity-usd) capitalization for LUSD is $ 603,016,411.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- None at the time of writing.

## **renBTC**

renBTC is an ERC20 token backed 1:1 by Bitcoin. Ren also decentralizes the custody of the BTC. User’s deposit BTC to RenVM, which holds that BTC and mints renBTC with 1:1 ratio.

_**Smart-contract risks**_: The renBTC smart [contract](https://etherscan.io/address/0xeb4c2781e4eba804ce9a9803c67d0893436bb27d) was launched in May 2020, making it a fairly _mature contract_. The number of transactions since launch stands at 34,738. The total [amount](https://explorer.bitquery.io/ethereum/token/0xeb4c2781e4eba804ce9a9803c67d0893436bb27d) transacted is \~ 1,116,999 renBTC, with a median of \~ 0.23 renBTC.

_**Counter-party risks**_: Ren project is a trustless, decentralized virtual machine, which connects blockchains via the REN tokens. The Ren project aims to be the leading [decentralized](https://forum.renproject.io/t/ren-governance-process/392) universal interoperability protocol in the crypto ecosystem. There are 3,062 token [holders](https://etherscan.io/token/tokenholderchart/0xeb4c2781e4eba804ce9a9803c67d0893436bb27d) at the time of writing.

_**Market risks**_: At present, the [market](https://www.coingecko.com/en/coins/renbtc) capitalization for renBTC is more than $679 million and a circulation coin supply of 13,817.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- None at the time of writing.

## **sBTC**

sBTC differs from the rest, as Bitcoins does not back it. The value of sBTC is kept stable through an over-collateralization mechanism leveraging Synthetix SNX tokens.

_**Smart-contract risks**_: The sBTC smart [contract](https://etherscan.io/token/0xfE18be6b3Bd88A2D2A7f928d00292E7a9963CfC6) was launched in September 2019, making it a _mature contract_. The number of transactions since launch stands at 29,636. The total [amount](https://explorer.bitquery.io/ethereum/token/0xfE18be6b3Bd88A2D2A7f928d00292E7a9963CfC6) transacted is \~ 139,697 sBTCUSD, with a median of \~ 0.199 sBTC.

_**Counter-party risks**_: Synthetix is a decentralized platform on Ethereum for the creation of Synths: on-chain synthetic assets that track the value of real-world assets. The key decentralised autonomous organisations ([DAOs](https://docs.synthetix.io/governance/)) are the - Spartan Council, Protocol DAO, Synthetix DAO, Ambassadors DAO and the Grants DAO. There are 1,342 token [holders](https://etherscan.io/token/tokenholderchart/0xfE18be6b3Bd88A2D2A7f928d00292E7a9963CfC6) at the time of writing.

_**Market risks**_: Synthetix is composed of a smart contract infrastructure and a set of incentives which maintains Synth prices. At present, the [market](https://www.coingecko.com/en/coins/sbtc) capitalization for sBTC is over $176 million and a circulation coin supply of 3,576.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- None at the time of writing.

## **sETH**

Synthetix is a decentralised synthetic asset issuance protocol built on Ethereum. These synthetic assets are collateralized by the Synthetix Network Token (SNX) which when locked in the contract enables the issuance of synthetic assets (Synths).

_**Smart-contract risks**_: The sETH smart [contract](https://etherscan.io/token/0x5e74c9036fb86bd7ecdcb084a0673efc32ea31cb) was launched in September 2019, making it a _mature contract_. The number of transactions since launch stands at 96,733. The total [amount](https://explorer.bitquery.io/ethereum/token/0x5e74c9036fb86bd7ecdcb084a0673efc32ea31cb) transacted is \~ 8,978,550 sETH, with a median of \~ 4.4 sETH.

_**Counter-party risks**_: Synthetix is a decentralized platform on Ethereum for the creation of Synths: on-chain synthetic assets that track the value of real-world assets. The key decentralised autonomous organisations ([DAOs](https://docs.synthetix.io/governance/)) are the - Spartan Council, Protocol DAO, Synthetix DAO, Ambassadors DAO and the Grants DAO. There are 2,044 token [holders](https://etherscan.io/token/tokenholderchart/0x5e74c9036fb86bd7ecdcb084a0673efc32ea31cb) at the time of writing.

_**Market risks**_: Synthetix is composed of a smart contract infrastructure and a set of incentives which maintains Synth prices. At present, the [market](https://www.coingecko.com/en/coins/seth) capitalization for sETH is over $346 million and a circulation coin supply of 104,954.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- Synthetix Reverses [Oracle Error-Caused](https://cointelegraph.com/news/synthetix-reverses-oracle-error-caused-misplaced-seth-in-exchange-for-a-bug-bounty) Misplaced sETH.

## **sUSD**

sUSD is a synthetic USD token created by staking Synthetix Network Token (SNX) or ETH in Synthetix, a decentralized synthetic asset issuance protocol built on Ethereum.

_**Smart-contract risks**_: The sUSD smart [contract](https://etherscan.io/token/0x57ab1ec28d129707052df4df418d58a2d46d5f51) was launched in September 2018 and migrated to the current contract in May 2020, making it a _mature contract_. The number of transactions since launch stands at 781,978. The total [amount](https://explorer.bitquery.io/ethereum/token/0x57ab1ec28d129707052df4df418d58a2d46d5f51) transacted is \~ 33,424,667,667 sUSD, with a median of \~ 802.5 sUSD.

_**Counter-party risks**_: Synthetix is a decentralized platform on Ethereum for the creation of Synths: on-chain synthetic assets that track the value of real-world assets. The key decentralised autonomous organisations ([DAOs](https://docs.synthetix.io/governance/)) are the - Spartan Council, Protocol DAO, Synthetix DAO, Ambassadors DAO and the Grants DAO. There are 12,576 token [holders](https://etherscan.io/token/tokenholderchart/0x57ab1ec28d129707052df4df418d58a2d46d5f51) at the time of writing.

_**Market risks**_: Synthetix is composed of a smart contract infrastructure and a set of incentives which maintains Synth prices. At present, the [market](https://www.coingecko.com/en/coins/susd) capitalization for sUSD is over $288 million and a circulation coin supply of over 288 million.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- None at the time of writing.

## **tBTC**

tBTC is an open-source project of Keep, Summa and the Cross-Chain Group. tBTC, an ERC-20 token, is backed 1:1 by Bitcoin and truly decentralized.

_**Smart-contract risks**_: The tBTC smart [contract](https://etherscan.io/token/0x1bBE271d15Bb64dF0bc6CD28Df9Ff322F2eBD847) was launched in May 2020, making it a _mature contract_. The number of transactions since launch stands at 188. The total [amount](https://explorer.bitquery.io/ethereum/token/0x1bBE271d15Bb64dF0bc6CD28Df9Ff322F2eBD847) transacted is \~ 37 tbTC, with a median of \~ 0.0005 tBTC.

_**Counter-party risks**_: tBTC is a safe and permissionless bridge between BTC and ETH. The first version of tBTC has been built with no ability to upgrade contracts, following a Bitcoin-inspired philosophy of immutability and opt-in [governance](https://tbtc.network/developers/tbtc-security-model/). Any future versions of tBTC will be new systems, and require social coordination to “upgrade”, like how a hard fork might on Bitcoin. There are 32 token [holders](https://etherscan.io/token/tokenholderchart/0x1bBE271d15Bb64dF0bc6CD28Df9Ff322F2eBD847) at the time of writing.

_**Market risks**_: At present, the [market](https://www.coingecko.com/en/coins/alchemix-usd) capitalization for tBTC is $ 42,688,862 and a circulation coin supply of 873.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- 10-day [emergency](https://www.theblockcrypto.com/post/65941/tbtc-post-mortem-describes-how-a-missed-smart-contract-bug-forced-the-developers-to-press-the-emergency-pause-button) pause for new deposits after identifying a smart contract bug.

## **USDC**

USDC is an ERC20 token pegged 1:1 to the US dollars (USD). USDC is issued by regulated financial institutions, backed by fully reserved assets, redeemable on a 1:1 basis for US dollars, and governed by Centre, a membership-based consortium that sets technical, policy and financial standards for stablecoins.

_**Smart-contract risks**_: The USDC smart [contract](https://etherscan.io/token/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48) was launched in September 2018, making it a _mature contract_. The number of transactions since launch stands at over 24 million. The total [amount](https://explorer.bitquery.io/ethereum/token/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48) transacted is over 1,5 trillion USDC, with a median of \~ 1,050 USDC.

_**Counter-party risks**_: USDC is [governed](https://www.centre.io/hubfs/PDF/Centre_Blacklisting_Policy_20200512.pdf?hsLang=en) by The Centre Consortium which could block transactions and blacklist addresses. There are over 1 million token [holders](https://etherscan.io/token/tokenholderchart/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48) at the time of writing.

_**Market risks**_: USDC has gained wide adoption since its inception because of its easy integration with all ERC-20 compatible wallets. At present, the [market](https://www.coingecko.com/en/coins/usd-coin) capitalization for USDC is \~ $27 billion and a circulation coin supply of \~ 27 billion.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- None at the time of writing.

## **USDT**

USDT, like USDC, is pegged 1:1 to the USD. It’s the oldest USD backed stablecoin.

_**Smart-contract risks**_: The USDT smart [contract](https://etherscan.io/address/0xdac17f958d2ee523a2206206994597c13d831ec7) was launched in November 2017, making it a _mature contract_. The number of transactions since launch stands at over 109 million. The total [amount](https://explorer.bitquery.io/ethereum/token/0xdac17f958d2ee523a2206206994597c13d831ec7) transacted is over 2.4 trillion USDT, with a median of \~ 726 USDT.

_**Counter-party risks**_: USDT is [pegged](https://wallet.tether.to/transparency) to USD and Euros on a scale of 1:1 by a Hong Kong based firm, Tether Holdings Limited. There are over 3.4 million token [holders](https://etherscan.io/token/tokenholderchart/0xdac17f958d2ee523a2206206994597c13d831ec7) at the time of writing.

_**Market risks**_: USDT is the most widely integrated digital-to- fiat currency today. At present, the [market](https://www.coingecko.com/en/coins/tether) capitalization for USDT is \~ $65 billion and a circulation coin supply of \~ 65 billion.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- None at the time of writing.

## **wBTC**

Wrapped BTC is an ERC20 token backed 1:1 by the actual Bitcoin. Users can swap their BTC for WBTC through merchants, like Kyber, Set Protocol, Ren, etc.

_**Smart-contract risks**_: The wBTC smart [contract](https://etherscan.io/address/0x2260fac5e5542a773aa44fbcfedf7c193bc2c599) was launched in November 2018, making it a _mature contract_. The number of transactions since launch stands at over 419,000. The total [amount](https://explorer.bitquery.io/ethereum/token/0x2260fac5e5542a773aa44fbcfedf7c193bc2c599) transacted is \~ 10,203,162 wBTC, with a median of \~ 0.26 wBTC.

_**Counter-party risks**_: Merchants perform key roles for the WBTC community as [administrators](https://wbtc.network/assets/wrapped-tokens-whitepaper.pdf) who start minting newly wrapped tokens and burning wrapped tokens which are performed by the Custodians. There are 35,930 token [holders](https://etherscan.io/token/tokenholderchart/0x2260fac5e5542a773aa44fbcfedf7c193bc2c599) at the time of writing.

_**Market risks**_: Minting in the wrapped framework is started by a merchant and performed by a custodian. At present, the [market](https://www.coingecko.com/en/coins/wrapped-bitcoin) capitalization for wBTC is over $9 billion and a circulation coin supply of over 194,000.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- Price [manipulation](https://www.trustnodes.com/2020/02/17/flashloan-haxor-sent-wbtcs-price-to-4000-on-kyber) through flashloans.

## **wCUSD**

Wrapped Celo Dollars is an ERC20 token, representing a 1:1 share of Celo Dollar (CUSD). wCUSD provides a simple and secure bridge to Ethereum’s DeFi ecosystem.

_**Smart-contract risks**_: The wCUSD smart [contract](https://etherscan.io/token/0xad3e3fc59dff318beceaab7d00eb4f68b1ecf195) was launched in December 2020, making it a relatively _young contract_. The number of transactions since launch stands at 52. The total [amount](https://explorer.bitquery.io/ethereum/token/0xad3e3fc59dff318beceaab7d00eb4f68b1ecf195) transacted is \~ 2,247,874 wCUSD, with a median of \~ 988 wCUSD.

_**Counter-party risks**_: Wrapping CUSD to wCUSD is permissionless and so is the reverse process to unwrap. There are 7 token [holders](https://etherscan.io/token/tokenholderchart/0xad3e3fc59dff318beceaab7d00eb4f68b1ecf195) at the time of writing.

_**Market risks**_: Minting in the wrapped framework is started by a merchant and performed by a custodian. At present, the fully diluted [market](https://coinmarketcap.com/currencies/wrapped-celo/) capitalization for wCUSD is over $3 million and a total coin [supply](https://www.coingecko.com/en/coins/wrapped-celo-dollar) of close to 700,000.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

· None at the time of writing.

## **WETH**

ETH was the proto-token of the Ethereum Alt tokens, which means it was built before the ERC-20 standard existed. Wrapped ETH is an ERC20 token backed 1:1 by ETH, allowing trade directly with ALT coins.

_**Smart-contract risks**_: The wETH smart [contract](https://etherscan.io/address/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2) was launched in December 2017, making it a _mature contract_. The number of transactions since launch stands at over 2.3 million. The total [amount](https://explorer.bitquery.io/ethereum/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2) transacted is \~ 2,322,213,729 wETH, with a median of \~ 0.87 wETH.

_**Counter-party risks**_: Wrapping ETH to wETH is permissionless and so is the reverse process to unwrap. There are 225,770 token [holders](https://etherscan.io/token/tokenholderchart/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2) at the time of writing.

_**Market risks**_: Users can verify that WBTC is fully-backed via on-chain proof of reserves. At present, the [market](https://coinmarketcap.com/currencies/weth/) capitalization for wETH is over 3.7 billion (fully diluted) and a total coin supply of over 1.1 million.

_**Notable incidents**_: The following incidents and/or bugs were identified relating to the protocol:

- None at the time of writing.
