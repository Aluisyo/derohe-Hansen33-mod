### Welcome to the DEROHE - Hansen33 Mod

If you don't alredy know DERO - Check out [DEROHE Git Repo](https://github.com/deroproject/derohe)

* This is NOT the official release of DERO. This version is a modified version of DERO.
* If all your minis get lost or your computer blows up, it's no my fault, you installed this.

* This modded DERO version is powering DERO Community Pools and it's related services.
  * DERO Community Pools - https://community-pools.mysrv.cloud/
  * DERO API - https://dero-api.mysrv.cloud/

### What is Hansen33 Mod?

* A community driven fork of the offical DEROHE Suite (daemon, miner and wallet) which has additional features and functionality.

<<<<<<< HEAD
### Changes from official release includes (but not limited to)
=======
**DERO is pleased to announce release of DERO Homomorphic Encryption Protocol testnet.** 
DERO will migrate from existing CryptoNote Protocol to its own DERO Homomorphic Encryption Blockchain Protocol(DHEBP).
>>>>>>> official

* Many Mining and Network stats
* Live TX, Blocks, Orphans and Node Connectiviy Tracking (Eye Candy)
* Running Node Config Changes
* Enhanced debug features
* Anti-Cheat Mining Feature, Miniblock and TX Spam Mitigation
* Many new command (check `help` and `config` for more info)
* Wallet has TOR & SOCKS5 Support. Default remote host is https://dero-api.mysrv.cloud/ (SSL Encrypted)
* Miner's default node is DERO Community Pools at `community-pools.mysrv.cloud:10300`

### Screen Shots

![Hansen33Mod](https://dero-api.mysrv.cloud/images/hansenmod-start.png)
![Active Miners](https://dero-api.mysrv.cloud/images/active_miners_cli.png)

## Installation

* Hansen33 Mod is 100% compatible with official DERO, so you can safely use same data directory.
* Download binary from release page or compile from source.
* Replace Official binary file (make backup first)

* Send feature requests to hansen33#2541 on Discord

### Build Instructions

Run following commands to build,
```
git clone https://github.com/Hansen333/derohe-Hansen33-mod.git
cd derohe-Hansen33-mod
bash build_all.sh
```

## Developers

 * @Hansen33
   * Address: dero1qy07h9mk6xxf2k4x0ymdpezvksjy0talskhpvqmat3xk3d9wczg5jqqvwl0sn
 * @mmarcel
   * Address: dero1qydkj6dznyk5njmzr96hjcr5uj74anqqqv90mg39mtzm4d2dcpwsqqqk6zvve

<<<<<<< HEAD
=======
6. No more chain scanning  or wallet scanning to detect funds, no key images etc.

7. Truly light weight and efficient wallets.

8. Fixed per account cost of  66 bytes in blockchain[Immense scalability].

9. Perfectly anonymous transactions with many-out-of-many proofs [bulletproofs and sigma protocol]

10. Deniability

11. Fixed transaction size say  ~2.5KB (ring size 8) or ~3.4 KB (ring size 16) etc based on chosen anonymity group size[ logarithmic growth]

12. Anonymity group can be chosen in powers of 2.

13. Allows homomorphic assets ( programmable SCs with fixed overhead per asset ), with open Smart Contract but encrypted data [Internal testing/implementation not on this current testnet branch].

14. Allows open assets ( programmable SCs with fixed overhead per asset ) [Internal testing/implementation not on this current testnet branch]

15. Allows chain pruning on daemons to control growth of data on daemons. 

16. Transaction generation takes less than 25 ms.

17. Transaction verification takes even less than 25ms time.

18. No trusted setup, no hidden parameters.

19. Pruning chain/history for immense scalibility[while still secured using merkle proofs].

20. Example disk  requirements of 1 billion accounts ( assuming it does not want to keep history of transactions, but keeps proofs to prove that the node is in sync with all other nodes)
    
    ```
    Requirement of 1 account = 66 bytes
    Assuming storage overhead per account of 128 bytes ( constant )
    Total requirements = (66 + 128)GB ~ 200GB
    Assuming we are off by factor of 4 = 800GB
    ```

21. Note that, Even after 1 trillion transactions, 1 billion accounts will consume 800GB only, If history is not maintained, and everything still will be in proved state using merkle roots.
    And so, Even Raspberry Pi can host the entire chain.

22. Senders can prove to receiver what amount they have send (without revealing themselves).

23. Worlds first Erasure Coded Propagation protocol, which allows 100x block size without increasing propagation delays.

24. Entire chain is rsyncable while in operation.

25. Testnet released with source code.

#### DERO HE TX Sizes

| Ring Size | DEROHE TX Size |
| --------- | -------------- |
| 2         | 1553 bytes     |
| 4         | 2013 bytes     |
| 8         | 2605 bytes     |
| 16        | 3461 bytes     |
| 32        | 4825 bytes     |
| 64        | 7285 bytes     |
| 128       | 11839 bytes    |
| 512       | ~35000 bytes   |

**NB:** Plan to reduce TX sizes further.  

#### DERO Crypto

&nbsp; &nbsp; &nbsp; &nbsp; Secure and fast crypto is the basic necessity of this project and adequate amount of time has been devoted to develop/study/implement/audit it. Most of the crypto such as ring signatures have been studied by various researchers and are in production by number of projects. As far as the Bulletproofs are considered, since DERO is the first one to implement/deploy, they have been given a more detailed look. First, a bare bones bulletproofs was implemented, then implementations in development were studied (Benedict Bunz, XMR, Dalek Bulletproofs) and thus improving our own implementation.  
&nbsp; &nbsp; &nbsp; &nbsp; Some new improvements were discovered and implemented (There are number of other improvements which are not explained here). Major improvements are in the Double-Base Double-Scalar Multiplication while validating bulletproofs. A typical bulletproof takes ~15-17 ms to verify. Optimised bulletproofs takes ~1 to ~2 ms(simple bulletproof, no aggregate/batching). Since, in the case of bulletproofs the bases are fixed, we can use precompute table to convert 64*2 Base Scalar multiplication into doublings and additions (NOTE: We do not use Bos-Coster/Pippienger methods). This time can be again easily decreased to .5 ms with some more optimizations. With batching and aggregation, 5000 range-proofs (~2500 TX) can be easily verified on even a laptop. The implementation for bulletproofs is in github.com/deroproject/derosuite/crypto/ringct/bulletproof.go , optimized version is in github.com/deroproject/derosuite/crypto/ringct/bulletproof_ultrafast.go

&nbsp; &nbsp; &nbsp; &nbsp; There are other optimizations such as base-scalar multiplication could be done in less than a microsecond. Some of these optimizations are not yet deployed and may be deployed at a later stage.  

#### DEROHE PORTS

**Mainnet:**  
P2P Default Port: 10101  
RPC Default Port: 10102  
Wallet RPC Default Port: 10103  

**Testnet:**  
P2P Default Port: 40401  
RPC Default Port: 40402  
Wallet RPC Default Port: 40403  

#### Technical

&nbsp; &nbsp; &nbsp; &nbsp; For specific details of current DERO core (daemon) implementation and capabilities, see below:  

1. **DAG:** No orphan blocks, No soft-forks.
2. **BulletProofs:** Zero Knowledge range-proofs(NIZK)
3. **AstroBWT:** This is memory-bound algorithm. This provides assurance that all miners are equal. ( No miner has any advantage over common miners).
4. **P2P Protocol:** This layer controls exchange of blocks, transactions and blockchain itself.
5. **Pederson Commitment:** (Part of ring confidential transactions): Pederson commitment algorithm is a cryptographic primitive that allows user to commit to a chosen value  while keeping it hidden to others. Pederson commitment  is used to hide all amounts without revealing the actual amount. It is a homomorphic commitment scheme.
6. **Homomorphic Encryption:** Homomorphic Encryption is used to do operations such as addition/substraction to settle balances with data being always encrypted (Balances are never decrypted before/during/after operations in any form.).
7. **Homomorphic Ring Confidential Transactions:** Gives untraceability , privacy and fungibility while making sure that the system is stable and secure.
8. **Core-Consensus Protocol implemented:** Consensus protocol serves 2 major purposes
   1. Protects the system from adversaries and protects it from forking and tampering.
   2. Next block in the chain is the one and only correct version of truth ( balances).
9. **Proof-of-Work(PoW) algorithm:**  PoW part of core consensus protocol which is used to cryptographically prove that X amount of work has been done to successfully find a block.
10. **Difficulty algorithm**: Difficulty algorithm controls the system so as blocks are found roughly at the same speed, irrespective of the number and amount of mining power deployed.
11. **Serialization/De-serialization of blocks**: Capability to encode/decode/process blocks .
12. **Serialization/De-serialization of transactions**: Capability to encode/decode/process transactions.
13. **Transaction validity and verification**: Any transactions flowing within the DERO network are validated, verified.
14. **Socks proxy:** Socks proxy has been implemented and integrated within the daemon to decrease user identifiability and improve user anonymity.
15. **Interactive daemon** can print blocks, txs, even entire blockchain from within the daemon 
16. **status, diff, print_bc, print_block, print_tx** and several other commands implemented
17. GO DERO Daemon has both mainnet, testnet support.
18. **Enhanced Reliability, Privacy, Security, Useability, Portability assured.**

#### DERO blockchain salient features

- [DAG Based: No orphan blocks, No soft-forks.](#dero-dag)
- [51% Attack resistant.](#51-attack-resistant) 
- 60 Second Block time.
- Extremely fast transactions with one minute/block confirmation time.
- SSL/TLS P2P Network.
- Homomorphic: Fully Encrypted Blockchain
- [Dero Fastest Rocket BulletProofs](#dero-rocket-bulletproofs): Zero Knowledge range-proofs(NIZK). 
- Ring signatures.
- Fully Auditable Supply.
- DERO blockchain is written from scratch in Golang. [See all unique blockchains from scratch.](https://twitter.com/cryptic_monk/status/999227961059528704) 
- Developed and maintained by original developers.

#### DERO Innovations

&nbsp; &nbsp; &nbsp; &nbsp; Following are DERO first and leading innovations.

#### DERO DAG

&nbsp; &nbsp; &nbsp; &nbsp; DERO DAG implementation builds outs a main chain from the DAG network of blocks which refers to main blocks (100% reward) and side blocks (8% rewards).  

![DERO DAG stats.dero.io](https://raw.githubusercontent.com/deroproject/documentation/master/images/Dag1.jpeg)  
*DERO DAG Screenshot* [Live](https://stats.dero.io/)  

![DERO DAG network.dero.io](https://raw.githubusercontent.com/deroproject/documentation/master/images/dagx4.png)  
*DERO DAG Screenshot* [Live](https://network.dero.io/)  

#### **Erasure Coded Blocks**

        Traditional Blockchains process blocks as single unit of computation(if a double-spend tx occurs within the block, entire block is rejected). As soon as a block is found, it is sent to all its peers.DERO blockchain erasure codes the block into 48 chunks, dispersing and chunks are dispersed to peers randomly.Any peer receiving any 16 chunks( from 48 chunks) can regenerate the block and thus lower overheads and lower propagation time.

#### Client Protocol

&nbsp; &nbsp; &nbsp; &nbsp; Traditional Blockchains process blocks as single unit of computation(if a double-spend tx occurs within the block, entire block is rejected). However DERO network accepts such blocks since DERO blockchain considers transaction as a single unit of computation.DERO blocks may contain duplicate or double-spend transactions which are filtered by client protocol and ignored by the network. DERO DAG processes transactions atomically one transaction at a time.

#### DERO Rocket Bulletproofs

- Dero ultrafast bulletproofs optimization techniques in the form used did not exist anywhere in publicly available cryptography literature at the time of implementation. Please contact for any source/reference to include here if it exists.  Ultrafast optimizations verifies Dero bulletproofs 10 times faster than other/original bulletproof implementations. See: https://github.com/deroproject/derosuite/blob/master/crypto/ringct/bulletproof_ultrafast.go

- DERO rocket bulletproof implementations are hardened, which protects DERO from certain class of attacks.  

- DERO rocket bulletproof transactions structures are not compatible with other implementations.

&nbsp; &nbsp; &nbsp; &nbsp; Also there are several optimizations planned in near future in Dero rocket bulletproofs which will lead to several times performance boost. Presently they are under study for bugs, verifications, compatibility etc.

#### 51% Attack Resistant

&nbsp; &nbsp; &nbsp; &nbsp; DERO DAG implementation builds outs a main chain from the DAG network of blocks which refers to main blocks (100% reward) and side blocks (8% rewards). Side blocks contribute to chain PoW security and thus traditional 51% attacks are not possible on DERO network. If DERO network finds another block at the same height, instead of choosing one, DERO includes both blocks. Thus, rendering the 51% attack futile.

#### DERO Mining

[Mining](https://github.com/deroproject/wiki/wiki/Mining)  

#### DERO Installation

&nbsp; &nbsp; &nbsp; &nbsp; DERO is written in golang and very easy to install both from source and binary. 

#### Installation From Source

1. Install Golang, Golang version 1.12.12 required.  
2. In go workspace: ```go get -u github.com/deroproject/derohe/...```  
3. Check go workspace bin folder for binaries. 
4. For example on Linux machine following binaries will be created:
   1. derod-linux-amd64 -> DERO daemon.  
   2. dero-wallet-cli-linux-amd64 -> DERO cmdline wallet.  
   3. explorer-linux-amd64 -> DERO Explorer. Yes, DERO has prebuilt personal explorer also for advanced privacy users.

#### Installation From Binary

&nbsp; &nbsp; &nbsp; &nbsp; Download [DERO binaries](https://github.com/deroproject/derosuite/releases) for ARM, INTEL, MAC platform and Windows, Mac, FreeBSD, OpenBSD, Linux etc. operating systems.  
Most users required following binaries:  
[Windows 7-10, Server 64bit/amd64 ](https://github.com/deroproject/derosuite/releases/download/v2.1.6-1/dero_windows_amd64_2.1.6-1.alpha.atlantis.07032019.zip)  
[Windows 32bit/x86/386](https://github.com/deroproject/derosuite/releases/download/v2.1.6-1/dero_windows_x86_2.1.6-1.alpha.atlantis.07032019.zip)  
[Linux 64bit/amd64](https://github.com/deroproject/derosuite/releases/download/v2.1.6-1/dero_linux_amd64_2.1.6-1.alpha.atlantis.07032019.tar.gz)  
[Linux 32bit/x86](https://github.com/deroproject/derosuite/releases/download/v2.1.6-1/dero_linux_386_2.1.6-1.alpha.atlantis.07032019.tar.gz)  
[FreeBSD 64bit/amd64](https://github.com/deroproject/derosuite/releases/download/v2.1.6-1/dero_freebsd_amd64_2.1.6-1.alpha.atlantis.07032019.tar.gz)  
[OpenBSD 64bit/amd64](https://github.com/deroproject/derosuite/releases/download/v2.1.6-1/dero_openbsd_amd64_2.1.6-1.alpha.atlantis.07032019.tar.gz)  
[Mac OS](https://github.com/deroproject/derosuite/releases/download/v2.1.6-1/dero_apple_mac_darwin_amd64_2.1.6-1.alpha.atlantis.07032019.tar.gz)  
Contact for support of other hardware and OS.  

#### Next Step After DERO Installation

&nbsp; &nbsp; &nbsp; &nbsp; Running DERO daemon supports DERO network and shows your support to privacy.  

#### Running DERO Daemon

&nbsp; &nbsp; &nbsp; &nbsp; Run derod.exe or derod-linux-amd64 depending on your operating system. It will start syncing.

1. DERO daemon core cryptography is highly optimized and fast. 
2. Use dedicated machine and SSD for best results.  
3. VPS with 2-4 Cores, 4GB RAM,15GB disk is recommended.  

![DERO Daemon](https://raw.githubusercontent.com/deroproject/documentation/master/images/derod1.png)  
*DERO Daemon Screenshot*

#### Running DERO Wallet

Dero cmdline wallet is most reliable and has support of all functions. Cmdline wallet is most secure and reliable.

#### DERO Cmdline Wallet

&nbsp; &nbsp; &nbsp; &nbsp; DERO cmdline wallet is menu based and very easy to operate. 
Use various options to create, recover, transfer balance etc.  
**NOTE:** DERO cmdline wallet by default connects DERO daemon running on local machine on port 20206.  
If DERO daemon is not running start DERO wallet with --remote option like following:  
**./dero-wallet-cli-linux-amd64 --remote** 

![DERO Wallet](https://raw.githubusercontent.com/deroproject/documentation/master/images/wallet-recover2.png)  
*DERO Cmdline Wallet Screenshot*  

#### DERO Explorer

[DERO Explorer](https://explorer.dero.io/) is used to check and confirm transaction  on DERO Network.  
[DERO testnet Explorer](https://testnetexplorer.dero.io/) is used to check and confirm transaction  on DERO Network.  
DERO users can run their own explorer on local machine and can [browse](http://127.0.0.1:8080) on local machine port 8080.  
![DERO Explorer](https://github.com/deroproject/documentation/raw/master/images/dero_explorer.png)
*DERO EXPLORER Screenshot*  

#### Proving DERO Transactions

DERO blockchain is completely private, so anyone cannot view, confirm, verify any other's wallet balance or any transactions. 
So to prove any transaction you require *TXID* and *deroproof*.  
deroproof can be obtained using get_tx_key command in dero-wallet-cli.  
Enter the *TXID* and *deroproof* in [DERO EXPLORER](https://testnetexplorer.dero.io)  
![DERO Explorer Proving Transaction](https://github.com/deroproject/documentation/raw/master/images/explorer-prove-tx.png)
*DERO Explorer Proving Transaction*  
>>>>>>> official
