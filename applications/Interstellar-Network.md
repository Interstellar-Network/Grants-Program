# W3F Grant Proposal

> This document will be part of the terms and conditions of your agreement and therefore needs to contain all the required information about the project. Don't remove any of the mandatory parts presented in bold letters or as headlines! Lines starting with a `>` (such as this one) can be removed.
>
> See the [Grants Program Process](https://github.com/w3f/Grants-Program/#pencil-process) on how to submit a proposal.

- **Project Name:** Interstellar | Wallet Phase 1
- **Team Name:** Interstellar
- **Payment Address:** BTC, Ethereum (USDT/DAI) or Karura (kUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2 

> ⚠️ *The combination of your GitHub account submitting the application and the payment address above will be your unique identifier during the program. Please keep them safe.*

## Project Overview :page_facing_up:



### Overview

![Copy of Interstellar-Black-Text](https://user-images.githubusercontent.com/4605611/141333053-3f607ffe-1714-4512-b628-33274d0d0464.png)


 **Interstellar | Wallet Phase 1**: Substrate OCW Garbled Circuit Factory GCF and a Trusted Transaction Validation protocol pallet demo (as a GCF use case) 
 
#### Why Interstellar wallet?

**User experience** and **Security** are still the main **pain points** of non-custodial wallet. We think that they slow down blockchain and DeFi adoption.

Interstellar is a novel type of non-custodial **frictionless** decentralized wallet with **hardware security level**, designed to support blockchain and DeFi **mass market adoption**. Based on a **substrate blockchain** and on **substraTEE/IntegriTEE Workers** to secure

#### Our solution is designed to support Blockchain and SeFi mass market adoption with:

- **A Decentralized key & asset management service** where user’s privates key and signature program are stored and executed in TEE
- **A Decentralized Trusted Transaction Validation Protocol** that leverage **TEE features on mobile**, combined with **One Time Garbled Circuit and Visual Cryptography** to provide a **Trusted Authentication and Trusted UI layer** on user devices.

#### Features/Benefits
- **Hardware security Level** - TEE on nodes and mobiles with garbled circuits and visual cryptography secure interface
- **Just download an app** - no set-up nor registration, no Private Keys nor passphrase to backup, no PIN, password, or any secret to remember*
- **Multichain Wallet** - securely store and interact with native cryptocurrency coins and tokens from multiple blockchains
- **Confirm a transaction with ONLY ONE SCREEN** No short text message (SMS) to wait for, no additional 2FA app (like Google Authenticator) to use, no QR code to scan.
Anyway, banking trojan can already compromise the previous 2FA schemes*
[Android banking Trojan to steal cryptocurrency and 2FA codes](https://www.revelock.com/en/blog/oscorp-android-banking-trojan-to-steal-cryptocurrencies-and-2fa-codes  )


 **You just need to input on the keypad the one-time code you see (here 256)**

**That's all to securely confirm a transaction** ![Wallet-superposition-White-Shadow4medium smaller](https://user-images.githubusercontent.com/4605611/141301152-951143c3-d820-4bc1-8120-5a60a6878d52.png)
> And the best part, this scheme is designed to resist malware attacks from state of the art banking trojans (and even targeted attacks at a later stage)
- **Up to 1,000,000 tps** - thanks to IntegriTEE and hardware enclave technology
- **Social Recovery Service** that leverages the existing substrate pallet, and a novel decentralized autonomous recovery service* (Comment: we hope that we will be able to provide a response to the related RFP in the following phases)
- **Features to securely send coins with social network messages (even to people with no-wallet)** Link to "Can be easy to set-up wallet an efficient customer acquisition tool for DeFi players" to add
- **Cross chain Swap feature** based on a Continious Liquitity Pool (CLP like ThorChain but with higher security and performance TEE/MPC/TTS + Trusted Transaction Validation protocol with mutisig option*  mobiles + yubikey for Validators and power users)




***Link to medium Interstellar Wallet – Technology and security lightpaper.(draft/work in progress)**

#### Interstellar project Phase 1:

The project phase 1 focus on two of the core components of the Interstaller solution: 
- An OCW garbled circuit factory GCF to manage an external Garbled Circuit Generator service (We designed this Garbled circuit Factory to be used by substrate devellopers regardless of Interstellar solution)
- An implementation of the Transaction Validation protocol in substrate pallets to demo the usage of GCF whithin a substrate framework and with a mobile  Garbled Circuit evaluator client. 

Following are other use cases of Garbled Circuit Factory:

- Every schemes  based on Garbled Circuit generator and evaluator
- Multi Party Computation MPC protocol (when oblivious transfer OT will be managed in pallets)
- Proof of history of legitimate computation with reusable garbled circuit (Interstellar ongoing research: Detection of adverse code execution during short transaction session) - end of Technology and security lightpaper.(draft/work in progress)
- Post Quantum encryption and signature scheme implementation (NIST candiate examples)


### Project Details


#### Detailed [documentation](https://docs.google.com/document/d/1RTPx4EeA0Ek33f-8_Dj7p-qjzBp6VqLrrXNhIrwvFWI/edit?usp=sharing) on the project

- **OCW Garbled Circuit Factory**
- **Transaction Validation protocol pallets (including mobile registry)**
- **Transaction Validation Screen Technology (Trusted/Secure UI)**
- **Mobile client GC evaluator** 




#### Garbled Circuit Factory **previous vork**
The team has already develloped a strong authentication solution with circuits based on JustGarble implememtation https://cseweb.ucsd.edu/groups/justgarble/ that we customized with Free XOR and Half Gates and other specific improvement for our needs ( pre-computation of our Visual cryptographic Circuits).
We achieved a production ready platform with significant performance on the logic circuit production and the whole pipeline with memory mangement avoiding serilization/desirializtaion of the different circuit format: HDL, non-garbled and garbled.

------------

```shell
1 pratn@DESKTOP-U6PJB3U:~/workspace/j2l/lib_server/build$ ./circuit_display_gen_bench -nb_circuits_to_generate=5000
2 display_size : 360,154,50,590
3 time in s : 28.1261 s
4 circuits_per_hour : 639975
```


![1844c95c-1b74-4987-8466-4ba14da41ff3 (Custom)](https://user-images.githubusercontent.com/4605611/141327055-ea10f548-d6d2-4b1a-af2e-a059f2f67673.png)



```
5,65 ms per circuits on a Processor 11th Gen Intel(R) Core(TM) i7-11800H @ 2.30GHz, 2304 Mhz, 8 Core(s), 16 Logical Processor(s)
```


--------------------------









### Ecosystem Fit

Help us locate your project in the Polkadot/Substrate/Kusama landscape and what problems it tries to solve by answering each of these questions:

> Where and how does your project fit into the ecosystem?

This project is the first phase of a wallet project. Although, we think that our Transaction Validation protocol could bring a novel approach to address UX/UI security issues regardless of other features of our frictionless wallet.
We designed our Transaction Validation protocol to benfit to other wallet or Dapp. We think it could also be complemetary down the road to mobile light client like substrate connect (check future plan section).

![TTV overview overview drawio](https://user-images.githubusercontent.com/4605611/143036398-f4111713-652e-4478-8c77-afc9926149c1.png)

>Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?

We want to target in priority Dapp providers in the DeFi ecosystem with develloper tools to integrate our solution with their Dapps. We think that our value proposition should be attractive to them.  (link growth tool)
At the same time we want to target newcomers with a Robinhood for DeFi wallet app that include average dollar cost feature.

> What need(s) does your project meet?

The need for a wallet to be simpler to set-up and use, as well as the need for higher security to address the growing malware/banking trojan threats. (link attacks list in light paper)

> Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?

Math Wallet and Gluon are close to our solution

We think that we could bring a better user experience, security and performance (thanks to a highly scalable/higher txs layer 2 based on substraTEE): 

- Math Wallet is based on MPC that require heavier computation ressources. They also envision smartcard with screen, we think that despite a comparable level of security, It should be more expensive, cumbersome to use and less flexible and more complex to deploy than our solution.
 
- Gluon QR code based transaction confirmation that requires 2 screen should also be more cumbersome. Moreover, this scheme is already exposed to banking trojan with overlay capabilities ( see potential attack on QR code in our lightpaper). Although their TPM based approach could be complementary down the road to TEE, to mitigate potential future flaws on Intel SGX.


## Team :busts_in_silhouette:

### Team members

- Name of team leader:
Jean-Luc Leleu
- Names of team members:
- Nathan Prat
- Eliot Leleu
- Jean-Louis Honenen
- Markus Jakobssson https://www.markus-jakobsson.com/
- Aude Bourdouxhe

### Contact

- **Contact Name:** Full name of the contact person in your team
- **Contact Email:** 
- **Website:** https://www.interstellar.gg/

### Legal Structure

- **Registered Address:** Address of your registered legal entity, if available. Please keep it in a single line. (e.g. High Street 1, London LK1 234, UK)
- **Registered Legal Entity:** Name of your registered legal entity, if available. (e.g. Duo Ltd.)

### Team's experience

We are a cybersecurity team, specialized in end-user devices & smartphone security,  now working on blockchain after some experiences with the banking industry. We have won cybersecurity innovation award from Société Générale and Wavestone (security consulting and audit firm in the financial industry). We have also been selected by 500 startup Accelerator, batch 20 in San Francisco and have our patent portfolio financed by France Brevet, a government agency.

- 2018 Thales strategic partner(selected in Thales first batch 
accelerator in Station F)
- Partnership with Gemalto to issue smartcard hardware wallet 
solution for blockchain.
- 2017 500 Startups batch 20 (San Francisco California)
- Banking Cyber Security Innovation Awards winner
- 2016 Patent portfolio (10+ patents) financed by France Brevet

We then stop the activity of our former company to address legacy financial institutions and let go our patent ownership to focus on blockchain project.
We are now security and Fintech multiple entrepreneurs, security Researchers, patents fillers who turn open-source developers and blockchain enthusiasts.

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

- https://www.linkedin.com/in/nathan-prat/ Nathan Part
 
- https://www.linkedin.com/in/eliotjfl/ Eliot Leleu 
 
- https://www.linkedin.com/in/jlhoenen/ Jean-Louis Hoenen>
 
- https://www.linkedin.com/in/markusjakobsson/ Markus Jakobssson>
 
- https://www.linkedin.com/in/aude-bourdouxhe-40656b28/ Aude Bourdouxhe

- https://www.linkedin.com/in/jlleleu/ Jean-Luc Leleu



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

### Milestone 1 — Implement GCF Substrate Modules

- **Estimated duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can create and set-up a VHDL Master File, lauch Garbled Circuit generation and get the resulted Garbled circuit cid on IPFS.   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | GCF substrate Interface | GCF external service interface to interact with the following substrate modules and IPFS |  
| 2. | Substrate module: GCF CFG | We will create a Substrate GCF configuration pallet that will store GCF encrypted configuration information on chain (including cid of Master Circuit file, master key and other security parameter to ensure security of circuit production  |  
| 3. | Substrate GCF CFG CLI| a CLI to set-up  GCF configuration palllet | 
| 4. | Substrate module: OCW GCF | We will create an OCW pallet that will control and interact with GCF external service - Launch GC production and get resulted GC cid on IPFS |  
 



### Milestone 2 — GC management in substrate modules and Transaction Validation Protocol use case (first part)

- **Estimated Duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | Substrate module OCW GCP  | we will create a OCW GC Provider to interact with a GC evaluator/IPFS client  |  
| 2. | Substrate module: Authenticator| We will create a Substrate Authenticator  pallet that will implement the Transaction Validation protocol to manage GC evaluator and IPFS client|  
| 3. | Substrate GCP CLI| a CLI to request GC cid for evaluation | 
  
### Milestone 3 — Transaction Validation Protocol with  mobile use case (second part)

- **Estimated Duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example with mobile evaluators   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | Mobile Client (android 1.a/iOS 1.b) | We will create android and iOS mobile client with GC evaluator and IPFS light client to manage Transaction Confirmation |  
| 2. | Substrate module Mobile Registry | We will create a substrate Mobile Registry pallet to deal with mobile client (android/iOS) and Mobile Public Key and signature verification |  
| 3. | Substrate module: Authenticator with mobile | We will add mobile features to Substrate Authenticator/Transaction Validation Mngt  pallet|  

### Milestone 4 — Integration with substraTEE/IntegriTEE

- **Estimated Duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example in TEE environement with substraTEE  |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | substrate modules Authenicator port in TEE | We will migrate Authenticator in substraTEE/IntergriTEE workers |  
| 2. | Substrate module Mobile Registry port in TEE | We will migrate part of the mobile registry pallet in substraTEE/IntergriTEE workers |  
  


### Milestone 5 — GCF in TEE

- **Estimated Duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage GCF in IntelSGX/Asylo  |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | GCF external service in TEE | We will migrate GCF service in TEE/Intel SGX with Asylo framework | 
 
  




...


## Future Plans

Please include here

>how you intend to use, enhance, promote and support your project in the short term:

- We aim at develloping a user comunity and get in talks with Dapp and especially DeFi players with a taylored value proposition for them.
- Improvement of our Visual Cryptography scheme by reintroducing pure visual cryptography frame (to display character and figures) to increase the complexity and ressources required for an attack.
- potential research grant on our real-time Malware detection scheme
- add OT oblivious transfer in our pallet to enable usage of MPC with our GCF.
- add behavioral biometric feature

>the team's long-term plans and intentions in relation to it.

- Bounty to crack our transaction validation protocol when both Android protected confirmation and detection of adverse code execution will be deployed
- Include a TEE layer 2 to manage Root of trust based on full HSM hardware ( based on YubiHSM) to provide a 3 tier distributed HSM capability.

![3T Distributed HSM overview drawio (Custom)](https://user-images.githubusercontent.com/4605611/143676701-869ebba4-51ff-49f5-9e3b-97797984d844.png)

- Investigate potential integration with substrate connect to increase the security of the solution with additional off-chain features.
- Reseach on other human brain decryption capabilities (like Visual Cryptography, audio cryptography, etc..): the long term Goal is to increase our capabilities to descriminate real human from bot with IA capabilities. # W3F Grant Proposal

> This document will be part of the terms and conditions of your agreement and therefore needs to contain all the required information about the project. Don't remove any of the mandatory parts presented in bold letters or as headlines! Lines starting with a `>` (such as this one) can be removed.
>
> See the [Grants Program Process](https://github.com/w3f/Grants-Program/#pencil-process) on how to submit a proposal.

- **Project Name:** Interstellar | Wallet Phase 1
- **Team Name:** Interstellar
- **Payment Address:** BTC, Ethereum (USDT/DAI) or Karura (kUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2 

> ⚠️ *The combination of your GitHub account submitting the application and the payment address above will be your unique identifier during the program. Please keep them safe.*

## Project Overview :page_facing_up:



### Overview

![Copy of Interstellar-Black-Text](https://user-images.githubusercontent.com/4605611/141333053-3f607ffe-1714-4512-b628-33274d0d0464.png)


 **Interstellar | Wallet Phase 1**: Substrate OCW Garbled Circuit Factory GCF and a Trusted Transaction Validation protocol pallet demo (as a GCF use case) 
 
#### Why Interstellar wallet?

**User experience** and **Security** are still the main **pain points** of non-custodial wallet. We think that they slow down blockchain and DeFi adoption.

- **Wallets are not easy for newcomers and even for some experienced users:** The Public Private key concept is complex for non-technical people and can be easily misused. The process of wallet creation can be a bit confusing and misleading, and the average user still do not understand clearly what information, passphrase, private key, etc. need to be protected and how to store it safely.

- **Only Hardware Wallets (like Ledger, Trezor, Ngrave, etc.) are secures:** Because blockchains themselves and centralized exchanges are getting more secures, bad actors now focus their attacks on Individual wallets and exchange accounts. 
Banking trojans are now also targeting cryptocurrencies's owners. Dapp and wallets are more and more exposed on mobiles and in browsers as those trojans are getting more sophisticated and pervasive.
**“Android banking malware, which rose by an incredible 158.7 per cent in Q1, saw a continued increase of 49 per cent”**- Source ESET quarterly threat report 2021. Zero day that enables bad actors, through “exploit chain”, to get the control on mobile operating system and browsers have never been higher.[2021 has broken the record for zero-day hacking attacks]( https://www-technologyreview-com.cdn.ampproject.org/c/s/www.technologyreview.com/2021/09/23/1036140/2021-record-zero-day-hacks-reasons/amp/). Given the growth dynamic of the malware/banking trojan threat, the blockchain ecosystem need now a protection against malware on mobiles wallet and Dapps.


#### Our solution to address the previous issues
Interstellar is a novel type of non-custodial **frictionless** decentralized wallet with **hardware security level**, designed to support blockchain and DeFi **mass market adoption**. Based on a **substrate blockchain** and on **substraTEE/IntegriTEE Workers** to secure:
- **A Decentralized key & asset management service** where user’s privates key and signature program are stored and executed in TEE
- **A Decentralized Trusted Transaction Validation Protocol** that leverage **TEE features on mobile**, combined with **One Time Garbled Circuit and Visual Cryptography** to provide a **Trusted Authentication and Trusted UI layer** on user devices.

#### Features/Benefits

- **Just download an app** with no set-up nor registration, no Private Keys nor passphrase to backup, no PIN, password, or any secret to remember*
- **Confirm a transaction with ONLY ONE SCREEN** No short text message (SMS) to wait for, no additional 2FA app (like Google Authenticator) to use, no QR code to scan.
Anyway, banking trojan can already compromise the previous 2FA schemes*
[Android banking Trojan to steal cryptocurrency and 2FA codes](https://www.revelock.com/en/blog/oscorp-android-banking-trojan-to-steal-cryptocurrencies-and-2fa-codes  )


 **You just need to input on the keypad the one-time code you see (here 256)**

**That's all to securely confirm a transaction** ![Wallet-superposition-White-Shadow4medium smaller](https://user-images.githubusercontent.com/4605611/141301152-951143c3-d820-4bc1-8120-5a60a6878d52.png)
> And the best part, this scheme is designed to resist malware attacks from state of the art banking trojans (and even targeted attacks at a later stage)
- **Social Recovery Service** that leverages the existing substrate pallet, and a novel decentralized autonomous recovery service* (Comment: we hope that we will be able to provide a response to the related RFP in the following phases)
- **Features to securely send coins with social network messages (even to people with no-wallet)** Link to "Can be easy to set-up wallet an efficient customer acquisition tool for DeFi players" to add
- **Cross chain Swap feature** based on a Continious Liquitity Pool (CLP like ThorChain but with higher security and performance TEE/MPC/TTS + Trusted Transaction Validation protocol with mutisig option*  mobiles + yubikey for Validators and power users)




***Link to medium Interstellar Wallet – Technology and security lightpaper.(draft/work in progress)**

#### Interstellar project Phase 1:

The project phase 1 focus on two of the core components of the Interstaller solution: 
- An OCW garbled circuit factory GCF to manage an external Garbled Circuit Generator service (We designed this Garbled circuit Factory to be used by substrate devellopers regardless of Interstellar solution)
- An implementation of the Transaction Validation protocol in substrate pallets to demo the usage of GCF whithin a substrate framework and with a mobile  Garbled Circuit evaluator client. 

Following are other use cases of Garbled Circuit Factory:

- Every schemes  based on Garbled Circuit generator and evaluator
- Multi Party Computation MPC protocol (when oblivious transfer OT will be managed in pallets)
- Proof of history of legitimate computation with reusable garbled circuit (Interstellar ongoing research: Detection of adverse code execution during short transaction session) - end of Technology and security lightpaper.(draft/work in progress)
- Post Quantum encryption and signature scheme implementation (NIST candiate examples)


### Project Details


#### Detailed [documentation](https://docs.google.com/document/d/1RTPx4EeA0Ek33f-8_Dj7p-qjzBp6VqLrrXNhIrwvFWI/edit?usp=sharing) on the project

- **OCW Garbled Circuit Factory**
- **Transaction Validation protocol pallets (including mobile registry)**
- **Transaction Validation Screen Technology (Trusted/Secure UI)**
- **Mobile client GC evaluator** 




#### Garbled Circuit Factory **previous vork**
The team has already develloped a strong authentication solution with circuits based on JustGarble implememtation https://cseweb.ucsd.edu/groups/justgarble/ that we customized with Free XOR and Half Gates and other specific improvement for our needs ( pre-computation of our Visual cryptographic Circuits).
We achieved a production ready platform with significant performance on the logic circuit production and the whole pipeline with memory mangement avoiding serilization/desirializtaion of the different circuit format: HDL, non-garbled and garbled.

------------

```shell
1 pratn@DESKTOP-U6PJB3U:~/workspace/j2l/lib_server/build$ ./circuit_display_gen_bench -nb_circuits_to_generate=5000
2 display_size : 360,154,50,590
3 time in s : 28.1261 s
4 circuits_per_hour : 639975
```


![1844c95c-1b74-4987-8466-4ba14da41ff3 (Custom)](https://user-images.githubusercontent.com/4605611/141327055-ea10f548-d6d2-4b1a-af2e-a059f2f67673.png)



```
5,65 ms per circuits on a Processor 11th Gen Intel(R) Core(TM) i7-11800H @ 2.30GHz, 2304 Mhz, 8 Core(s), 16 Logical Processor(s)
```


--------------------------









### Ecosystem Fit

Help us locate your project in the Polkadot/Substrate/Kusama landscape and what problems it tries to solve by answering each of these questions:

> Where and how does your project fit into the ecosystem?

This project is the first phase of a wallet project. Although, we think that our Transaction Validation protocol could bring a novel approach to address UX/UI security issues regardless of other features of our frictionless wallet.
We designed our Transaction Validation protocol to benfit to other wallet or Dapp. We think it could also be complemetary down the road to mobile light client like substrate connect (check future plan section).

![TTV overview overview drawio](https://user-images.githubusercontent.com/4605611/143036398-f4111713-652e-4478-8c77-afc9926149c1.png)

>Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?

We want to target in priority Dapp providers in the DeFi ecosystem with develloper tools to integrate our solution with their Dapps. We think that our value proposition should be attractive to them.  (link growth tool)
At the same time we want to target newcomers with a Robinhood for DeFi wallet app that include average dollar cost feature.

> What need(s) does your project meet?

The need for a wallet to be simpler to set-up and use, as well as the need for higher security to address the growing malware/banking trojan threats. (link attacks list in light paper)

> Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?

Math Wallet and Gluon are close to our solution

We think that we could bring a better user experience, security and performance (thanks to a highly scalable/higher txs layer 2 based on substraTEE): 

- Math Wallet is based on MPC that require heavier computation ressources. They also envision smartcard with screen, we think that despite a comparable level of security, It should be more expensive, cumbersome to use and less flexible and more complex to deploy than our solution.
 
- Gluon QR code based transaction confirmation that requires 2 screen should also be more cumbersome. Moreover, this scheme is already exposed to banking trojan with overlay capabilities ( see potential attack on QR code in our lightpaper). Although their TPM based approach could be complementary down the road to TEE, to mitigate potential future flaws on Intel SGX.


## Team :busts_in_silhouette:

### Team members

- Name of team leader:
Jean-Luc Leleu
- Names of team members:
- Nathan Prat
- Eliot Leleu
- Jean-Louis Honenen
- Markus Jakobssson https://www.markus-jakobsson.com/
- Aude Bourdouxhe

### Contact

- **Contact Name:** Full name of the contact person in your team
- **Contact Email:** 
- **Website:** https://www.interstellar.gg/

### Legal Structure

- **Registered Address:** Address of your registered legal entity, if available. Please keep it in a single line. (e.g. High Street 1, London LK1 234, UK)
- **Registered Legal Entity:** Name of your registered legal entity, if available. (e.g. Duo Ltd.)

### Team's experience

We are a cybersecurity team, specialized in end-user devices & smartphone security,  now working on blockchain after some experiences with the banking industry. We have won cybersecurity innovation award from Société Générale and Wavestone (security consulting and audit firm in the financial industry). We have also been selected by 500 startup Accelerator, batch 20 in San Francisco and have our patent portfolio financed by France Brevet, a government agency.

- 2018 Thales strategic partner(selected in Thales first batch 
accelerator in Station F)
- Partnership with Gemalto to issue smartcard hardware wallet 
solution for blockchain.
- 2017 500 Startups batch 20 (San Francisco California)
- Banking Cyber Security Innovation Awards winner
- 2016 Patent portfolio (10+ patents) financed by France Brevet

We then stop the activity of our former company to address legacy financial institutions and let go our patent ownership to focus on blockchain project.
We are now security and Fintech multiple entrepreneurs, security Researchers, patents fillers who turn open-source developers and blockchain enthusiasts.

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

- https://www.linkedin.com/in/nathan-prat/ Nathan Part
 
- https://www.linkedin.com/in/eliotjfl/ Eliot Leleu 
 
- https://www.linkedin.com/in/jlhoenen/ Jean-Louis Hoenen>
 
- https://www.linkedin.com/in/markusjakobsson/ Markus Jakobssson>
 
- https://www.linkedin.com/in/aude-bourdouxhe-40656b28/ Aude Bourdouxhe

- https://www.linkedin.com/in/jlleleu/ Jean-Luc Leleu



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

### Milestone 1 — Implement GCF Substrate Modules

- **Estimated duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can create and set-up a VHDL Master File, lauch Garbled Circuit generation and get the resulted Garbled circuit cid on IPFS.   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | GCF substrate Interface | GCF external service interface to interact with the following substrate modules and IPFS |  
| 2. | Substrate module: GCF CFG | We will create a Substrate GCF configuration pallet that will store GCF encrypted configuration information on chain (including cid of Master Circuit file, master key and other security parameter to ensure security of circuit production  |  
| 3. | Substrate GCF CFG CLI| a CLI to set-up  GCF configuration palllet | 
| 4. | Substrate module: OCW GCF | We will create an OCW pallet that will control and interact with GCF external service - Launch GC production and get resulted GC cid on IPFS |  
 



### Milestone 2 — GC management in substrate modules and Transaction Validation Protocol use case (first part)

- **Estimated Duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | Substrate module OCW GCP  | we will create a OCW GC Provider to interact with a GC evaluator/IPFS client  |  
| 2. | Substrate module: Authenticator| We will create a Substrate Authenticator  pallet that will implement the Transaction Validation protocol to manage GC evaluator and IPFS client|  
| 3. | Substrate GCP CLI| a CLI to request GC cid for evaluation | 
  
### Milestone 3 — Transaction Validation Protocol with  mobile use case (second part)

- **Estimated Duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example with mobile evaluators   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | Mobile Client (android 1.a/iOS 1.b) | We will create android and iOS mobile client with GC evaluator and IPFS light client to manage Transaction Confirmation |  
| 2. | Substrate module Mobile Registry | We will create a substrate Mobile Registry pallet to deal with mobile client (android/iOS) and Mobile Public Key and signature verification |  
| 3. | Substrate module: Authenticator with mobile | We will add mobile features to Substrate Authenticator/Transaction Validation Mngt  pallet|  

### Milestone 4 — Integration with substraTEE/IntegriTEE

- **Estimated Duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example in TEE environement with substraTEE  |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | substrate modules Authenicator port in TEE | We will migrate Authenticator in substraTEE/IntergriTEE workers |  
| 2. | Substrate module Mobile Registry port in TEE | We will migrate part of the mobile registry pallet in substraTEE/IntergriTEE workers |  
  


### Milestone 5 — GCF in TEE

- **Estimated Duration:** 1 month
- **FTE:**  2
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage GCF in IntelSGX/Asylo  |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | GCF external service in TEE | We will migrate GCF service in TEE/Intel SGX with Asylo framework | 
 
  




...


## Future Plans

Please include here

>how you intend to use, enhance, promote and support your project in the short term:

- We aim at develloping a user comunity and get in talks with Dapp and especially DeFi players with a taylored value proposition for them.
- Improvement of our Visual Cryptography scheme by reintroducing pure visual cryptography frame (to display character and figures) to increase the complexity and ressources required for an attack.
- potential research grant on our real-time Malware detection scheme
- add OT oblivious transfer in our pallet to enable usage of MPC with our GCF.
- add behavioral biometric feature

>the team's long-term plans and intentions in relation to it.

- Bounty to crack our transaction validation protocol when both Android protected confirmation and detection of adverse code execution will be deployed
- Include a TEE layer 2 to manage Root of trust based on full HSM hardware ( based on YubiHSM) to provide a 3 tier distributed HSM capability.
- Investigate potential integration with substrate connect to increase the security of the solution with additional on-chain features at device level.

![3T Distributed HSM overview drawio (Custom)](https://user-images.githubusercontent.com/4605611/143676701-869ebba4-51ff-49f5-9e3b-97797984d844.png)

- Reseach on other human brain decryption capabilities (like Visual Cryptography, audio cryptography, etc..): the long term Goal is to increase our capabilities to descriminate real human from bot with IA capabilities
[Review of the use of human senses and capabilities in cryptography](https://www.sciencedirect.com/science/article/pii/S1574013720304408)


## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Web3 Foundation Website / Medium / Twitter / Element / Announcement by another team / personal recommendation / etc.

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:


- Work you have already done.
- Wheter there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.


## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Web3 Foundation Website / Medium / Twitter / Element / Announcement by another team / personal recommendation / etc.

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:


- Work you have already done.
- Wheter there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.
