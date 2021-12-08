# W3F Grant Proposal


>
> See the [Grants Program Process](https://github.com/w3f/Grants-Program/#pencil-process) on how to submit a proposal.

- **Project Name:** Interstellar - Wallet Phase 1
- **Team Name:** Interstellar
- **Payment Address:** BTC, Ethereum (USDT/DAI) or Karura (kUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2 

> ⚠️ *The combination of your GitHub account submitting the application and the payment address above will be your unique identifier during the program. Please keep them safe.*

## Project Overview :page_facing_up:



### Overview


“The blockchain ecosystem needs an easy to use interface with hardware wallet security to reach the mass market.”
 
The main pain points of non-custodial wallet solutions still are:
- **User experience**  [Can an easy to set-up wallet be an efficient customer acquisition tool for DeFi players?](https://medium.com/@jlleleu/can-be-an-easy-to-set-up-wallet-an-efficient-customer-acquisition-tool-for-defi-players-8600812fe01e)  
- **Security** [Are cryptocurrency wallets more at risk than ever?](https://medium.com/@jlleleu/are-cryptocurrency-wallets-more-at-risk-than-ever-cf1ce9725de7) 

> We think that current wallet solutions slow down the DeFi adoption.


Interstellar is a novel non-custodial peace of mind mobile wallet with a hardware security level. Based on a Substrate blockchain and SubstraTEE/IntegriTEE workers.

**We can now provide the same hardware security level as hardware wallet with only a mobile and a blockchain**

![Grant-Scheme-White (1)](https://user-images.githubusercontent.com/4605611/145108720-becb76be-6c16-46c8-af69-7e953e5a166d.png#gh-dark-mode-only)




![Grant-Scheme-Black (3)](https://user-images.githubusercontent.com/4605611/145108818-6f8b6158-6c27-4f0d-a104-9d2469c73636.png#gh-light-mode-only)



**Thanks to Trusted User Interface TUI on mobile and Trusted Execution Environment on both mobile and blockchain nodes**

Because TUI is not yet avalaible on all mobiles devices we use a Garbled Circuit/Visual Cryptography scheme which provides an alternative that will be complementary down the road to mitigate potential flaws in TUI.

![HW2InterstellarGC_TUIdark drawio](https://user-images.githubusercontent.com/4605611/145189435-a7f2e09f-e96d-43d8-97e0-efb35ffe1cdb.png)



#### Features:
- **Hardware security Level** - TEE on nodes and mobiles (incl. TUI), garbled circuits and visual cryptography secure interface
- **Just download an app** - no registration, PIN, password, passphrase, private key or any secret to store or remember
- **Multichain Wallet** - securely store and interact with native cryptocurrency coins and tokens from multiple blockchains
- **Confirm a transaction with ONLY ONE SCREEN** - no SMS to wait for, no additional 2FA app to use, no QR code to scan

- **Up to 1,000,000 tps** - no tps limit due to slow consensus, thanks to IntegriTEE layer 2 based on hardware enclave technology 
- **Social Recovery Service** - leverages the existing Substrate pallet and a novel decentralized autonomous recovery service 
> We hope that we will be able to provide a response to the related RFP in the following phases
- **Features to securely send coins with social network messages (even to persons with no-wallet)** - explained in [Can an easy to set-up wallet be an efficient customer acquisition tool]
- **Cross chain swap feature** - based on a Continuous Liquidity Pool (CLP like THORChain but with higher security and performance) - leverages TEE/MPC/TTS + Trusted Transaction Validation protocol with a multisig option (mobiles + yubikey) for validators and large liquidity owners

#### Our solution is designed to support blockchain and DeFi mass market adoption with:

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


#### [Detailed documentation](https://docs.google.com/document/d/1RTPx4EeA0Ek33f-8_Dj7p-qjzBp6VqLrrXNhIrwvFWI/edit?usp=sharing) on the project

- **OCW Garbled Circuit Factory**
- **Transaction Validation protocol pallets (including mobile registry)**
  - **Transaction Validation Screen Technology (Trusted/Secure UI)**
  - **Mobile client GC evaluator** 




#### Garbled Circuit Factory **previous work**
The team has already developed a strong authentication solution with circuits based on JustGarble implementation https://cseweb.ucsd.edu/groups/justgarble/ that we customized with Free XOR and Half Gates and other specific improvement for our needs ( pre-computation of our Visual cryptographic Circuits).
We achieved a production ready platform with significant performance on the logic circuit and garbled circuit production with AES-NI. The whole pipeline use optimized memory management and avoid serialization/deserialization of the different circuit formats: HDL-> non-garbled->garbled.

------------

```shell
1 ./circuit_display_gen_bench -nb_circuits_to_generate=5000
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

> Where and how does your project fit into the ecosystem?

This project is the first phase of a wallet project. Although, we think that our Trusted Transaction Validation protocol could bring a novel approach to address UX/UI security issues regardless of other features of our frictionless wallet.
We designed our validation transaction protocol to benefit to other wallets or Dapps. We think it could also be complementary down the road to mobile light client like substrate connect (check **Future Plans** section).
  





![TTV overview overview drawio](https://user-images.githubusercontent.com/4605611/144742049-54d3a212-b471-4a69-9f44-adfb150814ca.png#gh-light-mode-only)


![TTV overview overview dark drawio](https://user-images.githubusercontent.com/4605611/144738926-e6f0db47-f7ff-4382-ae5d-251420e23a61.png#gh-dark-mode-only)



>Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?

We want to target in priority Dapp providers in the DeFi ecosystem with developer tools to integrate our solution with their Dapps. We think that our value proposition should be attractive to them.
At the same time we want to target newcomers with a Robinhood for DeFi wallet app that include average dollar cost feature.

> What need(s) does your project meet?

The need for a wallet to be simpler to set-up and use, as well as the need for higher security to address the growing malware/banking trojan threats.

> Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?

Math Wallet and Gluon are close to our solution

We think that we could bring a better user experience, security and performance, thanks to a highly scalable layer 2 based on substraTEE: 

- Math Wallet is based on MPC that requires heavier computation resources. They also envision smartcards with screen for users. It's comparable to our level of security, but more expensive, cumbersome to use, less flexible and more complex to deploy than our solution.
 
- Gluon QR code based transaction confirmation that requires 2 screens is more cumbersome for the user. Moreover, this scheme is already exposed to banking trojan with overlay capabilities*. Although their TPM based approach could be complementary down the road to TEE, to mitigate potential future flaws on Intel SGX.
> *see: An attack high level description on solutions that use QR code for transaction confirmation [Are cryptocurrency wallets more at risk than ever](https://medium.com/@jlleleu/are-cryptocurrency-wallets-more-at-risk-than-ever-cf1ce9725de7) 
 


## Team :busts_in_silhouette:

### Team members

- Name of team leader:
- Jean-Luc Leleu
- Names of team members:
- Nathan Prat
- Eliot Leleu
- Jean-Louis Hoenen
- Aude Bourdouxhe
- Philippe Salats ( advisor)


### Contact

- **Contact Name:** Jean-Luc Leleu
- **Contact Email:** jeanluc.leleu@protonmail.com
- **Website:** https://www.interstellar.gg/

### Legal Structure

- **Registered Address:** N/A
- **Registered Legal Entity:** N/A - we are still in the process of establishing a legal entity.

### Team's experience
[Team deck](https://docs.google.com/presentation/d/1AuM5YO4ysFqoj3uquQ46NJIprDSaALZrqUqAef-ITns/edit?usp=sharing)

We are now security and fintech multiple entrepreneurs, security researchers, patents fillers who turn open-source developers and blockchain enthusiasts.

### Team Code Repos

- https://github.com/Interstellar-Network
- https://github.com/Interstellar-Network/wallet-ph1



- https://github.com/nathanprat


### Team LinkedIn Profiles (if available)

- https://www.linkedin.com/in/nathan-prat/ Nathan Part
 
- https://www.linkedin.com/in/eliotjfl/ Eliot Leleu 
 
- https://www.linkedin.com/in/jlhoenen/ Jean-Louis Hoenen>

- https://www.linkedin.com/in/aude-bourdouxhe-40656b28/ Aude Bourdouxhe
 
- https://www.linkedin.com/in/philippesalats/ Philippe Salats (advisor)

- https://www.linkedin.com/in/jlleleu/ Jean-Luc Leleu


## Development Roadmap :nut_and_bolt:

### Overview

- **Total Estimated Duration:** 5 months
- **Full-Time Equivalent (FTE):**  11
- **Total Costs:** 47,000 USD

### Milestone 1 — Implement GCF Substrate Modules

- **Estimated duration:** 1 month
- **FTE:**  2.2
- **Costs:** 9,400 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT  |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can create and set-up a VHDL Master File, launch Garbled Circuit generation and get the resulted Garbled circuit cid on IPFS.   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | GCF substrate Interface | GCF external service interface to interact with the following substrate modules and IPFS |  
| 2. | Substrate module: GCF CFG | We will create a Substrate GCF configuration pallet that will store GCF encrypted configuration information on chain (including cid of Master Circuit file, master key and other security parameter to ensure security of circuit production  |  
| 3. | Substrate GCF CFG CLI| a CLI to set-up  GCF configuration pallet | 
| 4. | Substrate module: OCW GCF | We will create an OCW pallet that will control and interact with GCF external service - Launch GC production and get resulted GC cid on IPFS |  
 



### Milestone 2 — GC management in substrate modules and Transaction Validation Protocol use case (first part)

- **Estimated Duration:** 1 month
- **FTE:**  2.2
- **Costs:** 9,400 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT  |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | Substrate module OCW GCP  | we will create a OCW GC Provider to interact with a GC evaluator/IPFS client  |  
| 2. | Substrate module: Authenticator| We will create a Substrate Authenticator  pallet that will implement the Transaction Validation protocol to manage GC evaluator and IPFS client|  
| 3. | Substrate GCP CLI| a CLI to request GC cid for evaluation | 
  
### Milestone 3 — Transaction Validation Protocol with  mobile use case (second part)

- **Estimated Duration:** 1 month
- **FTE:**  2.2
- **Costs:** 9,400 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example with mobile evaluators   |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | Mobile Client (android 1.a/iOS 1.b) | We will create android and iOS mobile client with GC evaluator and IPFS light client to manage Transaction Confirmation |  
| 2. | Substrate module Mobile Registry | We will create a substrate Mobile Registry pallet to deal with mobile client (android/iOS) and Mobile Public Key and signature verification |  
| 3. | Substrate module: Authenticator with mobile | We will add mobile features to Substrate Authenticator/Transaction Validation Mngt  pallet|  

### Milestone 4 — Integration with substraTEE/IntegriTEE

- **Estimated Duration:** 1 month
- **FTE:**  2.2
- **Costs:** 9,400 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example in TEE environment with substraTEE  |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | substrate modules Authenticator port in TEE | We will migrate Authenticator in substraTEE/IntegriTEE workers |  
| 2. | Substrate module Mobile Registry port in TEE | We will migrate part of the mobile registry pallet in substraTEE/IntegriTEE workers |  
  


### Milestone 5 — GCF in TEE

- **Estimated Duration:** 1 month
- **FTE:**  2.2
- **Costs:** 9,400 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT  |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage GCF in IntelSGX/Asylo  |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | GCF external service in TEE | We will migrate GCF service in TEE/Intel SGX with Asylo framework | 
 
  




...


## Future Plans



>how you intend to use, enhance, promote and support your project in the short term:

- We aim at developing a user community and get in talks with Dapp and especially DeFi players with a tailored value proposition for them.
- Garbled Circuit Evaluator in WASM to enable its use on browser and nodes - Transaction Validation variants on browsers.
- Improvement of our Visual Cryptography scheme by reintroducing pure visual cryptography frame to display character, figures, images. It should increase the complexity, cost and resources required for an attack.
- Potential research grant on our real-time Malware detection scheme
- Add OT oblivious transfer in our pallet to enable usage of MPC with our GCF.
- Add behavioural biometric feature

>the team's long-term plans and intentions in relation to it.

- Bounty to crack our transaction validation protocol when both Android protected confirmation and detection of adverse code execution will be deployed
- Include a TEE layer 2 to manage a Root of trust based on full HSM hardware ( with YubiHSM type of solution) to provide a 3 tier distributed HSM capability.



- Investigate potential integration with substrate connect to increase the security and flexibility of our solution with potential additional on-chain/off-chain data/features at mobile/browser level.

![3T Distributed HSM overview drawio](https://user-images.githubusercontent.com/4605611/144741459-3776d2a7-a64b-40f8-b8a9-98abd590e452.png#gh-light-mode-only)

![3T DHSM overview dark drawio](https://user-images.githubusercontent.com/4605611/144741651-ff9f0bb0-91cb-4b76-8f0e-097395303723.png#gh-dark-mode-only)




- Research on other human brain decryption capabilities (like Visual Cryptography, audio cryptography, etc..): the long term Goal is to increase our capabilities to discriminate real humans from bots with IA capabilities. [ Review of the use of human senses and capabilities in cryptography](https://www.sciencedirect.com/science/article/pii/S1574013720304408)

## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Web3 Foundation Website / Medium / Twitter / Element / Announcement by another team / personal recommendation / etc.

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:


- Work you have already done.
- Whether there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.
