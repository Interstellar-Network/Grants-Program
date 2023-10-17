# Interstellar - Wallet Phase 2 (amended)


- **Team Name:** Interstellar
- **Payment Address:** Fiat 04.04.2023, 22:42
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2


## Project Overview :page_facing_up:

**Follow-up of Interstellar- Wallet Phase 1**: Link to the application pull request: [w3f/Grants-Program#734](https://github.com/w3f/Grants-Program/pull/734). Amendment: [w3f/Grants-Program#1354](https://github.com/w3f/Grants-Program/pull/1354)

### Overview



### Project Details

Interstellar Account Recovery
Interstellar uses the Substrate Recovery Frame Pallet to manage three recovery processes: Cloud Recovery, NFC Recovery, and Social Recovery.
To streamline the process and avoid modifying the Substrate Recovery Frame Pallet, 0xwhisker.hashnode.dev., ad-hoc accounts related to both Cloud Recovery and NFC Recovery can be created to represent virtual friends associated   to an NFC device or a cloud recovery file/program token. Those virtual friends accounts can be managed with both cloud and NFC pallets off-chain in TEE/Integritee workers to ensure recovery security.
Recovery Set-up/configuration

Alice is the account that create recovery configuration.
 

![image](https://github.com/Interstellar-Network/Grants-Program/assets/4605611/fda0a693-ee89-4581-a340-08cb96b484cc)


Recover Stage

Bob is the new account created on the new mobile device.

 ![image](https://github.com/Interstellar-Network/Grants-Program/assets/4605611/e922726b-150c-4bf9-8cb6-9c99b5702c31)



Mobile Account (not use for the grant)
When users create a new app, a new mobile account is created with a new public/private key pair is created on mobile secure element and associated with the user. On this respect a specific pallet will be created to handle the mobile signature scheme as well as a specific extrinsic with signed extension to be associated to the mobile account key pair and an SR 25519 address derived from the mobile public key.
Note: discuss if we want that for the grant or postpone it for later or associate mobile to classic substrate account.
The app recovery interface enables the user to manage both recovery setup and recovery initiation, letting the respective pallet manage create_recovery or initiate_recovery calls based on recovery option chosen by the user. 
Cloud Recovery with Cloud Pallet
Recovery Setup
1.	Create a display garbled circuit Visual Cryptography Display - Interstellar Book with an embedded one-time recovery code, encrypted with an AES key.
2.	The program token recovery file is sent to the app to be stored on a cloud service (like Google Drive) or on a local file.
3.	Create an ad-hoc account matching the unique program token file.
4.	Call create_recovery on the recovery pallet to set up a recovery account specifying the ad hoc account. 
Note: Multiple program token recovery files can be created to be stored on different cloud services, each associated with an ad hoc account.
Initiate Recovery
1.	The AES key associated with the program token is received, used to decrypt the recovery token, and displays a one-time recovery code to the user through a validation screen.
2.	The one-time recovery code is received by the Tx Validation pallet, which verifies the code.
3.	From the new account, call initiate_recovery on the frame recovery pallet.
4.	The old account associated with the app receives a notification to approve or reject the recovery a defined number of times.
5.	If approved or after a defined number of times without responses, from the account associated with the program token, call vouch_recovery on the frame recovery pallet releases.parity.io.
NFC Recovery with NFC Pallet
Recovery Setup
1.	The user taps their NFC device on their phone.
2.	The NFC serial number hashed is signed with the mobile private key and sent to the NFC pallet.
3.	The signature is verified, and the serial number hashed is encrypted with an associated AES key on L1.
4.	Create an ad hoc account matching the serial number.
5.	Call create_recovery on the recovery pallet to set up a recovery account specifying the ad hoc account releases.parity.io.
Note; A hash is used to ensure pseudonymity of the data to comply with data protection and other legal requirements.
Note: Multiple NFC devices can be used, each associated with an ad hoc account for recovery.

Initiate Recovery
1.	The user taps their NFC device on their mobile device.
2.	A serial key is received, signed with the mobile private key.
3.	Transaction validation/sensitive operation confirmation is performed and verified
4.	The encrypted NFC hashed serial number is retrieved on L1, decrypted with the AES key, and verified.
5.	From the new account, call initiate_recovery on the frame recovery pallet.
6.	The old account associated with the app receives a notification to approve or reject the recovery a defined number of times.
7.	If approved or after a defined number of times without responses, from the account associated with the program token, call vouch_recovery on the frame recovery pallet releases.parity.io.

Future: a dedicated NFC smartcard signature can be used instead of the NFC tag in the future to increase security for power user or corporate/enterprises. Such smartcards shipped to the user can also be used to enable multi-signature transactions.
When using payment cards as a NFC devices. Users can complete instead a small transaction protected with ZKP to ensure the pseudonymity of the user during the recovery set-up and initiation.

Social Recovery
Social Recovery involves authorization from friends' apps with TX Validation, sensitive recovery approval with our app. and a special case: Parity signer. 
Note: can we postpone social recovery to implement mobile account instead?

Finalize the recovery process with pallet recovery.
1.	Once a threshold number of friends/pseudo friends accounts (NFC/Cloud) have vouched for the recovery attempt, the account owner needs to wait until the delay period has passed, starting when they initiated the recovery process.
2.	Now the account owner is able to call claim_recovery, which subsequently allows them to call as_recovered and directly make calls on behalf of the lost account.
3.	Using the now recovered account, the account owner can call close_recovery on the recovery process they opened, reclaiming the recovery deposit they placed.
4.	Then the account owner should then call remove_recovery to remove the recovery configuration on the recovered account and reclaim the recovery configuration deposit they placed.
5.	Using as_recovered, the account owner is able to call any other pallets to clean up their state and reclaim any reserved or locked funds. They can then transfer all funds from the recovered account to the new account.
6.	When the recovered account becomes reaped (i.e. its free and reserved balance drops to zero), the final recovery link is removed.



####  Architecture Overview
![Architecture overview](https://book.interstellar.gg/fig/Architecture-mobile-L1-L2-Signers.svg "architecture L1 L2 signer")
#### TTVP Detailed
![TTVP Detailed](https://book.interstellar.gg/fig/Transaction_Validation_Module.svg "TTVP detailed")


#### Technology stack

- VHDL
- C/C++
- Java/Kotlin/Jetpack Compose/Swift/Swift UI
- gRPC
- Rust/Substrate
- IPFS


### Ecosystem Fit

At parisDOT<sup>.comm</sup> we had a fantastic opportunity to present our project to the leading teams in the Polkadot Parachain community. And the feedback we received was nothing short of extraordinary. Our solution, which aims to provide both hardware security and user-friendliness in a wallet solution, struck a chord with the teams.

Their positive response is a testament to the importance of a solution that addresses this critical need in the Polkadot ecosystem and beyond. The teams were not only impressed with our solution, but they were also eager to put it to the test as soon as it becomes available.

This is a major market fit milestone for us, and we're thrilled to have the support of such influential players in the Polkadot community. We're dedicated to delivering a solution that meets their expectations and contributes to the continued growth and success of the Polkadot ecosystem.

We are in active conversations with some of the teams we met there, and continuously have new discussions with new teams also beyond the Polkadot ecosystem. So far, everyone is impressed and enthusiastic about the solution.


## Team :busts_in_silhouette:


### Team members
- Name of team leader:
- Jean-Luc Leleu
- Names of team members:
- Nathan Prat
- Eliot Leleu

- Philippe Salats (advisor)

### Contact

- **Contact Name:** Jean-Luc Leleu
- **Contact Email:** jll@interstellar.gg
- **Website:** <https://www.interstellar.gg/>


### Legal Structure

- **Registered Address:** 61 rue de Lyon, Paris, France
- **Registered Legal Entity:** Interstellar SAS

### Team's experience
We are now multiple security and fintech entrepreneurs, security researchers, patents fillers who turned open-source developers and blockchain enthusiasts.


### Team Code Repos

- <https://github.com/Interstellar-Network>

- <https://github.com/nathanprat>

### Team LinkedIn Profiles (if available)

- <https://www.linkedin.com/in/jlleleu/> Jean-Luc Leleu

- <https://www.linkedin.com/in/nathan-prat/> Nathan Part

- <https://www.linkedin.com/in/eliotjfl/> Eliot Leleu


- <https://www.linkedin.com/in/philippesalats/> Philippe Salats (advisor)


## Development Roadmap :nut_and_bolt:

### Overview

- **Total Estimated Duration:** 2 months
- **Full-Time Equivalent (FTE):** 2.5
- **Total Costs:** 30,000 USD

### Milestone 1 — New Garbling scheme

- **Estimated duration:** 4 weeks
- **FTE:** 2.5
- **Costs:** 15,000 USD


|  Number | Deliverable                  | Specification                                                                                                                                                                                                                |
| ------: | ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **0a.** | License                      | APACHE 2                                                                                                                                                                                                                     |
| **0b.** | Documentation                | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up our stack and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide    | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.|  |  |  |
|      1. | Garble Circuit pallet update | We will rewrite the garbled circuit evaluation scheme to target at least **60 fps**  through parralelization, caching and likely with an efficient [1.permutation-based garbling scheme: see 4.5](https://www.cs.fsu.edu/~tvhoang/thesis.pdf) optimized for performance or a [2.new garbling scheme](https://www.esat.kuleuven.be/cosic/publications/article-3351.pdf) that could potentially require lower computation cost per gate|




### Milestone 2 — Circuit design optimization and light security screen

- **Estimated duration:** 4 weeks
- **FTE:** 2.5
- **Costs:** 15,000 USD


|  Number | Deliverable                  | Specification                                                                                                                                                                                                                |
| ------: | ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **0a.** | License                      | APACHE 2                                                                                                                                                                                                                     |
| **0b.** | Documentation                | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up our stack and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide    | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.                                                              |
   |  |  |  |
|      1. | Display Circuit update       | We will modify the current display circuit to enable a more comfortable user experience by decreasing the cognitive load needed for the user to read the screen. - likely by adding specific sub-circuits to manage a set of probabilities of displaying segments for each frame, then fine tuned segments ON/OFF per frame to improve readbility
|      2. | Light security screen     | We will provide a less secure but very comfortable to read secure screen version using fading with less blinking (link)  - this  non-screenshot proof version will be used later with our adaptive security framework                                                                      |

**Additional information (reason for amendment):**

As we prioritize the user experience and aim to showcase the FPS improvement and overall viusal improvement for the user compared to the previous milestone, there is no need for a Docker here. Instead, we provide an offline demo app to simplify the evaluation.

However, if you'd like to test the full pipeline for this milestone, we can provide you with both a Docker and an online version of the app and the related demo tutorial.








