---
description: SIP stands for Saddle Improvement Proposal.
---

# Governance (SIPs)

### Important links:

- [Saddle Improvement Proposals GitHub](https://github.com/saddle-finance/SIPS)
- [Saddle Improvement Proposals](https://sips.saddle.community) (overview)
- [Discourse](https://www.saddle.community) (saddle.community)
- [Snapshot](https://snapshot.org/#/saddlefinance.eth)

## Proposal Process

**SIP** stands for [Saddle Improvement Proposal](https://github.com/saddle-finance/SIPS/blob/master/SIPS/sip-0.md#what-is-an-sip). An SIP is a design document providing information to the Saddle community about a proposed change to the system. The author builds consensus within the community and documents dissenting opinions.

### GOVERNANCE STEPS

The chart below shows a high-level view of the Saddle governance process:

![](<.gitbook/assets/image (3).png>)

#### Stage 1: Gauge Interest

If you have an idea for improving the Saddle protocol, the first stage is to test the waters. Go to Saddle on [Discord](https://discord.gg/saddle) and look for the Governance > [#discussion](https://discord.com/channels/780508954916290610/909713556491108352) channel. Share your idea and listen to what the community has to say.

If the initial reactions are positive and encouraging, start formalizing your idea into a post for polling on Discourse.

#### Stage 2: Poll on Discourse

Go to [Discourse](https://www.saddle.community), look for the [Proposals](https://www.saddle.community/c/proposals/6) category, and post your proposal there (rec copying the formatting from a prev passing proposal, or using [this template](https://github.com/saddle-finance/SIPS/blob/master/sip-X.md)).

![](https://lh3.googleusercontent.com/ZjKjKwrLsW36QT2_bYZTbruEWpONi6vEU6kK-398u_2rD6kVsfsGb-GjIzbwc3KgWb0FP8sSKqZxGs_HbMaD19ofrZdmfVnck5pIU7hrvC7azEsyjx7l665iaMLl5kaQV7fm6h5F)

Here’s are a few handy tools to help draft your post:

- Tips on posting proposals on Discourse: [Link](https://www.saddle.community/t/about-the-proposals-category/15)
- Template for your post: [Link](https://github.com/saddle-finance/SIPS/blob/master/sip-X.md)
- Before you click the submit button, check if your post has:
  - **Sections:** Simple Summary, Abstract, Motivation, Specification
  - **Poll:** Include a 72h poll (using the most appropriate poll type, typically Y/N or multiple choice)

All set! Last step is to ping a Saddle Core Contributor in Discord to blast your shiny new proposal on all the socials to maximize engagement.

#### Stage 3: Vote on Snapshot

If the Discourse poll passes after 72 hours, the SIP editor will step in to formalize the SIP. The voting process comprises:

- Creating a vote on [Snapshot](https://snapshot.org/#/saddlefinance.eth) (by SIP editor)
- Creating a specific discussion channel on [Discord](https://discord.gg/saddle) (by Saddle core contributor or gov mod)
- Announcing the vote on all socials (by Saddle core contributor)
- 72-hour voting period _for SDL holders_

**Stage 4: Fork SIP**

Once the Snapshot voting is finished and passes successfully, the SIP editor will fork the SIPs repo and create a pull request (PR):

- The PR will have a copy of your proposal
- With the metadata filled out, notably _discussions-to_ which will link to the Discourse post
- The proposal will be named in the format: _sip-draft_title_abbrev.md_
- Read [SIP-0](https://github.com/saddle-finance/SIPS/blob/master/SIPS/sip-0.md) for additional information (e.g., workflow, attaching images/diagrams, SIP editor responsibilities).

#### Stage 5: Execution

Lastly, a Saddle core contributor or SIP editor will coordinate with the [community multisig](saddle-faq.md#who-controls-saddles-admin-keys) to execute the proposed change.

### GOVERNANCE ROLES

The stakeholders for the governance process can be both internal and external. Various governance roles exist to ensure the stakeholders engage in delivering the type of value desired or expected. The key roles and responsibilities of Saddle governance are:

#### SIP Editor

Broadly, the [SIP editor](https://github.com/saddle-finance/SIPS/blob/master/SIPS/sip-0.md#sip-editors)’s powers and responsibilities are:

- Checks the incoming proposals for quality
- Validate technical correctness
- Check language and grammar, and other editorial aspects
- Work with the SIP authors for revision, where required
- Create vote on Snapshot
- Formalize and document passed SIPs on GitHub

The editors don’t pass on judgement on SIPs, rather act as an administrative check-and-balance role.

**Who:** The current editors are @alphastorm, @penandlim, @hammeiam, and @ug02fast.

#### Saddle Core Contributors

Core contributor powers and responsibilities:

- Provide feedback on proposals
- Advise on how best to create a passing proposal
- Create channels and shepherd discussions in Discord and Discourse
- Post announcements of voting start on social channels (Discord, TG, Twitter)

**Who:** Anyone with a `Saddle Team` role in Discord

#### Governance Mod

Gov mod powers and responsibilities:

- Moderating messages in communities and deleting inappropriate messages
- Invite, ban, or suspend people who violate the community rules
- Create channels and shepherd discussions in Discord and Discourse
- Create vote on Snapshot

**Who:** No one as of now. Community members interested in contributing as a gov mod should ping `zim#2649` on Discord.
