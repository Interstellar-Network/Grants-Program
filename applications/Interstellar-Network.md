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

![Copy of Interstellar-Black-Text](https://user-images.githubusercontent.com/4605611/141333053-3f607ffe-1714-4512-b628-33274d0d0464.png)


 **Interstellar Wallet Phase 1: Substrate OCW Garbled Circuit Factory GCF and Trusted Transaction Validation protocol pallet demo (as a GCF use case)** 
 
#### Why Interstellar wallet?

**User experience** and **Security** are still the main **pain points** of non-custodial wallet. We think that they slow down blockchain and DeFi adoption.

- **Wallets are not easy for newcomers and even for some experienced users:**

The Public Private key concept is complex for non-technical people and can be easily misused. The process of wallet creation can be a bit confusing and misleading, and the average user still do not understand clearly what information, passphrase, private key, etc. need to be protected and how to store it safely.

- **Only Hardware Wallets (like Ledger, Trezor, Ngrave, etc.) are secures:**

Because blockchains themselves and centralized exchanges are getting more secures, bad actors now focus their attacks on Individual wallets and exchange accounts. 

Banking trojans are now also targeting cryptocurrencies's owners. Dapp and wallets are more and more exposed on mobiles and in browsers as those trojans are getting more sophisticated and pervasive.
**“Android banking malware, which rose by an incredible 158.7 per cent in Q1, saw a continued increase of 49 per cent”**- Source ESET quarterly threat report 2021. Zero day that enables bad actors, through “exploit chain”, to get the control on mobile operating system and browsers have never been higher.[2021 has broken the record for zero-day hacking attacks]( https://www-technologyreview-com.cdn.ampproject.org/c/s/www.technologyreview.com/2021/09/23/1036140/2021-record-zero-day-hacks-reasons/amp/)

Given the growth dynamic of the malware/banking trojan threat, the blockchain ecosystem need now a protection against malware on mobiles wallet and Dapps.
We think that Hardware security, Trusted Execution Environnement TEE and especially Trusted User Interface TUI can provide a level of hardware security comparable to hardware wallet. Mobile UI security is crucial on this respect to address current and growing threats (including banking trojan with their overlay capabilities). They can easily build fake UI that mislead user to trigger tampered transaction. From a pure security standpoints mobile banking application (DSP2 compliant) are now more robust than mobile wallet. As a consequence, threat actors focus now on wallets.

At the time of W3f, Parity, Polkadot is pushing its light client on the mobile and browsers to increase security. We think that the blockchain ecosystem and especially polkdaot/kusama will benefit from the adding of a TRUSTED UI LAYER (including hardware protected Tusted User Interface TUI and Trusted Execution Environement TEE) for mobiles light client like Substrate connect. Unfortunately, TUI and full TEE features are not yet available on all mobiles and the most advanced feature you find on servers will take time to be mainstream, as manufacturers are slow to integrate them. Moreover, ARM TrustZone still lack of a service like IAS for IntelSGX for the management of remote attestation.

#### Our solution to address the previous issues

There is a security gap to fill before TEE and TUI will be fully avalaible on a large majority of mobile.
We use One Time and Reusable Garbled circuits to ensure private computation and visual cryptography to help on the UI security issues. Thi is an alternative that will be complementary down the road to mitigate potential future security flaws in TEE and TUI.

Interstellar is a novel type of non-custodial **frictionless** decentralized wallet with **hardware security level**, designed to support blockchain and DeFi **mass market adoption**.

#### Features/Benefits

- **Just download an app** with no set-up nor registration, no Private Keys nor passphrase to backup, no PIN, password, or any secret to remember*
- **Confirm a transaction with ONLY ONE SCREEN** No short text message (SMS) to wait for, no additional 2FA app (like Google Authenticator) to use, no QR code to scan.
Anyway, banking trojan can already compromise the previous 2FA schemes*
[Android banking Trojan to steal cryptocurrency and 2FA codes](https://www.revelock.com/en/blog/oscorp-android-banking-trojan-to-steal-cryptocurrencies-and-2fa-codes  )


 **You just need to input on the keypad the one-time code you see (here 256)**

**That's all to securely confirm a transaction** ![Wallet-superposition-White-Shadow4medium smaller](https://user-images.githubusercontent.com/4605611/141301152-951143c3-d820-4bc1-8120-5a60a6878d52.png)
> ***And the best part, this scheme is designed to resist malware attacks from state of the art banking trojan (and even targeted attacks at a later stage)


- **Decentralized key & asset management service** where user’s privates key and signature program are stored and executed in Hardware Enclave/Trusted Execution Environment TEE*

- **Social Recovery Service** that leverages the existing substrate pallet, and a novel decentralized autonomous recovery service* (Comment: we hope that we will be able to provide a response to the related RFP in the following phases)
- **Features to securely send coins with social network messages (even to people with no-wallet)** Link to "Can be easy to set-up wallet an efficient customer acquisition tool for DeFi players" to add
- **Cross chain Swap feature** based on a Continious Liquitity Pool (CLP like ThorChain but with higher security and performance TEE/MPC/TTS + Trusted Transaction Validation protocol with mutisig option*  mobiles + yubikey for Validators and power users)


#### Substrate Technology Overview

**The solution relies on a substrate blockchain and on substaTEE/IntegriTEE Workers** to secure private keys, signature programs and the friendly authentication and transaction validation service. The last service use a novel **Decentralized Trusted Transaction Validation Protocol** that leverage **TEE features on mobile**, combined with **One Time Garbled Circuit and Visual Cryptography** to provide a **Trusted Authentication and Trusted UI layer** on user devices.

***Link to medium Interstellar Wallet – Technology and security lightpaper.(draft/work in progress)**

#### Interstellar project Phase 1:

The project phase 1 focus on two of the core components of the Interstaller solution: An OCW garbled circuit factory GCF (to manage an external Garbled Circuit Genrator service) and an implementation of the transaction validation protocol in substrate pallets. It demonstrate the usage of GCF whithin a substrate framework and with a mobile client Garbled Circuit evaluator. We designed this Garbled circuit Factory to be used by substrate devellopers regardless of Interstellar solution.

Following are other use cases of Garbled Circuit Factory:

- Every schemes  based on Garbled Circuit generator and evaluator
- Multi Party Computation MPC protocol (when oblivious transfer OT will be managed in pallets)
- Proof of history of legitimate computation with reusable garbled circuit (Interstellar ongoing research: Detection of adverse code execution during short transaction session) - end of Technology and security lightpaper.(draft/work in progress)
- Efficient alternative to Public Key encryption. (based on AES or symetric encryption  Garbled Circuit that embed securely the symetric secret key, highly increase performance on recipent nodes)
- Post Quantum encryption and signature scheme implementation (NIST candiate examples)


### Project Details
- Mockups/designs of any UI components
- Data models / API specifications of the core functionality
- An overview of the technology stack to be used
- Documentation of core components, protocols, architecture, etc. to be deployed
- PoC/MVP or other relevant prior work or research on the topic
- What your project is _not_ or will _not_ provide or implement
  - This is a place for you to manage expectations and to clarify any limitations that might not be obvious

#### Garbled Circuit Factory GCF overview

Before to go into the details of Garbled Circuit Factory architecture, let's digg into the design of a basic garbled circuit structure.

A garbled circuit is a cryptographic obfuscation technique and a cryptographic algorithm that ensures computation privacy i.e. manages the protection of a Boolean circuit that can be executed without leaking information. Neither the semantics of Boolean operators (AND, OR, XOR, etc.) that makes up the circuit nor the semantics of inputs and outputs of the circuit will be revealed to the attackers through reverse-engineering or brute force attacks

![1_v4GuUlPEaVzo6gGZdJ4R6g (1) (Phone) (Custom)](https://user-images.githubusercontent.com/4605611/141653727-44bc2460-44eb-4179-ad39-00e55f7f0775.jpeg)


- Inputs and Outputs are Garbled Values i.e. 128 bits token indistinguishable from random with a secret semantic value of 0 or 1 only known by the nodes
- Each Boolean operator is implemented in the circuit by an encrypted truth table, decrypted by its respective Garbled Values inputs.

More detailed on the topic:
[Foundation of Garbled Circuits,   Viet Tung Hoang, B.S. (National University of Singapore) 2007 ](https://www.cs.fsu.edu/~tvhoang/thesis.pdf)

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







#### Garbled Circuits Factory high level architecture and GC production pipeline

Following are the different componenets of the GCF:
![GCF pipeline drawio](https://user-images.githubusercontent.com/4605611/141283607-f95a7170-9729-4af4-9221-d776f52223f3.png)


##### GCF components:
- Circuit Production Orchestrator/Scheduler

Input: VHDL Generic File master circuit.
ex: in our use case, it is the generic circuit that display the Transaction Validation screen, with one time code amd random keypad topology.

- Circuit Randomizer
Input: VHDL generic file

Output: a VHDL circuit file with randomized parts (managed with composition of  sub circuits)
ex: in our case, set-up the random one time code and keypad, with specific attributes, differents fonts and fonts size, random deformation, etc..

- Circuit Generator ( build netlist and manage optimization: limit number of logical gates,etc..)

Input: VHDL Circuit file outputed by Randomizer
Output: Logical Circuit file ( custom scd format IntSCD)

- Garbled Circuit Generator

Input: IntSCD Logical Circuit File
Output: Garbled Circuit File (ready to be evaluated on mobile)

#### GCF integration in substrate

Given the constraint related to GC Factory code and library dependencies especially VHDL/Verilog i.e not compilable in WASM (rust -no-std) - It sounds simpler for now to use regular/basic substrate OCW Off-Chain Workers to integrate with GCF as an external service. And then to use this in Intel SGX TEE enclave.
As Garbled Circuits are heavy, it is better to store them on IPFS. IPFS  store only their IPFS hash/cid encrypted on-chain when needed and store their cid in TEE workers  to use them with Authenticator pallet


![GCF-Substrate drawio](https://user-images.githubusercontent.com/4605611/142644005-1ca280b7-e1e4-4ff6-afad-be6a7ea597b5.png)



##### GCF substrate components

- GCF configuration pallet:

input: Master File + (at a later stage) sub circuits use in randomization) + security parameters (a master key to derive session keys for circuit production)
Store this configuration information on-chain ( at later stage, we plan to split this information with an encrypted part on-chain and another part  off-chain in TEE workers)

- OCW GCF:

Launch circuit generation request
Get IPFS cid in response

- Substrate extrinsecs and RPC to use  GC in runtime pallet and OCW GC Provider pallet to serve  GC cid to GC evaluator clients




#### GCF in Interstellar architecture

First architecture approach, STF functions will be managed through Parity Substrate Frame pallets with substraTEE/IntegrTEE framework.
Pallets on both substrate TEE nodes (not in SGX enclave) and substrate TEE workers (in SGX enclave).

Thanks to integritee-network.
- integritee-node: substraTEE node with TEE registry validating remote attestation https://github.com/integritee-network/integritee-node
- integritee-worker: substraTEE worker https://github.com/integritee-network/worker


![Node architecture 4github](https://user-images.githubusercontent.com/4605611/141462134-e7c58840-5f7e-4a6c-add5-80fa1cd12498.png)




#### Trusted Transaction Validation protocol building blocks

- Trusted Authentication and Secure UI layer
- Trusted Transaction Validation Management on TEE layer 2 nodes (substrate Frame pallet)

----------------------------------------------------
**Trusted Authentication and Secure UI**

Because some TEE features are still missing on some mobiles and to address potential future flaws in mobile TEE (and TUI when available), we provide a strong authentication and secure UI scheme based on the combination of One Time Garbled Circuits evaluation and Visual Cryptography scheme.

![GC-VC part 1 (Custom) (Custom) (1) (Custom)](https://user-images.githubusercontent.com/4605611/141459596-29ffd9a5-4879-4f18-b61d-77c92feb0fbb.png)


![Visual_crypto_animation_demo](https://user-images.githubusercontent.com/4605611/141341588-c431d0a4-67eb-4d5a-8e0a-ae99c88c9ed7.gif)

We use a pre-computed One-time Garbled Circuit to generate and outputs Visual Cryptographic Shares at 60–120 Frames/Seconde on the device framebuffer.

Those visual cryptographic shares do not superpose on the device screen but only in the user's eye. Thanks to the human Persistence of Vision properties. This ensures that an attacker won' be able to obtain the secret information (transaction message, one time code and random keypad topology) with a simple screenshot, or quickly enough to build and execute a fake User Interface.
This scheme makes a fake UI attack, complexe and ressource intensive enough to enable us to detect it during the transaction validation session. Thanks to our proof of history of legitimate computation scheme, (roadmap/research in progress), based on a specific reusable Garbled Circuit evaluation.



Although, we started by implementing a working solution that output visual cryptographic shares we realized that it was a bit disturbing for the user and that pure viusal cryptographic scheme is not crucial for our overall security model. We then decided to provide a more friendly solution for the user that is also more efficient especially regarding Garbled Circuit size.

So, let's go back to old fashion display to do it.
![images8](https://user-images.githubusercontent.com/4605611/141358949-5c0eaffb-e0c3-437d-88f9-7ab948f782a0.png)




--------------------------------------------------------

#### Trusted Transaction Validation Protocol architecture overview

We expect the teams to already have a solid idea about your project's expected final state. Therefore, we ask the teams to submit (where relevant)

**High level componenents overview of Interstellar blockchain based on parity substrate and IntegriteeTEE workers sidechain**

Include future roadmap modules

![Interstellar Overview-Page-1 drawio](https://user-images.githubusercontent.com/4605611/142175758-236146cf-ad5a-4cd1-b1b8-ddf96d24d798.png)

A Public/Private key pair is generated in the mobile Hardware enclave. The private key is not accessible by anyone, even when the device is rooted and signature is triggered only with user's biometrics (also managed with TEE)

This mobile Private key and a set of Garbled Circuits are securely tied with the wallet private keys associated with user's assets and managed in the blockchain hardware enclave TEE nodes. To prevent potential attacks on Hardware Enclaves on nodes, we will also use down the road Multi Party Computation and especially Threshold Signature Scheme.

Transaction screen is managed with Garbled circuits that are pre-computed on TEE nodes and provisioned on the mobile by the nodes from time to time. The one-time code secret and keypad topology cannot be accessed during garbled circuit execution to display the Visual Cryptographic secret frames that appears only in users' eyes (thanks to persistence of vision)

Touch screen positions matching the one-time code are sent to the node in a message signed with mobile private key, triggered with biometrics for validation.
Once the message is received by the node, if valid, the crypto transaction is signed with related wallet private key and submit to the related blockchain network.

Behavioral Biometric: each user has a unique typing pattern for a sequence of digits on a keypad. So, if a bad actor tries to replicate this pattern. It will be detected with a 98% success rate. This feature will be managed by TEE nodes with Machine Learnings classification models based on secret touch screen position inputs received by the nodes and their related authenticated timestamps. 

Ref. USERS' TOUCH DYNAMIC BIOMETRICS TO ENHANCE AUTHENTICATION ON MOBILE DEVICES (manchester.ac.uk)https://www.research.manchester.ac.uk/portal/files/159168194/FULL_TEXT.PDF

Ongoing research (roadmap): Garbled circuits to generate proof of history of legitimate computation scheme to detect malware attacks tentative to compromise the UI i.e. the building and execution of a fake User Interface by the attackers.
***Link to Intertsellar Light paper**


-------------------------------------------




**Detailed architecture for the Transaction Validation protocol use case demo**


![Transaction Validation Module drawio](https://user-images.githubusercontent.com/4605611/141464149-3741ae99-d3bf-47fc-a1f2-a30e23592316.png)

Each time a transaction validation is required, a request is sent to the nodes. This request includes an operation message including transaction parameter: amount, destination address wallet.
Upon reception of this message the node associates a precomputed garbled circuit program on the wallet owner mobile app and compute a cryptographic mask including transaction parameters to oversee displaying of each pixel on the user's device's screen. Then this mask is sent to the mobile app with the asymmetric key to decrypt the chosen garbled circuit own by the wallet owner.
When the client's device receives masks and symmetric key, the device evaluates the circuit to display the keypad and the authentication message with one-time code for validation.
Once the transaction screen appears on device, the user will type the one-time code displayed on the random keypad.
The response, randomized position is then signed and sent to the nodes for validation. Wallet owner fingerprint is used to authenticate user presence and enable the signature of the message with the user device private key stored in the hardware enclave. The node uses its associated public key to verify that the randomized position taped by the wallet owner come from his devices and that the user was present at that time. Thanks for the associated fingerprint user authentication managed with mobile hardware enclave.
This process ensures that even if a legit garbled circuit is stolen, it cannot be used by another device through a man in the middle attack to validate the transaction.







### Ecosystem Fit

Help us locate your project in the Polkadot/Substrate/Kusama landscape and what problems it tries to solve by answering each of these questions:

- Where and how does your project fit into the ecosystem?



![Transaction Validation overview drawio](https://user-images.githubusercontent.com/4605611/142284724-8b5660f5-fdbb-4ddb-b012-9a2b9c2eb901.png)








- Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?
- What need(s) does your project meet?
- Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?
  - If so, how is your project different?
  - If not, are there similar projects in related ecosystems?

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

month 1: Off-chain worker substrate Garbled circuit Factory
0
License
Documentation
Testing guide
Docker test all the features
Article
1
Circuit Design ->HDL
Circuit randomizer-> HDL
Boolean circuit generation-> scd format
scd->fancy garble/swanky format
replace Garbled circuit generator JustGarble by swanky.
circuit evaluator test
production schedulers communicate with pallets.
storage IPFS
Bench 

month 2: fig transaction validation for use case demo
API GCF ->pallet
describe API
check evaluation with circuits metadata i.e. OTP random keypad







month 3: 
TEE integration with pallet


month 4: 
Transaction Validation protocol demo with mobile- android (iOS/)
pallet mobile
month 5: TEE for OCW GCF










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
| 2. | Substrate module: GCF CFG | We will create a Substrate GCF configuration pallet that will store GCF configuration information on chain (including security parameter ie master key to ensure security of circuit production batch  |  
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
- **FTE:**  2,5
- **Costs:** 12,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | Mobile Client (android 1.a/iOS 1.b) | we will create android and iOS mobile client with GC evaluator and IPFS light client to manage Transaction Confirmation |  
| 2. | Substrate module Mobile Registry | we will create a substrate Mobile Registry pallet to deal with mobile client (android/iOS) and Mobile Public Key and signature verification |  
| 3. | Substrate module: Authenticator with mobile | We will add mobile features to Substrate Authenticator/Transaction Validation Mngt  pallet|  






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
