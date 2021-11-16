---
description: We hire well reputed external agencies to audit our smart contract codes.
---

# Smart Contract Security

Smart contracts are subject to flaws, coding errors, unintended behavior, and inefficiencies. Once deployed in the blockchain, smart contracts are immutable \(cannot change\). At Saddle, we take the security of the smart contract seriously.

We conduct our own internal security audit of the smart contract code we’ve written. As a further check, to make sure Saddle’s code is proper and working as intended, we hire well reputed external agencies to audit our smart contract codes.

As for now, we have passed security auditing on all Saddle smart contracts, from the following auditors, with no issues.

| **AUDITOR**                              | **PROTOCOL AUDIT**                                                                              | **VIRTUAL SWAP AUDIT**                                                                                      | **TOKEN AUDIT**                                                                                       |
| :--------------------------------------- | :---------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------- |
| [Certik](https://certik.io/)             | [PASSED](https://github.com/saddle-finance/saddle-audits/blob/master/10-29-2020_Certik.pdf)     | N/A                                                                                                         | N/A                                                                                                   |
| [Quantstamp](https://quantstamp.com/)    | [PASSED](https://github.com/saddle-finance/saddle-audits/blob/master/12-09-2020_Quantstamp.pdf) | [PASSED](https://github.com/saddle-finance/saddle-audits/blob/master/03-31-2021_Quantstamp_VirtualSwap.pdf) | [PASSED](https://github.com/saddle-finance/saddle-audits/blob/master/10-27-2021_Quantstamp_Token.pdf) |
| [OpenZepplin](https://openzeppelin.com/) | [PASSED](https://blog.openzeppelin.com/saddle-contracts-audit/)                                 | N/A                                                                                                         | N/A                                                                                                   |

_**Disclaimer**:_ Security audits don’t eliminate all risks. Using Saddle as an exchange for a user should be significantly less risky, but please bear in mind there are still risks. Refer to the risks section for more details.

### **Certik Audit Report**

Founded in 2018 by professors at Yale University and Columbia University, CertiK is a pioneer in blockchain security, using best-in-class AI technology to secure and monitor blockchain protocols and smart contracts. CertiK’s mission is to secure the cyber world. Starting with blockchain, CertiK applies innovations from academia into enterprise, enabling mission-critical applications to be built with security and correctness.

![](.gitbook/assets/0%20%285%29.png)

CERTIX AUDIT REPORT FOR SADDLE PROTOCOL - 29 OCT 2020

### **Quantstamp Audit Report**

Quantstamp is the leader in blockchain security, having performed over 200 audits and secured over $100 billion in value. Their top team of PhDs and security professionals have a combined total of over 1,000 Google Scholar citations. They have audited many blockchain systems, including Ethereum 2.0, Binance Smart Chain, Flow, Cardano, and Avalanche and have secured successful innovative applications such as Maker, Compound, and NBA Top Shot.

![](.gitbook/assets/1%20%285%29.png)

QUANTSTAMP AUDIT REPORT FOR SADDLE PROTOCOL - 10 DEC 2020

![](.gitbook/assets/2%20%282%29.png)

QUANTSTAMP AUDIT REPORT FOR SADDLE VIRTUAL SWAP – 31 MAR 2021

### **OpenZeppelin Audit Report**

Founded in 2015, OpenZeppelin has set industry standards for building secure distributed systems. OpenZeppelin builds developer tools and performs security audits for distributed systems that power multimillion-dollar economies. OpenZeppelin verifies the distributed systems work as intended by performing an audit. Their engineers fully review the system's architecture and codebase and then write a thorough report that includes actionable feedback for every issue found.

![](.gitbook/assets/3%20%287%29.png)

OPENZEPPLIN AUDIT REPORT FOR SADDLE PROTOCOL - 11 DEC 2020

## **SADDLE ADMIN KEYS SECURITY**

A [Gnosis Safe](https://gnosis-safe.io/) multisig secures Saddle’s admin keys. Gnosis is a trusted platform to manage digital assets in Ethereum. Gnosis Safe is a smart contract wallet running on Ethereum, which requires a minimum number of people to approve a transaction before it can occur \(M-of-N\). This assures that no single person could compromise the funds.

A [3/5 Gnosis Safe multisig](https://etherscan.io/address/0x3F8E527aF4e0c6e763e8f368AC679c44C45626aE) secures Saddle's admin keys. The signers are Mariano Conti, Kain Warwick, DegenSpartan, Klim K, and Damir Bandalo.

| **NAME**                                          | **ENS**           | **ADDRESS**                                |
| :------------------------------------------------ | :---------------- | :----------------------------------------- |
| [Mariano Conti](https://twitter.com/nanexcool)    | -                 | 0x6F2A8Ee9452ba7d336b3fba03caC27f7818AeAD6 |
| [Kain Warwick](https://twitter.com/kaiynne)       | Kain.eth          | 0x5b97680e165b4dbf5c45f4ff4241e85f418c66c2 |
| [DegenSpartan](https://twitter.com/DegenSpartan)  | degenspartan.eth  | 0x4E60bE84870FE6AE350B563A121042396Abe1eaF |
| [Klim K](https://twitter.com/milkyklim)           | yfi.milkyklim.eth | 0x0cec743b8ce4ef8802cac0e5df18a180ed8402a7 |
| [Damir Bandalo](https://twitter.com/damirbandalo) | -                 | 0xa83838221278f22ee5bAe3E523f34D42b066D67D |

This 3/5 multisig has capabilities to pause new deposits and trades in case of technical emergencies. Users will always be able to withdraw their funds regardless of new deposits being paused. The multisig can also change the swap/withdrawal fees and the per pool/account deposit limits.

## **BUG BOUNTY PROGRAM**

Our goal is to provide you with the safest Saddle protocol. We encourage the community to help us find bugs or vulnerabilities in the protocol. The bounty reward is up to **US$ 50,000**. Help us find an issue and earn a reward for your service.

### **Report Via Email**

Report bugs and issues for Saddle protocol by sending an e-mail to [security@saddle.finance](mailto:security@saddle.finance). Please include the following details in your email:

- **Subject:** A subject field summarizing the bug/issue
- **Description**: Provide detailed information in the email body - detailed information about the issue, steps to reproduce the bug, any other details needed to help identify and resolve the problem, etc.
- **Attachments**: Supporting documents & attachments like screenshot, video, logs, etc\)
- **Your name and e-mail**
- **Your wallet address**: Please specify your network and wallet address

### **Report Via Other Channels**

Report your findings via any one of these channels.

| **REPORT HERE**                   | **LINK**                                                                               |
| :-------------------------------- | :------------------------------------------------------------------------------------- |
| **Discord \(\#support channel\)** | [**https://discord.gg/hX8RZFBW9R**](https://discord.gg/hX8RZFBW9R) \*\*\*\*            |
| **Telegram**                      | [**https://t.me/saddle_finance**](https://t.me/saddle_finance) \*\*\*\*                |
| **Immunify Bug Bounty**           | \*\*\*\*[**https://immunefi.com/bounty/saddle/**](https://immunefi.com/bounty/saddle/) |

### **Terms & Conditions**

The [Terms and Conditions](https://immunefi.com/bounty/saddle/) cover your participation in the Bug Bounty Program. By submitting any vulnerabilities to Saddle Finance or otherwise participating in the Program in any manner, you accept these Terms.
