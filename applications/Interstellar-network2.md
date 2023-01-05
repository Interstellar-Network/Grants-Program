# Interstellar - Wallet Phase 2


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
- within Secure Element and TEE on mobile

For the private key associated to mobiles to sign transaction request and transaction confirmations i.e. (a private key that is a proxy to actual crypto privates keys managed by the nodes)
- within Trusted Transaction Environement TEE on nodes

For the private keys associated to asset owned
This hardware level security combined with a Trusted Transaction validation protocol based on TUI and/or garbled circuits and Visual Cryptography enables the overall solution to resist state of the art malware threats including banking trojan. (Attacks commonly used to compromise devices and bowsers to access CEX accounts, ex crypto,com,etc…)

Social Recovery combined with a future new recovery based on the hardware devices owned by the wallet owner when they connect  NFC/BT/WiFi to your mobile’s devices.

The achieved security level of this novel approach enables the solution to guarantee the security of **one-click instant web3 onboarding (add a link)** for newcomers in crypto.

It also represents **an easy to use alternative to hardware wallets** for crypto veterans.


> We think that like with Google vs. Yahoo there is a technology arm race that can disrupt hardware wallet, smart contract wallet and even hot wallet market down the road!


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


### Overview

- **Total Estimated Duration:** 9 months
- **Full-Time Equivalent (FTE):**  2.5
- **Total Costs:** 130,000 USD

### Milestone 1  — iOS client TTVP demo

- **Estimated duration:** 1 month
- **FTE:**  2.2
- **Costs:** 15,000 USD


| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License |  MIT  |
| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. ||||
| 1. | iOS client: TTVP demo | We will create a basic iOS app to demonstrate the TTVP protocol including the registration of an iPhone on the mobile registry pallet. ( for this milestone we won't yet demomstrate a cryptocurrency transaction neither the whole wallet UI/UX) |
| 2. | Substrate module: Mobile Registry update | we will update the mobile registry pallet to handle iPhone registration i.e mobile public key required  to validate TTVP - Transaction Confirmation result on the TTVP pallet |
| 3. | TTVP benchmark | We will develop a tool to benchmark TTVP execution on both mobile and pallets for future optimization of the Circuits/Garbled Circuits used by the TTVP protocol |
|

### Milestone 2 — Circuits and Garbled Circuits optimization/Benchmarks

- **Estimated Duration:** 1.5/2 months
- **FTE:**  2.2
- **Costs:** 25,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License |  MIT  |
| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. ||||
| 1. | Circuit Design optimization | We will modify the current design of the circuits used in the TTVP protocol to make it more user friendly for the user|
| 2. | Garbled Circuits optimization | we will modify both the Garbled Circuits evaluator on the mobile iOS and android and the GC generator on the GCF |
| 3.a | TTVP benchmark on iOS|benchmark results |
| 3.b | TTVP benchmark on Android | benchmark results |
| 3.c | TTVP benchmark on substrate pallets | benchmark results|

### Milestone 3 - Polkadot and Ethereum pallet signers

- **Estimated Duration:** 1.5 months
- **FTE:**  2.2
- **Costs:** 20,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License |  MIT  |
| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. ||||
| 1. | Subtrate Module - Signer Manager | We will create a pallet to manage OCW signers|
| 2. | Substrate Module - Poladot signer | we will create an OCW pallet to sign Polkadot transaction |
| 3. | Substrate Module - Ethereum signer | we will create a pallet to sign Ethereum transaction |
| 4. | Substrate Module - submit transaction | we will create an OCW pallet to send transactions to the appropriate network |


### Milestone 4 - Android pre-MVP wallet Polkadot/Ethereum

- **Estimated Duration:** 1.5 months
- **FTE:**  2.2
- **Costs:** 20,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License |  MIT  |
| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. ||||
| 1. | Android Wallet App | We will update the current android app to handle Polkadot and Ethereum transaction|
| 3. | Substrate chain | Modules TTVP, Mobile Registry and signers, will handle complete polkadot and ethereum transactions  |


### Milestone 5 - iOS pre-MVP wallet Polkadot/Ethereum

- **Estimated Duration:** 1.5 months
- **FTE:**  2.2
- **Costs:** 20,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License |  MIT  |
| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. ||||
| 1. | iOS Wallet App | We will update the iOS app (port Jetpack compose to Swift UI) to handle Polkadot and Ethereum transaction |




### Milestone 6 - MVP iOS/Android with NFC recovery
- **Estimated duration:** 2 months
- **FTE:**  2.2
- **Costs:** 30,000 USD


| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License |  MIT  |
| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| **0e.** | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.) |
| 1. | Substrate Module - NFC recovery | We will create a pallet to handle NFC recovery i.e a dedicated hardware or a payment card owned by the user to trigger its account recovery with a new mobile|
| 2.a | Android Wallet | we will update android app to handle NFC recovery|
| 2.b | iOS Wallet | we will update iOS app to handle NFC recovery|
| 3. | Substrate chain | with the support of Substrate builder program we aim at launching an MVP chain with TEE hardware to demomstrate instant onborading and easy airdrop  |
||||




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
