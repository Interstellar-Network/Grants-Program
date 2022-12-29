# Interstellar - Wallet Phase 2

> This document will be part of the terms and conditions of your agreement and therefore needs to contain all the required information about the project. Don't remove any of the mandatory parts presented in bold letters or as headlines (except for the title)! Lines starting with a `>` (such as this one) should be removed. Please use markdown instead of HTML (e.g. `![](image.png)` instead of `<img>`). 
>
> See the [Grants Program Process](https://github.com/w3f/Grants-Program/#pencil-process) on how to submit a proposal.

- **Team Name:** Interstellar
- **Payment Address:**  Ethereum - 0xc5C54DcD7b76b3B26ab4a02f191338F31aD732f6 (ETH)
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 3


## Project Overview :page_facing_up:

**Follow-up of Interstellar- Wallet Phase 1**
add pull request
If this is an application for a follow-up grant (the continuation of an earlier, successful W3F grant), please provide name and/or pull request of said grant on the first line of this section.

### Overview


We think that there is an opportunity to turn any mobile devices/smartphones into a cold wallet where private keys needed to sign transactions are hardware protected: 
- within secure element and TEE on mobile
for the private key associated to mobiles to sign transaction request and transaction confirmations i.e. (a private key that is a proxy to actual crypto privates keys managed by the nodes)
-within TEE on nodes
For the private keys associated to asset owned
This hardware level security combined with a Trusted Transaction validation protocol based on TUI and/or garbled circuits and Visual Cryptography enables the overall solution to resist state of the art malware threats including banking trojan. (Attacks commonly used to compromise devices and bowsers to access CEX accounts, ex crypto,com,etc…)
Social Recovery combined with a future new recovery based on the hardware devices owned by the wallet owner when they connect  NFC/BT/WiFi to your mobile’s devices.

The achieved security level of this novel approach enables us to guarantee the security of one-click instant web3 onboarding for newcomers in crypto.
And represents a secure but simpler alternative to hardware wallets for crypto veterans.
We think that like with Google vs. Yahoo there is a technology arm race that can disrupt hardware wallet, smart contract wallet and even hot wallet market down the road!

“The blockchain ecosystem needs an easy to use interface with hardware wallet security to reach the mass market.”

The main pain points of non-custodial wallet solutions still are:

- **User experience**  [Can an easy to set-up wallet be an efficient customer acquisition tool for DeFi players?](https://medium.com/@jlleleu/can-be-an-easy-to-set-up-wallet-an-efficient-customer-acquisition-tool-for-defi-players-8600812fe01e)  
- **Security** [Are cryptocurrency wallets more at risk than ever?](https://medium.com/@jlleleu/are-cryptocurrency-wallets-more-at-risk-than-ever-cf1ce9725de7)

> We think that current wallet solutions slow down the DeFi adoption.

Interstellar is a novel non-custodial peace of mind mobile wallet with a hardware security level. Based on a Substrate blockchain and SubstraTEE/IntegriTEE workers.

**We can now provide the same hardware security level as hardware wallets with only a mobile and a blockchain**

![Grant-Scheme-White (1)](https://user-images.githubusercontent.com/4605611/145108720-becb76be-6c16-46c8-af69-7e953e5a166d.png#gh-dark-mode-only)

![Grant-Scheme-Black (3)](https://user-images.githubusercontent.com/4605611/145108818-6f8b6158-6c27-4f0d-a104-9d2469c73636.png#gh-light-mode-only)

**Thanks to Trusted User Interface TUI on mobile and Trusted Execution Environment on both mobile and blockchain nodes**

Because TUI is not yet avalaible on all mobile devices we use a Garbled Circuit/Visual Cryptography scheme which provides an alternative that will be complementary down the road to mitigate potential flaws in TUI.

![Iphone-Android-TUI-White (1)](https://user-images.githubusercontent.com/4605611/145201585-5d106219-e51e-44d3-8c1b-95fe99e71455.png#gh-dark-mode-only)

![Iphone-Android-TUI-Black (1)](https://user-images.githubusercontent.com/4605611/145201886-30bafb07-fc1c-4dc0-acf9-f0e9f163fa66.png#gh-light-mode-only)

#### Features

- **Hardware security Level** - TEE on nodes and mobiles (incl. TUI), garbled circuits and visual cryptography secure interface
- **Just download an app** - no registration, PIN, password, passphrase, private key or any secret to store or remember
- **Multichain Wallet** - securely store and interact with native cryptocurrency coins and tokens from multiple blockchains
- **Confirm a transaction with ONLY ONE SCREEN** - no SMS to wait for, no additional 2FA app to use, no QR code to scan

- **Up to 1,000,000 tps** - no tps limit due to slow consensus, thanks to IntegriTEE layer 2 based on hardware enclave technology
- **Social Recovery Service** - leverages the existing Substrate pallet and a novel decentralized autonomous recovery service

> We hope that we will be able to provide a response to the related RFP in the following phases

- **Features to securely send coins with social network messages (even to persons with no-wallet)** - explained in [Can an easy to set-up wallet be an efficient customer acquisition tool for DeFi players?](https://medium.com/@jlleleu/can-be-an-easy-to-set-up-wallet-an-efficient-customer-acquisition-tool-for-defi-players-8600812fe01e)

#### Our solution is designed to support blockchain and DeFi mass market adoption with

- **A decentralized key & asset management service** where the user’s privates keys and signature programs are stored and executed in TEE nodes
- **A decentralized Trusted Transaction Validation protocol** that leverages TEE and TUI features on mobile, combined with One Time Garbled Circuits and Visual Cryptography to provide a **Trusted Authentication and Trusted UI layer** on user devices

The **Interstellar - Wallet Phase 1** W3F Grant Proposal focuses on two of the core components of the Interstellar solution:

- A Substrate Off-Chain Worker OCW Garbled Circuit Factory GCF to manage an external garbled circuit generator service (designed to be used by Substrate developers regardless of the Interstellar solution)
- An implementation of the Trusted Transaction Validation protocol in Substrate pallets to demonstrate the usage of GCF within a Substrate framework and with a mobile  Garbled Circuit evaluator client

Following are other use cases of the Garbled Circuit Factory:

- Every schemes  based on Garbled Circuit generators and evaluators
- Multi Party Computation MPC protocol (when Oblivious Transfer OT will be managed in pallets)
- Proof of history of legitimate computation with reusable Garbled Circuit (Interstellar ongoing research: Detection of adverse code execution during short transaction sessions - work in progress)
- Post Quantum encryption and signature scheme implementations (NIST candidate examples)

### Project Details

We expect the teams to already have a solid idea about your project's expected final state. Therefore, we ask the teams to submit (where relevant) for each kind of project:

Software development projects:
- Mockups/designs of any UI components
- Data models / API specifications of the core functionality
- An overview of the technology stack to be used
- Documentation of core components, protocols, architecture, etc. to be deployed
- PoC/MVP or other relevant prior work or research on the topic
- What your project is _not_ or will _not_ provide or implement
  - This is a place for you to manage expectations and to clarify any limitations that might not be obvious

Research projects:
- The problem(s) that you want to investigate, and why these are important. 
- Research questions/hypothesis.
- The methodology that will be applied. 
- The data collection and analysis procedures.
- The expected results and how they would be double-checked by the grants team (reproducibility of the data analysis).
- Relevant related work.
- Intended venue for results publication and the timeline for publication. 
- What your project is _not_ or will _not_ provide or implement
  - This is a place for you to manage expectations and clarify any limitations that might not be obvious

Things that shouldn’t be part of the application (see also our [FAQ](../docs/faq.md)):
- The (future) tokenomics of your project 
- For non-infrastructure projects—deployment and hosting costs, maintenance or audits
- Business-oriented activities (marketing, business planning), events or outreach

#### Technology stack

- VHDL
- C/C++
- Java/Kotlin/Swift
- gRPC
- Rust/Substrate
- IPFS




### Ecosystem Fit
> Where and how does your project fit into the ecosystem?

This project is the first phase of a wallet project. Although, we think that our Trusted Transaction Validation protocol could bring a novel approach to address UX/UI security issues regardless of other features of our frictionless wallet.
We designed our validation transaction protocol to benefit to other wallets or Dapps. We think it could also be complementary down the road to mobile light clients like Substrate Connect (check **Future Plans** section).
  
![TTV overview overview drawio](https://user-images.githubusercontent.com/4605611/144742049-54d3a212-b471-4a69-9f44-adfb150814ca.png#gh-light-mode-only)

![TTV overview overview dark drawio](https://user-images.githubusercontent.com/4605611/144738926-e6f0db47-f7ff-4382-ae5d-251420e23a61.png#gh-dark-mode-only)

>Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?

We want to target Dapp providers in the DeFi ecosystem with developer tools to integrate our solution with their Dapps. We think that our value proposition should be attractive to them.
At the same time we want to target newcomers with a Robinhood wallet for Defi that includes an average dollar cost feature.
> What need(s) does your project meet?

The need for a wallet to be simpler to set-up and use, as well as the need for higher security to address the growing malware/banking trojan threats.

> Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?

Math Wallet and Gluon are close to our solution.

We think that we could bring a better user experience, security and performance, thanks to a highly scalable layer 2 based on SubstraTEE:

- Math Wallet is based on MPC that requires heavier computation resources. They also envision smartcards with a screen for their users. It's comparable to our level of security, but more expensive, cumbersome to use, less flexible and more complex to deploy than our solution.

- Gluon QR code based transaction confirmation that requires 2 screens is more cumbersome for the user. Moreover, this scheme is already exposed to banking trojans with overlay capabilities*. Although their TPM based approach could be complementary down the road to TEE, to mitigate potential future flaws on Intel SGX.

> *see: A high level attack  description on solutions that use QR code for transaction confirmations [Are cryptocurrency wallets more at risk than ever?](https://medium.com/@jlleleu/are-cryptocurrency-wallets-more-at-risk-than-ever-cf1ce9725de7)

## Team :busts_in_silhouette:







### Team members
- Name of team leader:
- Jean-Luc Leleu
- Names of team members:
- Nathan Prat
- Eliot Leleu
- Jean-Louis Hoenen
- Aude Bourdouxhe
- Philippe Salats (advisor)
- 
### Contact

- **Contact Name:** Jean-Luc Leleu
- **Contact Email:** jeanluc.leleu@protonmail.com
- **Website:** <https://www.interstellar.gg/>


### Legal Structure

- **Registered Address:** Paris, France
- **Registered Legal Entity:** Interstellar SAS

### Team's experience
We are now multiple security and fintech  entrepreneurs, security researchers, patents fillers who turned open-source developers and blockchain enthusiasts.
Please describe the team's relevant experience. If your project involves development work, we would appreciate it if you singled out a few interesting projects or contributions made by team members in the past. For research-related grants, references to past publications and projects in a related domain are helpful.

If anyone on your team has applied for a grant at the Web3 Foundation previously, please list the name of the project and legal entity here.

### Team Code Repos

- <https://github.com/Interstellar-Network>

- <https://github.com/nathanprat>

### Team LinkedIn Profiles (if available)

- <https://www.linkedin.com/in/jlleleu/> Jean-Luc Leleu

- <https://www.linkedin.com/in/nathan-prat/> Nathan Part

- <https://www.linkedin.com/in/eliotjfl/> Eliot Leleu

- <https://www.linkedin.com/in/jlhoenen/> Jean-Louis Hoenen

- <https://www.linkedin.com/in/aude-bourdouxhe-40656b28/> Aude Bourdouxhe

- <https://www.linkedin.com/in/philippesalats/> Philippe Salats (advisor)

## Development Roadmap :nut_and_bolt:

### Overview



## Development Status :open_book:

If you've already started implementing your project or it is part of a larger repository, please provide a link and a description of the code here. In any case, please provide some documentation on the research and other work you have conducted before applying. This could be:

- links to improvement proposals or [RFPs](https://github.com/w3f/Grants-Program/tree/master/rfp-proposal) (requests for proposal),
- academic publications relevant to the problem,
- links to your research diary, blog posts, articles, forum discussions or open GitHub issues,
- references to conversations you might have had related to this project with anyone from the Web3 Foundation,
- previous interface iterations, such as mock-ups and wireframes.

## Development Roadmap :nut_and_bolt:

This section should break the development roadmap down into milestones and deliverables. To assist you in defining it, we have created a document with examples for some grant categories [here](../docs/grant_guidelines_per_category.md). Since these will be part of the agreement, it helps to describe _the functionality we should expect in as much detail as possible_, plus how we can verify and test that functionality. Whenever milestones are delivered, we refer to this document to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions, it should be clear how your project is related to Substrate, Kusama or Polkadot. We _recommend_ that teams structure their roadmap as 1 milestone ≈ 1 month.

> :exclamation: If any of your deliverables is based on somebody else's work, make sure you work and publish _under the terms of the license_ of the respective project and that you **highlight this fact in your milestone documentation** and in the source code if applicable! **Teams that submit others' work without attributing it will be immediately terminated.**

### Overview

- **Total Estimated Duration:** Duration of the whole project (e.g. 2 months)
- **Full-Time Equivalent (FTE):**  Average number of full-time employees working on the project throughout its duration (see [Wikipedia](https://en.wikipedia.org/wiki/Full-time_equivalent), e.g. 2 FTE)
- **Total Costs:** Requested amount in USD for the whole project (e.g. 12,000 USD). Note that the acceptance criteria and additional benefits vary depending on the [level](../README.md#level_slider-levels) of funding requested. This and the costs for each milestone need to be provided in USD; if the grant is paid out in Bitcoin, the amount will be calculated according to the exchange rate at the time of payment.

### Milestone 1 Example — Basic functionality

- **Estimated duration:** 1 month
- **FTE:**  1,5
- **Costs:** 8,000 USD

> :exclamation: **The default deliverables 0a-0d below are mandatory for all milestones**, and deliverable 0e at least for the last one. If you do not intend to deliver one of these, please state a reason in its specification (e.g. Milestone X is research oriented and as such there is no code to test).

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.) |
| 1. | Substrate module: X | We will create a Substrate module that will... (Please list the functionality that will be implemented for the first milestone. You can refer to details provided in previous sections.) |
| 2. | Substrate module: Y | The Y Substrate module will... |
| 3. | Substrate module: Z | The Z Substrate module will... |
| 4. | Substrate chain | Modules X, Y & Z of our custom chain will interact in such a way... (Please describe the deliverable here as detailed as possible) |
| 5. | Library: ABC | We will deliver a JS library that will implement the functionality described under "ABC Library" |
| 6. | Smart contracts: ... | We will deliver a set of ink! smart contracts that will...


### Milestone 2 Example — Additional features

- **Estimated Duration:** 1 month
- **FTE:**  1,5
- **Costs:** 8,000 USD

...

## Future Plans

Please include here

-how you intend to use, enhance, promote and support your project in the short term, and
-the team's long-term plans and intentions in relation to it.

## Referral Program (optional) :moneybag: 

You can find more information about the program [here](../README.md#moneybag-referral-program).
- **Referrer:** Name of the Polkadot Ambassador or GitHub account of the Web3 Foundation grantee
- **Payment Address:** BTC, Ethereum (USDT/USDC/DAI) or Polkadot/Kusama (aUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))

## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Web3 Foundation Website / Medium / Twitter / Element / Announcement by another team / personal recommendation / etc.

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:

- Work you have already done.
- If there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.
