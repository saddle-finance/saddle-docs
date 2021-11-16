---
description: Layer 2 is a different network running atop the Ethereum Mainnet (Layer 1).
---

# Layer 2 Guide

Saddle is launching on L2 starting with an incentivized stablecoin pool. The first Saddle pool on Arbitrum is a stablecoin pool composed of USDC, USDT, nUSD, and MIM launched in collaboration with [Synapse Protocol](https://twitter.com/synapseprotocol).

This pool will be incentivized with 4,958,678 SDL tokens (\~0.5% of total supply) over \~6 months. Read more about pool incentives in the [tokenomics section](sdl-token.md). Incentives distribution will start on 11/18/21 12:00AM UTC.

**`Note:`**` Initially Saddle will launch on Arbitrum and (later) Optimism.`

### **ETHEREUM LAYER 2 SOLUTIONS** <a href="_toc87951811" id="_toc87951811"></a>

Ethereum network is a popular destination for most decentralized apps (dApps). The popularity has led to enormous activity of Ethereum, which results in high gas fees and slow transaction speed. [Layer 2 networks](https://ethereum.org/en/developers/docs/scaling/layer-2-rollups/) are a solution for Ethereum scaling challenges.

Layer 2 is a different network running atop the Ethereum Mainnet (layer 1) and stays on the Mainnet as smart contract. Thus, layer 2 solutions help scale applications by handling transactions off the Ethereum Mainnet (layer 1) while taking advantage of the robust decentralized security model of Mainnet.

### **Rollups** <a href="_toc87951812" id="_toc87951812"></a>

Rollups perform transaction execution outside the Ethereum Mainnet (layer 1) and post the transaction data on layer 1. The “rollup” is so-called because the layer 2 solutions roll up transactions and fit them into a single block in layer 1. As transaction data is on layer 1, rollups are secured by layer 1. There are two types of rollups:

**1) Optimistic rollup **assumes transactions are valid by default (hence the name optimistic) and only runs computation, via a fraud proof, in the event of a challenge. Optimistic rollups are scalable because they don't do any computation by default. If someone notices a fraudulent transaction, the rollup will execute a fraud-proof and run the transaction's computation, using the available state data.

| **Advantages**                                                                    | **Disadvantages**                                                                                                        |
| --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| <ul><li>Low gas fees</li><li>Scalable</li><li>Smart contract compatible</li></ul> | <ul><li>Long wait times for on-chain transaction because of potential fraud challenges (may take up to a week)</li></ul> |

Major implementations of optimistic rollup: [Optimism](https://optimism.io), [Arbitrum](https://arbitrum.io), [Boba](https://boba.network), [Fuel Network](https://fuel.sh).

**2) Zero-knowledge rollup** runs computation off-chain and submits a validity proof to the chain. Also known as ZK rollups, these scaling solutions “roll up” many transactions off-chain and generate a cryptographic proof known as SNARK (validity proof) for the whole bundle. The validity proof is posted on layer 1, and the proof can be quickly verified, and invalid batches are rejected straightaway.

| **Advantages**                                                                                 | **Disadvantages**                                                                           |
| ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| <ul><li>Low gas fees</li><li>Scalable</li><li>Shorter wait time for fund withdrawals</li></ul> | <ul><li>Some solutions don't have EVM support (ZKSync 2.0 is expected in Q4 2021)</li></ul> |

Major implementations of ZK-rollup: [Loopring](https://loopring.org/#/), [Aztek 2.0](https://aztec.network), [Starkware](https://starkware.co), [zkTube](https://zktube.io).

### **ARBITRUM & OPTIMISM LAYER 2** <a href="_toc87951813" id="_toc87951813"></a>

[Arbitrum](https://arbitrum.io) and [Optimism](https://optimism.io) are both layer 2 solutions with a lot in common – both implement optimistic rollup, have smart contracts living in Ethereum Mainnet (layer 1), and use ETH as their currency.

**Note**: The challenge window for fraud and dispute is _**one week**_ for both Optimism and Arbitrum. Your transactions in a bundle under suspicion can be held up for one week before they’re verified, and funds are released. However, the challenge process varies across Optimism and Arbitrum.

* **Arbitrum**: When a [challenge](https://developer.offchainlabs.com/docs/dispute\_resolution#dispute-resolution) is submitted, Arbitrum uses an offchain dispute resolution process to isolate a single step within a transaction. The isolated step is then sent to EVM for final verification.
* **Optimism**: When a [challenge](https://community.optimism.io/docs/protocol/fraud-proofs.html) is submitted, the entire transaction in question is run through the Ethereum EVM.

### **Arbitrum: Moving Assets In And Out (Deposit/Withdraw)** <a href="_toc87951814" id="_toc87951814"></a>

You can transfer assets from Layer 1 Ethereum to Layer 2 Arbitrum through the [Arbitrum Bridge](https://bridge.arbitrum.io). Follow this [guideline](https://arbitrum.io/bridge-tutorial/) to deposit and withdraw crypto assets in Arbitrum.

### **Optimism: Moving Assets In And Out (Deposit/Withdraw)** <a href="_toc87951815" id="_toc87951815"></a>

Follow these guidelines to move crypto assets in Optimism.

* **Deposit Ether** via [The Teleporter](https://portr.xyz) or [The Optimism Gateway](https://gateway.optimism.io). Follow this guide [here](https://community.optimism.io/docs/users/deposit.html#ether).
* **Deposit ERC-20 tokens** via [The Optimism Gateway](https://gateway.optimism.io) or [3rd Party Bridges](https://www.optimism.io/apps/bridges). Follow this guide [here](https://community.optimism.io/docs/users/deposit.html#erc-20-tokens).
* **Withdraw Ether** via [The Optimism Gateway](https://gateway.optimism.io). Follow this guide [here](https://community.optimism.io/docs/users/withdrawal.html#ether).
* **Withdraw ERC-20 tokens** via [The Optimism Gateway](https://gateway.optimism.io) or [3rd Party Bridges](https://www.optimism.io/apps/bridges). Follow this guide [here](https://community.optimism.io/docs/users/withdrawal.html#erc-20-tokens).

**`Note:`**` Initially Saddle will launch on Arbitrum and (later) Optimism.`

### **BRIDGES ** <a href="_toc87951816" id="_toc87951816"></a>

Like physical bridges which connect locations enabling movement of people and wealth, in the crypto ecosystem, a bridge is a connection between blockchain networks operating under different conditions. Bridges establish interoperability by enabling transfer of assets and information.

The communities built around individual blockchain networks need to collaborate and cooperate for the ecosystem to be truly decentralized and open. Bridges help the benefits to cross the boundaries and grow beyond the genesis ecosystem.

Therefore, bridges are not only about connecting Layer 1 Mainnet and Layer 2 solutions. For the ecosystem to mature and blossom, we require bridges across Layer 2 as well. Besides the bridges mentioned above, there are other bridges available to transfer assets across Layer 1/Layer 2. Let’s explore a few bridges now.

### **Hop Protocol** <a href="_toc87951817" id="_toc87951817"></a>

[Hop](https://hop.exchange) is a scalable rollup-to-rollup general token bridge. Hop allows users to transfer tokens directly and easily between Layer 2s, sidechains, and Layer 1 Ethereum. With Hop, users can send tokens from one rollup to another almost immediately without having to wait for the rollup’s challenge period. [Built with Saddle](https://docs.saddle.finance/build-with-saddle#hop-protocol), Hop is a protocol built for quick, low cost, and trustless transfer of assets.&#x20;

Check out the guide [here](https://medium.com/hop-protocol/hop-send-tokens-across-rollups-30f14c432f7c) to get started.&#x20;

### **Synapse Protocol** <a href="_toc87951818" id="_toc87951818"></a>

[Synapse](https://synapseprotocol.com) is another bridge that provides users the option for cost-efficient, user friendly, and low-slippage stablecoin trade. Synapse unifies the thriving L1/L2 ecosystem, allowing users to seamlessly bridge assets across the most popular chains. Synapse allows users to frictionlessly transfer stablecoins to/from Arbitrum, Avalanche, BSC, Ethereum, Fantom, Polygon (as well as ETH to/from Arbitrum) - with more chains and assets in the works.&#x20;

Check out the guide [here](https://docs.synapseprotocol.com/how-to/bridge) to get started.&#x20;

### **Celer Bridge** <a href="_toc87951819" id="_toc87951819"></a>

[Celer](https://www.celer.network) network is a layer-2 scaling platform that brings fast, secure, and low-cost blockchain applications on Ethereum, Polkadot and other blockchains to mass adoption. Celer bridge ([cBridge](https://cbridge.celer.network)) can be used to instantly transfer token cross-chain and cross-layer between any two of these networks: Ethereum, Arbitrum, Polygon, and Binance Smart Chain. cBridge keeps the liquidity flow between these loosely coupled networks without long delays or a trust-based custodian.

Check out the guide [here](https://cbridge-docs.celer.network/#/) to get started.

### **Connext Network** <a href="_toc87951820" id="_toc87951820"></a>

[Connext](https://connext.network) is a protocol for fast, fully noncustodial transfers and contract calls between EVM-compatible systems. As a cross-chain routing network, Connext enables seamless communication between the Ethereum mainnet, L2 systems, and shards. Connext routers act as the backbone of the network, providing liquidity for user swaps and earning fees in return.

Check out the guide [here](https://docs.connext.network) to get started.

### **WORKING WITH SADDLE L2 POOLS** <a href="_toc87951821" id="_toc87951821"></a>

Swapping and LPing are the same as on L1 (check out the [deposit](https://docs.saddle.finance/saddle-pools#deposit) and [withdraw](https://docs.saddle.finance/saddle-pools#withdraw) guides), but ensure you have **successfully switched the network**.

### **Switching from L1 to L2 Network** <a href="_toc87951822" id="_toc87951822"></a>

* **Step 1:** Head to [https://saddle.exchange/#/pools](https://saddle.exchange/#/pools).
* **Step 2:** Switch the network from **Ethereum to Arbitrum** to LP or trade of Saddle’s L2 Stablecoin pool.

![](.gitbook/assets/0)

* **Step 3: **Confirm the** **network switch

![](<.gitbook/assets/1 (1)>)

* **Step 4 : **Once switched, working with L2 pools is the same as on L1 pools (check out the [deposit](https://docs.saddle.finance/saddle-pools#deposit) and [withdraw](https://docs.saddle.finance/saddle-pools#withdraw) guides).

### **Incentives** <a href="_toc87951823" id="_toc87951823"></a>

Depositing assets into a pool on Saddle allows users to take part in the protocol as liquidity providers and earn reward incentives.

The Saddle stablecoin pool on Arbitrum will initially be incentivized with 4,958,678 SDL tokens over \~6 months. Additional incentives may be added alla governance / community vote.&#x20;

Incentives distribution will start on 11/18/21 12:00AM UTC, in order to give users who wish to participate a fair window to move their liquidity.

Read more about pool incentives in the [tokenomics section](sdl-token.md).
