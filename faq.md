# 常见问题解答

回答您关于AMM、代币化比特币、和Saddle app等的相关问题。

还有更多问题吗？[加入我们的Discord](https://discord.gg/hX8RZFBW9R)

## 问题和解答

### 什么是Saddle？

Saddle是一款针对固定价值加密资产的自动做市商（AMM）。Saddle能使任何持有固定价值加密资产的用户以最小滑点在其他固定资产之间进行交易，从而确保用户不会在进行交易时损失资产价值。

### 什么是代币化比特币？

代币化比特币是从比特币区块链被“存款”到以太坊区块链的BTC。此时，BTC会被保存于一存款合同中，该合同接着在以太坊上“铸造”和BTC具有相同价值的代币，但是此代币却具有ERC-20代币的所有功能。代币化比特币包括了tBTC、renBTCc、WBTC、和sBTC等。

### 什么是固定价值加密资产？

固定价值加密资产是指透过某种方式，将其价值与一基础资产挂钩。以稳定币或代币化比特币为例，这些货币的价值永远都分别是1美元。

目前固定价值加密资产能透过不同的机制来将其价值固定，某些资产，例如sBTC或sUSD，是运用综合的的方式来维持他们的挂钩（此例是透过抵押SNX）。还有一些资产则是透过实际基础资产的支持和可赎性，来维持其挂钩，而这个机制亦或不需要许可（例如tBTC），亦或需经过集中保管人（例如WBTC、USDC）。

这些不同的方式和相关的风险是为什么同一类型的固定价值加密资产会有轻微的价格波动。

### 为什么Saddle的启动要使用代币化比特币？

比特币是市值最大的加密货币，且以太坊上代币化比特币的数量仍持续呈爆炸式的增长—2020年的供应量已增加了高达135倍。但尽管如此，代币化比特币在功能与支持方面通常不会被优先考虑。我们深信比特币应被视为DeFi中的一等公民。

### Saddle也会支持其他资产池吗？何时开始？

会的！我们日后将会开始支持其他固定价值加密资产的交易，例如稳定币和以太坊代币。这些资产池预计会在2021年第一或第二季度上线。

### Saddle有发行代币吗？

Saddle目前没有发行代币。

### Saddle的受保护启动—“治理证明”是什么？有谁能参与？

Saddle上线时启用了治理证明（PoG），借此实施一定的限制来保护我们的用户，防止女巫攻击。起初，TVL资金池的上限为150 BTC，且每一个地址的存款限额为1 BTC，尔后这些限制将会于每1至2周提高一次。

若LP欲符合PoG资格，该地址必须透过下列任一方式来证明其积极的网路参与：

* 链上投票或委托 \(MKR, COMP, YFI, YAM, CRV, UNI, UMA, Moloch DAO\)
* [Snapshot](https://snapshot.page/)链下投票（所有协议）
* 抵押SNX和铸造sUSD \(&gt;$20\)

[这里提供了完整的合格地址清单](https://github.com/saddle-finance/saddle-allowlist-addresses)。PoG只是暂时的，并会在将来被逐步淘汰。

我们采用此种受保护的启动是为了建立一个更可控的环境，以确保平稳的启动、减少变数、并在一个可控的环境下对用户的资金负责。我们的首要目标是要确保应用程序运行无碍、保障用户资金的安全、以及使我们的支持者、开发人员、和用户皆对于我们能成功并公正启动的能力保有信心。

_受保护的启动并不适用于AMM。用户能立即在启动时在不同代币化比特币类型之间进行交易。_

### 为什么当我使用Saddle时会收到“很抱歉，这个地址没有存款的资格…”的信息？

Saddle的启动使用了名为治理证明（PoG）的受保护启动。若您看到错误信息，代表您所使用的钱包尚未在上列的治理过程中使用过。您可以尝试连接另一个钱包，或者等待受保护的启动结束。

### 谁可以使用Saddle？

在启动时，**每个人都**可以使用Saddle的AMM在代币化比特币配对之间进行交易。

然而在启动时，欲在Saddle上成为流动性提供者的用户必须参与过特定的治理过程， 您可参考“Saddle的受保护启动，‘治理证明’，是什么？…”问题来了解更多细节。

### 如何使用Saddle？

进入[Saddle App](https://saddle.exchange)便能立即开始使用！

### Saddle的流动性提供者可获得什么奖励？

Keep Network团队已承诺每周提供250,000 KEEP作为流动性提供者的奖赏。这意味着若达到TVL上限，LP能获得高达~30%的年度百分比收益率（APY）！[点击这里](https://keep.network/)了解更多关于Keep Network、KEEP、和抵押KEEP以增加APY的机会。

### 什么是tBTC？

tBTC是第一个真正去中心化、具安全性的代币化比特币，其安全性受到Keep Network的保护。而Keep Network则是一种保护隐私权的区块链解决方案。Keep Network将铸造tBTC的密钥储存在去中心化的“keeps”里，因而消除了中心化的弱点。

### 碍于受保护的启动，我无法为Saddle提供流动性。什么时候我才能开始使用Saddle呢？

受保护的启动会随着时间被逐步淘汰，届时任何人都能为Saddle的资金池提供流动性。

同时，任何人都能透过Saddle 的AMM在不同代币化比特币类型之间进行交易。

### 使用Saddle需要多少费用？

在启动时，从Saddle资金池取款不需任何费用。接着我们会采用费用递减机制，将费用在您首次提供流动性后的一个月内递减至0bps。

### 是谁创建了Saddle？

Saddle是由一群DeFi专家所创建，他们皆具有在Uber、Amazon、和Square等Web2公司多年的开发经验。您可能已经在YFI社区中与我们的创始人[Sunil](https://www.linkedin.com/in/sunilsrivatsa/)（亦称为[devops199fan](https://twitter.com/devops199fan)，是位多重签名的持有者）有过互动，或者已使用过我们团队成员所创建的工具，例如[John](https://www.linkedin.com/in/jongseunglim/)（亦称为[Weeb\_Mcgee](https://twitter.com/Weeb_Mcgee)）的[yieldfarming.info](https://yieldfarming.info/)。

### Saddle安全吗？

Saddle已经过Certik、Quantstamp、和Open Zeppelin等公司的审计。[点击这里](https://github.com/saddle-finance/saddle-audits)阅读审计报告。

### 如何关注Saddle?

[Discord](https://discord.gg/hX8RZFBW9R)! [Twitter](https://twitter.com/saddlefinance)! [Telegram](https://t.me/saddle_finance)! [Github](https://github.com/saddle-finance)! [Medium](https://medium.com/saddle)!

