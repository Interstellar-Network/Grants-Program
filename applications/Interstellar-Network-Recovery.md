# Interstellar - New Recovery process


- **Team Name:** Interstellar
- **Payment Address:** Fiat
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2


## Project Overview :page_facing_up:

**Follow-up of Interstellar- Wallet Phase 1**: Link to the application pull request: [w3f/Grants-Program#734](https://github.com/w3f/Grants-Program/pull/734). Amendment: [w3f/Grants-Program#1354](https://github.com/w3f/Grants-Program/pull/1354)

> FOLLOW_UP or NOT?

### Overview

We aim at leveraging the current substrate Recovery pallet to introduce both Cloud Recovery i.e. recovery with a file and an original NFC recovery based on day to day NFC devices, like payment card, earpods, smartwatch, etc... and later dedicated smartcard or NFC devices.

### Project Details

We will use the Substrate Recovery Frame Pallet to manage three recovery processes: Cloud Recovery, NFC Recovery, and Social Recovery.

To streamline the process and avoid modifying the Substrate recovery  pallet, virtual friends i.e item account id related to both recovery file and NFC recovery can be created, they are associated to an NFC device or a cloud recovery file/program token. 

Those account ids matching NFC tags, program recovery files or others items can be managed with a dedicated extended_recovery pallet  withiin TEE/Integritee validators to ensure recovery security and privacy.


The app recovery interface enables the user to manage both recovery setup and recovery initiation, letting the extended_recovery pallet manage create_recovery or initiate_recovery calls based on recovery options chosen by the user. 


#### Circuit File Recovery with extended recovery Pallet.

##### Recovery Setup
1.	Create a [display garbled circuit](https://book.interstellar.gg/VC-GC.html) with an embedded one-time recovery code, encrypted with an AES key.
2.	The program token circuit file is sent to the app to be stored on a cloud service (like Google Drive) or on a local file.
3.	Create an account id associated to the unique program token file.
4.	Call create_recovery on the recovery pallet to set up a recovery account specifying the account id related to the program token. 

>  Multiple program token recovery files can be created to be stored on different cloud services, each associated with an account id.


##### Initiate Recovery
1.	The AES key associated with the program token is received, used to decrypt the recovery token, and displays a one-time recovery code to the user through a validation screen.
2.	The one-time recovery code is received by the Tx Validation pallet, which verifies the code.
3.	From the new account, call initiate_recovery on the extended_recovery pallet.
4.	The old account associated with the app receives a notification to approve or reject the recovery a defined number of times.
5.	If approved or after a defined number of times without responses, with the account id associated with the program token, call vouch_recovery on the recovery pallet.

#### NFC Recovery with extended recovery pallet
##### Recovery Setup
1.	The user taps their NFC device on their phone.
2.	The NFC serial number hashed is transmitted through extrinsic to the extended_recovery pallet.
3.	The serial number hashed is stored.
> Later encrypted with an associated AES key on L1.
4.	Create an item account id associated to the serial number/tag.
5.	Call create_recovery on the recovery pallet to set up a recovery account specifying the account id related to NFC tag.

> Note; A hash is used to ensure pseudonymity of the data to comply with data protection regulation and other legal requirements.

>Multiple NFC devices can be used, each associated with its respective account id for recovery.

##### Initiate Recovery
1.	The user taps their NFC device on their mobile device.
2.	A serial key tag  is sent throuh extrinsic to NFC pallet.
3.	The NFC hashed serial number/tag is retrieved and verified.
> Later retrived encrypted on L1 and decrypted. 
4.	From the new account, call initiate_recovery on the extended_recovery pallet.
5.	The old account associated with the app receives a notification to approve or reject the recovery a defined number of times.
7.	If approved or after a defined number of times without responses, with the account id associated with the program token, call vouch_recovery on the frame recovery pallet.

**Planned future improvement:** a signature generated with a dedicated  NFC smartcard can be used instead of the NFC tag in the future to increase security for power user or corporate/enterprises.

>Such smartcards shipped to the user can also be used to enable multi-signature transactions.

When using payment cards as a NFC devices. Users can complete instead a small transaction with ZKP to ensure the pseudonymity of the user during the recovery set-up and initiation.

#### Social Recovery
We don't include social recovery in the scope of this milestone as it is pretty straitfoward to do it with the current recovery pallet.


#### Finalize the recovery process with pallet recovery.
1.	Once a threshold number of friends/pseudo friends accounts (NFC/Cloud) have vouched for the recovery attempt, the account owner needs to wait until the delay period has passed, starting when they initiated the recovery process.
2.	Now the account owner is able to call claim_recovery, which subsequently allows them to call as_recovered and directly make calls on behalf of the lost account.
3.	Using the now recovered account, the account owner can call close_recovery on the recovery process they opened, reclaiming the recovery deposit they placed.
4.	Then the account owner should then call remove_recovery to remove the recovery configuration on the recovered account and reclaim the recovery configuration deposit they placed.
5.	Using as_recovered, the account owner is able to call any other pallets to clean up their state and reclaim any reserved or locked funds. They can then transfer all funds from the recovered account to the new account.
6.	When the recovered account becomes reaped (i.e. its free and reserved balance drops to zero), the final recovery link is removed.


####  Architecture Overview
##### Recovery Set-up


Bob is the account that create recovery configuration.

![create-2023-10-20-1110](https://github.com/Interstellar-Network/Grants-Program/assets/4605611/669e0b66-fffe-41cb-8c96-0d548c2f112b)




##### Recover Stage

Alice is the new account created on the new mobile device.

![initiate-2023-10-20-1110](https://github.com/Interstellar-Network/Grants-Program/assets/4605611/cfcb76f0-70f3-4d23-bb53-ec5eb8588d57)



#### Technology stack

- VHDL
- C/C++
- Java/Kotlin/Jetpack Compose/Swift/Swift UI
- Rust/Substrate
- IPFS


### Ecosystem Fit

> Should we say something

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

### Milestone 1 — File Recovery

- **Estimated duration:** 4 weeks
- **FTE:** 2.5
- **Costs:** 15,000 USD


|  Number | Deliverable                  | Specification                                                                                                                                                                                                                |
| ------: | ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **0a.** | License                      | APACHE 2                                                                                                                                                                                                                     |
| **0b.** | Documentation                | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up our stack and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide    | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.|  |  |  |
| **0d.** | Docker    |  We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone.    |  |  |  |
|      **1.** | Circuit File Recovery | we will develop a pallet to handle circuit file recovery with a recovery token file based on garbled display circuits |||



### Milestone 2 — NFC Recovery

- **Estimated duration:** 4 weeks
- **FTE:** 2.5
- **Costs:** 15,000 USD


|  Number | Deliverable                  | Specification                                                                                                                                                                                                                |
| ------: | ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **0a.** | License                      | APACHE 2                                                                                                                                                                                                                     |
| **0b.** | Documentation                | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up our stack and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide    | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.                                                              |
   |  |  |  |
 |      **1.** | NFC Recovery | we will develop a pallet to handle NFC recovery with a day to day NFC device |||  


**Additional information:**

For simplicity purpose and to provide a solution that is independent of Interstellar network specificity, we don't create and manage specific accounts related to our specific AA model i.e. related to mobile devices hardware secure element/TEE and its ad hoc key managments.
Instead we will assign exiting accounts to program token and NFC devices.







