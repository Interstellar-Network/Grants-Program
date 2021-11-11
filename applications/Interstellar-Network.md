# W3F Grant Proposal

> This document will be part of the terms and conditions of your agreement and therefore needs to contain all the required information about the project. Don't remove any of the mandatory parts presented in bold letters or as headlines! Lines starting with a `>` (such as this one) can be removed.
>
> See the [Grants Program Process](https://github.com/w3f/Grants-Program/#pencil-process) on how to submit a proposal.

- **Project Name:** Interstellar Wallet Phase 1
- **Team Name:** Interstellar network/Dark Energy
- **Payment Address:** BTC, Ethereum (USDT/DAI) or Karura (kUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2 

> ⚠️ *The combination of your GitHub account submitting the application and the payment address above will be your unique identifier during the program. Please keep them safe.*

## Project Overview :page_facing_up:

If this application is in response to an RFP, please indicate this on the first line of this section.

If this is an application for a follow-up grant (the continuation of an earlier, successful W3F grant), please provide name and/or pull request of said grant on the first line of this section.

### Overview

- An indication of how your project relates to / integrates into Substrate / Polkadot / Kusama.
- An indication of why your team is interested in creating this project.

 Interstellar Wallet Phase 1: Substrate OCW Garbled Circuit Factory GCF and Trusted Transaction Validation protocol pallet demo (as a GCF use case) 
 
**Why Interstellar wallet?**

**User experience** and **Security** are still the main **pain points** of non-custodial wallet. We think that they slow down blockchain and DeFi adoption.

- **Wallets are not easy for newcomers and even for some experienced users:**

The Public Private key concept is complex for non-technical people and can be easily misused. The process of wallet creation can be a bit confusing and misleading, and the average user still do not understand clearly what information, passphrase, private key, etc. need to be protected and how to store it safely.

- **Only Hardware Wallets (like Ledger, Trezor, Ngrave, etc.) are secures:**

Because blockchains themselves and centralized exchanges are getting more secures, bad actors now focus their attacks on Individual wallets and exchange accounts. 

Banking trojan are now also targeting crypto wallet owners. Dapp and wallets are more and more exposed on mobiles and in browsers as those trojans are getting more sophisticated and pervasive.
**“Android banking malware, which rose by an incredible 158.7 per cent in Q1, saw a continued increase of 49 per cent”**- Source ESET quarterly threat report 2021. Zero day that enables bad actors, through “exploit chain”, to get the control on mobile operating system and browsers have never been higher.[2021 has broken the record for zero-day hacking attacks]( https://www-technologyreview-com.cdn.ampproject.org/c/s/www.technologyreview.com/2021/09/23/1036140/2021-record-zero-day-hacks-reasons/amp/)

Given the growth dynamic of the malware/banking trojan threat, the blockchain ecosystem need now a protection against malware on mobiles wallet and Dapps. 

We think that Hardware security,Trusted Execution Environement TEE and especialy Trusted User Interferface TUI can provide a level of hardware security comparable to hardware wallet. Mobile UI security is cruciable on this respect to address current and growing  threats (including banking trojan with their overlay capabilities). They can easily build fake UI that mislead user to trigger tampered transaction.
From a pure security stanpoint,some mobile banking application (DSP2 compliant) are now more robust than mobile wallet.

At the time of W3f,Parity,Polkadot is pushing its light client on the mobile and browsers to increase security.
We think that the blockchain ecosystem and especially polkdaot/kusama will benefit from the adding of a SECURE UI LAYER including TUI and TEE (layer 2) on mobiles light client like Substrate connect. 

Unfortunatly, TUI and full TEE features are not yet avalaible on all mobiles and the most advanced feature you find on servers will take time to be mainstream, as manufacturers are slow to integrate them. Moreover, ARM TrustZone still lack of a service like IAS for IntelSGX for the management of remote attestation.

**Our solution to address the previous issues**

There is a security gap to fill before TEE and TUI will be fully avalaible on a large majority of mobile.
We use One Time (not one time program) and Reusable Garbled circuits to ensure private computation and visual cryptography to help on the UI issues, an alternative that will be complementary down the road to mitigate potential future security flaws in TEE and TUI.

Interstellar is a novel type of non-custodial **frictionless** decentralized wallet with **hardware security level**, designed to support blockchain and DeFi **mass market adoption**.

**Features/Benefits**

- **Just download an app** with no set-up nor registration, no Private Keys nor passphrase to backup, no PIN, password, or any secret to remember*
- **Confirm a transaction with ONLY ONE SCREEN** No short text message (SMS) to wait for, no additional 2FA app (like Google Authenticator) to use, no QR code to scan.
Anyway, banking trojan can already compromise the previous 2FA schemes*
[Android banking Trojan to steal cryptocurrency and 2FA codes](https://www.revelock.com/en/blog/oscorp-android-banking-trojan-to-steal-cryptocurrencies-and-2fa-codes  )

- **Decentralized key & asset management service** where user’s privates key and signature program are stored and executed in Hardware Enclave/Trusted Execution Environment TEE*
The mobile client that control keys and triggers transactions is designed to resist malware attacks from banking trojan (and even targeted attacks at a later stage) 
- **Social Recovery Service** that leverages the existing substrate pallet, and a novel decentralized autonomous recovery service* (Comment: we hope that we will be able to provide a response to the related RFP in the following phases)
- **Features to securely send coins with social network messages (even to people with no-wallet)** Link to "Can be easy to set-up wallet an efficient customer acquisition tool for DeFi players" to add
- **Cross chain Swap feature** based on a Continious Liquitity Pool (CLP like ThorChain but with higher security and performance TEE/PMC/TTS + Trusted Transaction Validation protocol with mutisig option*  mobile + yubikey)

**The solution relies on a substrate blockchain and on substaTEE/IntegriTEE Workers** to secure private keys, signature programs and the friendly authentication and transaction validation service.

The last service use a novel **Decentralized Trusted Transaction Validation Protocol** that leverage **TEE features on mobile**, combined with **One Time Garbled Circuit and Visual Cryptography** to provide a **Trusted Authentication and Trusted UI layer** on user devices.

***Link to medium Interstellar Wallet – Technology and security lightpaper.(draft/work in progress)** 

The project phase 1 focus on two of the core components of the Interstaller solution: An OCW garbled circuit factory GCF and an implementation of the transaction validation protocol in a substrate pallet. It demonstrate the usage of GCF whithin a substrate framework and with a mobile client.

We designed this Garbled circuit Factory OCW to be used by substrate devellopers regardless of Interstellar solution.

Following are other use case of Garbled Circuit Factory:
- Efficient alternative to Public Key encryption. (based on AES or symetric encryption  Garbled Circuit that embed securely the symetric secret key, highly increase performance on recipent nodes)
- Post Quantum encryption and signature scheme implementation (NIST candiate example)
- Computation Privacy of verifiable delay function VDF and others cryptographic tools
- Proof of history of legitimate computation with reusable garbled circuit (Interstellar ongoing research:detection of adverse code execution during short transaction session) - end of Technology and security lightpaper.(draft/work in progress)
- TBD






### Project Details


Before to go into the details of Grabled Circuit Factory architecture, let's digg into the design of a basic garbled circuit structure.

A garbled circuit is a cryptographic obfuscation technique and a cryptographic algorithm that ensures computation privacy i.e. manages the protection of a Boolean circuit that can be executed without leaking information. Neither the semantics of Boolean operators (AND, OR, XOR, etc.) that makes up the circuit nor the semantics of inputs and outputs of the circuit will be revealed to the attackers through reverse-engineering or brute force attacks


![1_v4GuUlPEaVzo6gGZdJ4R6g (1) (Phone)](https://user-images.githubusercontent.com/4605611/141285502-7712225b-e2d8-4f1b-84bb-c0860eaefc64.jpeg)

- Inputs and Outputs are Garbled Values i.e. 128 bits token indistinguishable from random with a secret semantic value of 0 or 1 only known by the nodes
- Each Boolean operator is implemented in the circuit by an encrypted truth table, decrypted by its respective Garbled Values inputs

[Foundation of Garbled Circuits,   Viet Tung Hoang, B.S. (National University of Singapore) 2007 ](https://www.cs.fsu.edu/~tvhoang/thesis.pdf)








![GCF pipeline drawio](https://user-images.githubusercontent.com/4605611/141283607-f95a7170-9729-4af4-9221-d776f52223f3.png)







![Transaction Validation Module drawio](https://user-images.githubusercontent.com/4605611/140121290-adb8918c-9f79-4f64-92f4-bb5aa318932c.png)






We expect the teams to already have a solid idea about your project's expected final state. Therefore, we ask the teams to submit (where relevant):

- Mockups/designs of any UI components
- Data models / API specifications of the core functionality
- An overview of the technology stack to be used
- Documentation of core components, protocols, architecture, etc. to be deployed
- PoC/MVP or other relevant prior work or research on the topic
- What your project is _not_ or will _not_ provide or implement
  - This is a place for you to manage expectations and to clarify any limitations that might not be obvious

### Ecosystem Fit

Help us locate your project in the Polkadot/Substrate/Kusama landscape and what problems it tries to solve by answering each of these questions:

- Where and how does your project fit into the ecosystem?
- Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?
- What need(s) does your project meet?
- Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?
  - If so, how is your project different?
  - If not, are there similar projects in related ecosystems?

## Team :busts_in_silhouette:

### Team members

- Name of team leader
- Names of team members

### Contact

- **Contact Name:** Full name of the contact person in your team
- **Contact Email:** Contact email (e.g. john@duo.com)
- **Website:**

### Legal Structure

- **Registered Address:** Address of your registered legal entity, if available. Please keep it in a single line. (e.g. High Street 1, London LK1 234, UK)
- **Registered Legal Entity:** Name of your registered legal entity, if available. (e.g. Duo Ltd.)

### Team's experience

Please describe the team's relevant experience. If your project involves development work, we would appreciate it if you singled out a few interesting projects or contributions made by team members in the past. For research-related grants, references to past publications and projects in a related domain are helpful.

If anyone on your team has applied for a grant at the Web3 Foundation previously, please list the name of the project and legal entity here.

### Team Code Repos

- https://github.com/<your_organisation>
- https://github.com/<your_organisation>/<project_1>
- https://github.com/<your_organisation>/<project_2>

Please also provide the GitHub accounts of all team members. If they contain no activity, references to projects hosted elsewhere or live are also fine.

- https://github.com/<team_member_1>
- https://github.com/<team_member_2>

### Team LinkedIn Profiles (if available)

- https://www.linkedin.com/<person_1>
- https://www.linkedin.com/<person_2>

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

For each milestone,

- make sure to include a specification of your software. _Treat it as a contract_; the level of detail must be enough to later verify that the software meets the specification.
- include the amount of funding requested _per milestone_.
- include documentation (tutorials, API specifications, architecture diagrams, whatever is appropriate) in each milestone. This ensures that the code can be widely used by the community.
- provide a test suite, comprising unit and integration tests, along with a guide on how to set up and run them.
- commit to providing Dockerfiles for the delivery of your project.
- indicate milestone duration as well as number of full-time employees working on each milestone.
- **Deliverables 0a-0d are mandatory for all milestones**, and deliverable 0e at least for the last one. If you do not intend to deliver one of these, please state a reason in its specification (e.g. Milestone X is research oriented and as such there is no code to test).

> :zap: If any of your deliverables is based on somebody else's work, make sure you work and publish _under the terms of the license_ of the respective project and that you **highlight this fact in your milestone documentation** and in the source code if applicable! **Teams that submit others' work without attributing it will be immediately terminated.**

### Overview

- **Total Estimated Duration:** Duration of the whole project (e.g. 2 months)
- **Full-Time Equivalent (FTE):**  Average number of full-time employees working on the project throughout its duration (see [Wikipedia](https://en.wikipedia.org/wiki/Full-time_equivalent), e.g. 2 FTE)
- **Total Costs:** Requested amount in USD for the whole project (e.g. 12,000 USD). Note that the acceptance criteria and additional benefits vary depending on the [level](../README.md#level_slider-levels) of funding requested. This and the costs for each milestone need to be provided in USD; if the grant is paid out in Bitcoin, the amount will be calculated according to the exchange rate at the time of payment.

### Milestone 1 Example — Implement Substrate Modules

- **Estimated duration:** 1 month
- **FTE:**  2
- **Costs:** 8,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)
| 1. | Substrate module: X | We will create a Substrate module that will... (Please list the functionality that will be implemented for the first milestone) |  
| 2. | Substrate module: Y | We will create a Substrate module that will... |  
| 3. | Substrate module: Z | We will create a Substrate module that will... |  
| 4. | Substrate chain | Modules X, Y & Z of our custom chain will interact in such a way... (Please describe the deliverable here as detailed as possible) |  


### Milestone 2 Example — Additional features

- **Estimated Duration:** 1 month
- **FTE:**  1
- **Costs:** 4,000 USD

...


## Future Plans

Please include here

- how you intend to use, enhance, promote and support your project in the short term, and
- the team's long-term plans and intentions in relation to it.


## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Web3 Foundation Website / Medium / Twitter / Element / Announcement by another team / personal recommendation / etc.

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:


- Work you have already done.
- Wheter there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.
