# 关于Saddle

Saddle是一个自动做市商（AMM），旨在实现固定价值加密资产之间的高效交易。Saddle上线的同时也推出了代币化比特币矿池，使其用户能在renBTC、WBTC、sBTC、和renBTC之间进行交易并提供流动性。

Saddle是从[Thesis](https://thesis.co/)分拆出来之子公司，而母公司Thesis则是[tBTC](https://tbtc.network/)、[Keep](https://keep.network/)和[Fold](https://foldapp.com/)等项目背后的加密风险投资公司。

## 了解固定价值加密资产

### 什么是固定价值加密资产？

固定价值加密资产是指透过某种方式，将其价值与一基础资产挂钩。以稳定币或代币化比特币为例，这些货币的价值永远都分别是1美元。

目前固定价值加密资产能透过不同的机制来将其价值固定，某些资产，例如sBTC或sUSD，是运用综合的的方式来维持他们的挂钩（此例是透过抵押SNX）。还有一些资产则是透过实际基础资产的支持和可赎性，来维持其挂钩，而这个机制亦或不需要许可（例如tBTC），亦或需经过集中保管人（例如WBTC、USDC）。

这些不同的方式和相关的风险是为什么同一类型的固定价值加密资产会有轻微的价格波动。

### 固定价值加密资产有什么问题？

此类的资产交易可能成本高昂且效率低下，最后因为高滑点和交易手续费而导致资本损失。

### Saddle如何解决该问题？

为解决固定价值加密资产间交易的问题，Saddle对此提供一款经过专门设计改良的AMM，让用户能以最小滑点在这些资产之间进行交易。

## Saddle的解决方案

### 比特币为一等公民

比特币是市值最大的加密货币，且以太坊（Ethereum）上代币化比特币的数量仍持续呈爆炸式的增长—2020年的供应量已增加了高达[135](https://btconethereum.com/)倍。但尽管如此，代币化比特币在功能与支持方面通常不会被优先考虑。我们深信比特币应被视为DeFi中的一等公民。

### Virtual Synth功能支持

Virtual Synths是[SIP-89](https://sips.synthetix.io/sips/sip-89)所引入的一个Synthetix新特性。在“[关于Virtual Synths以及何处寻找他们](https://blog.synthetix.io/virtual-synths/)”一文中，SNX创始人Kain Warwick完整的概述了其潜在的发展。简而言之，Virtual Synths能够使Saddle平台上的任何资产实现大型、低滑点的交易。我们正积极的进行此项整合，并会在不久的将来分享更多相关细节。Virtual Synths是开启固定价值加密资产之间深层链上流动性的关键，而我们的目标是成为Synthetix生态系统的首要出入通道。

### 奖励机制留住LP

DeFi协议仍在不停探讨如何适当的激励及留住流动性提供者（LPs）。其中一种常见的机制是取款时的固定百分比费用（例如Yearn Vaults）。但是这种机制无法奖励长期的流动性提供者。为解决此问题，Saddle重新配置了取款费用，使该费用在一个月内减少至0。在另行通知前，此费用将于上线后暂时取消。我们现正努力研商更多其他的方式来激励LP，敬请保持关注！

### 安全性

保障用户资金的安全性是我们的首要之务。Saddle[运用Solidity](https://github.com/saddle-finance/saddle-contract)来实现[StableSwap](https://www.curve.fi/stableswap-paper.pdf)算法。使用任何涉及资金的代码皆需要格外的谨慎和详尽的审查，这也是为什么我们透过[Certik](https://certik.foundation/)、[Quantstamp](https://quantstamp.com/)、和[Open Zeppelin](https://openzeppelin.com/)，连续进行了三次智能合约审计。[点击这里阅读审计报告](https://github.com/saddle-finance/saddle-audits)。除此之外，我们还执行了名为“治理证明”（Proof of Governance）的[受保护启动](https://medium.com/electric-capital/derisking-defi-guarded-launches-2600ce730e0a)，下面将有更多细节。

## 关注Saddle最新消息

请到[Discord](https://discord.gg/hX8RZFBW9R)、[Twitter](https://twitter.com/saddlefinance)、[Telegram](https://t.me/saddle_finance)、[Github](https://github.com/saddle-finance)、和[Medium](https://medium.com/saddle)上关注我们。
