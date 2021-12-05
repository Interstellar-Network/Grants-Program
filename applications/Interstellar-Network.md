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

![Copy of Interstellar-Black-Text](https://user-images.githubusercontent.com/4605611/141333053-3f607ffe-1714-4512-b628-33274d0d0464.png)

“The blockchain ecosystem needs an easy to use interface with hardware wallet security to reach the mass market.” 
The main pain points of non-custodial wallet solutions are still:
- **User experience**  [Can be an easy to set-up wallet an efficient customer aquisition tool for DeFi players?](https://medium.com/@jlleleu/can-be-an-easy-to-set-up-wallet-an-efficient-customer-acquisition-tool-for-defi-players-8600812fe01e)  
- **Security** [Are cryptocurrency wallets more at risk than ever?](https://medium.com/@jlleleu/are-cryptocurrency-wallets-more-at-risk-than-ever-cf1ce9725de7) 

> We think that current wallet solutions slow down the DeFi adoption.


Interstellar is a novel non-custodial peace of mind mobile wallet with a hardware security level. Based on a Substrate blockchain and SubstraTEE/IntegriTEE workers, the wallet is the blockchain.

![HW2Interstellar drawio](https://user-images.githubusercontent.com/4605611/144306533-24e88a5e-ed01-44f9-974c-2f51e0c5ea62.png)


#### Features:
- **Hardware security Level** - TEE on nodes and mobiles (incl. TUI), garbled circuits and visual cryptography secure interface.
- **Just download an app** - no set-up nor registration, no Private Keys nor passphrase to backup, no PIN, password, or any secret to remember
- **Multichain Wallet** - securely store and interact with native cryptocurrency coins and tokens from multiple blockchains
- **Confirm a transaction with ONLY ONE SCREEN** - no SMS to wait for, no additional 2FA app to use, no QR code to scan.

- **Up to 1,000,000 tps** - thanks to IntegriTEE layer 2 based on hardware enclave technology
- **Social Recovery Service** - leverages the existing substrate pallet, and a novel decentralized autonomous recovery service 
> Comment: we hope that we will be able to provide a response to the related RFP in the following phases
- **Features to securely send coins with social network messages (even to people with no-wallet)** - [Can be an easy to set-up wallet an efficient customer aquisition tool for DeFi players?](https://medium.com/@jlleleu/can-be-an-easy-to-set-up-wallet-an-efficient-customer-acquisition-tool-for-defi-players-8600812fe01e)
- **Cross chain Swap feature** - based on a Continious Liquitity Pool (CLP like ThorChain but with higher security and performance) - leverages TEE/MPC/TTS + Trusted Transaction Validation protocol with a mutisig option (mobiles + yubikey) for Validators and large liquitity owners

#### Our solution is designed to support Blockchain and DeFi mass market adoption with:

- **A Decentralized key & asset management service** where user’s privates key and signature program are stored and executed in TEE
- **A Decentralized Trusted Transaction Validation Protocol** that leverages **TEE features on mobile incl. TUI**, combined with **One Time Garbled Circuit** and **Visual Cryptography** to provide a **Trusted Authentication and Trusted UI layer** on user devices.


The **Interstellar - Wallet Phase 1** W3F Grant Proposal focuses on two of the core components of the Interstaller solution: 

- A substrate Off-Chain Worker OCW Garbled Circuit Factory GCF to manage an external garbled circuit generator service (designed to be used by substrate devellopers regardless of Interstellar solution)
- An implementation of the Transaction Validation protocol in Substrate pallets to demonstrate the usage of GCF whithin a Substrate framework and with a mobile  Garbled Circuit evaluator client. 

Following are other use cases of Garbled Circuit Factory:

- Every schemes  based on Garbled Circuit generator and evaluator
- Multi Party Computation MPC protocol (when oblivious transfer OT will be managed in pallets)
- Proof of history of legitimate computation with reusable garbled circuit (Interstellar ongoing research: Detection of adverse code execution during short transaction session - work in progress)
- Post Quantum encryption and signature scheme implementation (NIST candiate examples)


### Project Details


#### [Detailed documentation](https://docs.google.com/document/d/1RTPx4EeA0Ek33f-8_Dj7p-qjzBp6VqLrrXNhIrwvFWI/edit?usp=sharing) on the project

- **OCW Garbled Circuit Factory**
- **Transaction Validation protocol pallets (including mobile registry)**
  - **Transaction Validation Screen Technology (Trusted/Secure UI)**
  - **Mobile client GC evaluator** 




#### Garbled Circuit Factory **previous vork**
The team has already develloped a strong authentication solution with circuits based on JustGarble implememtation https://cseweb.ucsd.edu/groups/justgarble/ that we customized with Free XOR and Half Gates and other specific improvement for our needs ( pre-computation of our Visual cryptographic Circuits).
We achieved a production ready platform with significant performance on the logic circuit and garbled circuit production with AES-NI. The whole pipeline use optimized memory mangement and avoid serialization/deserialization of the different circuit formats: HDL-> non-garbled->garbled.

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

This project is the first phase of a wallet project. Although, we think that our Trusted Transaction Validation protocol could bring a novel approach to address UX/UI security issues regardless of other features of our frictionless wallet.
We designed our validation transaction protocol to benfit to other wallets or Dapps. We think it could also be complemetary down the road to mobile light client like substrate connect (check **Future Plans** section).
  - -

![TTV overview overview drawio](https://user-images.githubusercontent.com/4605611/143036398-f4111713-652e-4478-8c77-afc9926149c1.png#gh-light-mode-only)

![TTV overview overview dark drawio](https://user-images.githubusercontent.com/4605611/144738811-d061b935-5dc3-4849-a3db-9cb117a06813.png#gh-dark-mode-only)


![TTV overview overview dark drawio](https://user-images.githubusercontent.com/4605611/144738369-e49db5af-b736-44ab-abcc-fd2b9706babc.png#gh-dark-mode-only)


>Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?

We want to target in priority Dapp providers in the DeFi ecosystem with develloper tools to integrate our solution with their Dapps. We think that our value proposition should be attractive to them.  (link growth tool)
At the same time we want to target newcomers with a Robinhood for DeFi wallet app that include average dollar cost feature.

> What need(s) does your project meet?

The need for a wallet to be simpler to set-up and use, as well as the need for higher security to address the growing malware/banking trojan threats. (link attacks list in light paper)

> Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?

Math Wallet and Gluon are close to our solution

We think that we could bring a better user experience, security and performance, thanks to a highly scalable layer 2 based on substraTEE: 

- Math Wallet is based on MPC that require heavier computation ressources. They also envision smartcard with screen. Despite a comparable level of security, it is more expensive, cumbersome to use, less flexible and more complex to deploy than our solution.
 
- Gluon QR code based transaction confirmation that requires 2 screens is more cumbersome for the user. Moreover, this scheme is already exposed to banking trojan with overlay capabilities*. Although their TPM based approach could be complementary down the road to TEE, to mitigate potential future flaws on Intel SGX.
> *see: An attack high level description on solutions that use QR code for transaction confirmation [Are cryptocurrency wallets more at risk than ever](https://medium.com/@jlleleu/are-cryptocurrency-wallets-more-at-risk-than-ever-cf1ce9725de7) 
 


## Team :busts_in_silhouette:

### Team members

- Name of team leader:
Jean-Luc Leleu
- Names of team members:
- Nathan Prat
- Eliot Leleu
- Jean-Louis Hoenen
- Aude Bourdouxhe
- Philippe Salats ( advisor)


### Contact

- **Contact Name:** Full name of the contact person in your team
- **Contact Email:** 
- **Website:** https://www.interstellar.gg/

### Legal Structure

- **Registered Address:** Address of your registered legal entity, if available. Please keep it in a single line. (e.g. High Street 1, London LK1 234, UK)
- **Registered Legal Entity:** Name of your registered legal entity, if available. (e.g. Duo Ltd.)

### Team's experience

We are a cybersecurity team, specialized in end-user devices & smartphone security,  now working on blockchain after some experiences with the banking industry. We have won the cybersecurity innovation award from Société Générale SG bank and Wavestone (security consulting and audit firm in the financial industry). We have also been selected by 500 startup Accelerator, batch 20 in San Francisco and have our patent portfolio financed by France Brevet, a government agency.

- 2018 Thales strategic partner(selected in Thales first batch 
accelerator in Station F)
- Partnership with Gemalto to issue smartcard hardware wallet 
solution for blockchain.
- 2017 500 Startups batch 20 (San Francisco California)
- Banking Cyber Security Innovation Awards winner
- 2016 Patent portfolio (10+ patents) financed by France Brevet

We then stop the activity of our former company to address legacy financial institutions and let go our patent ownership to focus on blockchain project.
We are now security and fintech multiple entrepreneurs, security researchers, patents fillers who turn open-source developers and blockchain enthusiasts.

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

- https://www.linkedin.com/in/aude-bourdouxhe-40656b28/ Aude Bourdouxhe
 
- https://www.linkedin.com/in/philippesalats/ Philippe Salats (advisor)

- https://www.linkedin.com/in/jlleleu/ Jean-Luc Leleu



## Development Status :open_book:

If you've already started implementing your project or it is part of a larger repository, please provide a link and a description of the code here. In any case, please provide some documentation on the research and other work you have conducted before applying. This could be:

- links to improvement proposals or [RFPs](https://github.com/w3f/Grants-Program/tree/master/rfp-proposal) (requests for proposal),
- academic publications relevant to the problem,
- links to your research diary, blog posts, articles, forum discussions or open GitHub issues,
- references to conversations you might have had related to this project with anyone from the Web3 Foundation,
- previous interface iterations, such as mock-ups and wireframes.

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
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can manage Garbled circuit cid in pallets. with a transaction validation use case example in TEE environement with substraTEE  |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)  |  
| 1. | substrate modules Authenicator port in TEE | We will migrate Authenticator in substraTEE/IntegriTEE workers |  
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

- We aim at develloping a user comunity and get in talks with Dapp and especially DeFi players with a taylored value proposition for them.
- Improvement of our Visual Cryptography scheme by reintroducing pure visual cryptography frame to display character, figures, images. It should increase the complexity, cost and ressources required for an attack.
- Potential research grant on our real-time Malware detection scheme
- Add OT oblivious transfer in our pallet to enable usage of MPC with our GCF.
- Add behavioral biometric feature

>the team's long-term plans and intentions in relation to it.

- Bounty to crack our transaction validation protocol when both Android protected confirmation and detection of adverse code execution will be deployed
- Include a TEE layer 2 to manage a Root of trust based on full HSM hardware ( with YubiHSM typeof solution) to provide a 3 tier distributed HSM capability.



- Investigate potential integration with substrate connect to increase the security and flexibility of the solution with potential additional on-chain/off-chain data/features at mobile/browser level.

![3T Distributed HSM overview drawio (Custom)](https://user-images.githubusercontent.com/4605611/143676701-869ebba4-51ff-49f5-9e3b-97797984d844.png)

- Reseach on other human brain decryption capabilities (like Visual Cryptography, audio cryptography, etc..): the long term Goal is to increase our capabilities to descriminate real humans from bots with IA capabilities. [ Review of the use of human senses and capabilities in cryptography](https://www.sciencedirect.com/science/article/pii/S1574013720304408)

## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Web3 Foundation Website / Medium / Twitter / Element / Announcement by another team / personal recommendation / etc.

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:


- Work you have already done.
- Wheter there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.
