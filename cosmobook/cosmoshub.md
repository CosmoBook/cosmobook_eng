# CosmosHub

## Cosmos ecosystem and Cosmos Hub

### **What is Cosmos?** <a href="#jkzn" id="jkzn"></a>

Cosmos is not only a blockchain. It is a decentralized network of independent and interoperable blockchains called "zones". The zones are powered by Tendermint Core and communicate with each other via IBC (Inter-Blockchain Communication protocol) using hubs.

#### **Concept**

The Cosmos network operates on three different levels.

1. Network layer. Responsible for the propagation of transactions and consensus-related messages
2. Consensus layer. Arranges nodes according to the validators' decisions to add new transactions
3. Application layer. Responsible for updating the state given a set of transactions, i.e. processing transactions

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

All three layers are combined by toolkits and applications with open source code. For example, Tendermint connects the network layer and the consensus layer in the automatically working and ready-to-use mechanism. Tendermint allows blockchain developers to focus on application development, so they can save their time and resources on the underlying protocol development.

### **Tendermint**

Tendermint is a solution that combines the network and consensus layers of the blockchain into a common engine. This allows developers to focus on application development rather than complex underlying protocol development.

Technically Tendermint can be described as a low-level protocol that performs the functions of the peer-to-peer network protocol. Also, Tendermint is responsible for the consensus algorithm. In addition, it is optimized for solving the problem of fault tolerance of Byzantine generals (i.e. to find consensus) in distributed applications and for processing data in a large number of nodes.

\*_Byzantine fault-tolerance problem (hereinafter BFT) – in a very simplified form, is the problem of finding consensus between nodes, when a certain number of nodes are malicious_

Jae Kwon started working on the creation of the BFT protocol in 2014. The system of hundreds of nodes was supposed to work on this protocol with trustless access and PoS as a security mechanism. In 2018, when all the necessary preparations were made, the Cosmos Network was launched.

Validators are chosen randomly based on their stakes in the total number of coins.

\*\* **** _In short, Tendermint functions as a network layer protocol, allowing nodes to communicate with each other and reach a consensus. The consensus is based on the BFT model, while security is provided by the PoS mechanism. The concept and features of Tendermint operation described_ [_here_](https://blog.cosmos.network/tendermint-explained-bringing-bft-based-pos-to-the-public-blockchain-domain-f22e274a0fdb)_._

Key features of Tendermint that make it competitive:

\
1\. It can be used by both public and private blockchains. If the application determines that validators are selected based on their stake, this is PoS blockchain. But if developers will implement pre-authorization for validators, the blockchain will become private

2\. High performance. Tendermint can handle transaction volume at the rate of 10,000 transactions per second&#x20;

3\. Instant finality. This means that users can be sure that their transactions will be considered completed and final as soon as the block is created&#x20;

4\. Security. If a fork did occur, then there is a way to determine responsibility



<figure><img src="../.gitbook/assets/image (9) (2).png" alt=""><figcaption></figcaption></figure>

Tendermint connects to the application layer using a protocol called the Application Blockchain Interface (ABCI). But creating a secure ABCI application from scratch remains a very hard task. To simplify this task as much as possible, Cosms SDK was developed.

### **CosmosSDK**

Cosmos SDK is an open-source framework for creating permissionless PoS blockchains like Cosmos Hub, or permissioned Proof-of-Authority (PoA) blockchains.

<figure><img src="../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

The Cosmos SDK allows developers to create their own customized blockchains that are compatible with other blockchains in the ecosystem by default, using ready-built modules and toolsets. In doing so, each developer can create a new module and it will be available to all of the other developers.

The advantages of Cosmos SDK:

1. The consensus engine available by default when developing on the Cosmos SDK is Tendermint, currently the best BFT solution.
2. App-chain modules (an app-chain is a blockchain created for an autonomic decentralized application). All modules are in the open access and their number is constantly growing.
3. The Cosmos SDK was created by high-experienced blockchain technology experts. It is a secure and constantly improving environment for blockchain development.

### **Staking**

Staking is the process of locking up a token to secure a public blockchain.

A validator is a node that is responsible for creating blocks, thereby protecting the network and processing transactions. Validators are rewarded for their work, which can consist of block finder rewards, transaction fees, and delegator commissions.

A delegator is any user who has sent (delegated) their tokens to any validator. The proportion of rewards received by delegator depends on the share of tokens, from the total number of tokens of the validator, and pays the validator a small commission for its services (the commission is set by the validator itself and usually does not exceed 5% of the delegator's reward).

To avoid cheating, a validator that publishes incorrect data to the blockchain is penalized financially, losing some of its tokens. It is called slashing.

### **Slashing**

Slashing is a "punishment" for a validator. In this case a predetermined percentage or a fixed quantity of the validator’s stake will be lost. The percentage of penalty depends on the severity of the misbehavior and the threat made to the safety of other network participants.

Slashing is not only a financial incentive for the validators to faithfully carry out their duties, but also a measure that forces them to risk their life and limbs. Meanwhile, since there is a risk of losing some of the tokens, it motivates delegators to choose validators carefully.

Slashing is triggered by two main conditions:

\- **0,01% slashing** can occur if the validator is offline and does not sign operations for too long. Downtime is fixed if the validator does not sign at least 500 blocks out of the last 10,000 blocks.

In addition, in this way a validator is removed from the active validator set and does not receive a block reward for at least for 10 minutes (it is called jail). Once the problems are fixed, the validator can re-join the active validator set by sending an unjail transaction.

![](https://telegra.ph/file/f6a5f216f13d513987a2b.png)

\- **Slashing 5%** can occur if the validator signs two different blocks at the same time. This malfunction is harder to predict, and it is caused from poor operating practices or node operator's malicious intent.

Besides the 5% of tokens, a validator loses the right to offer blocks and receive rewards without the possibility of unlocking (it is being removed from the validator set forever). All delegators receive their tokens back, the unbonding period (i.e. the time of tokens return from staking) is 21 days.

![](https://telegra.ph/file/97e89b3f303117a84a471.png)

### **IBC**

The Inter-Blockchain Communication Protocol or IBC, is a framework that allows zones to cross-chain communication without establishing trust assumptions from a third party (i.e., without using bridges). IBC can be compared to the TCP/IP protocol in traditional networking technologies. Interacting networks agree to trust each other's security model and use a distributed messaging standard to communicate and verify changes in network state. Thus, the IBC model inherits the lowest of the network security, involved in the message exchange (\* meaning that if the security of one network is 10/10 and the other is 8/10, the security of the IBC model will also be 8/10).

The establishment of such an interaction is resource-intensive for both networks. When one network initiates the sending of a message to another network, the public relayer transfers a proof of message request to the other network. The network receiving the message validates this proof using a light client. The light client reads the state of the sending network and writes a copy of this state to its own register. This process of the direct verification guarantees a receiving network that the request is valid. Only after the verification the state of the receiving network changes.

**Due to the optimization towards the security, IBC model has several important features:**

The receiving network is forced to assume that the transaction request has been finalized in the network sending the message (request). Forks and block reorganization, which are common for probabilistic finality (e.g., the Ethereum network), would destroy the basis of the IBC security model. What's why IBC is compatible only with consensus mechanisms having a guarantee of finality, such as Tendermint. While interacting with a probabilistic network, as a solution for a finality threshold set can be used so-called "peg zones". But such a solution complicates the system and creates additional possibilities for the attack.

The IBC model is too expensive for blockchains with a low bandwidth and expensive blocks. But this problem is not related to the Cosmos ecosystem, because IBC was originally developed for blockchains built with Cosmos SDK, where IBC modules work at the network, not at the smart contract level. Moreover, it allows Cosmos networks to redirect the cost and responsibility of recording the state of other networks from applications to the network validators.

Transaction costs for messaging between networks are borne by relayers, not users. Relayers are often managed by validators motivated to keep both (sending and receiving) networks running. The economic model of IBC makes it rational to coordinate between different relayers, so at the same time only one relayer can serve one IBC channel. If there is a situation when none of the relayers serve the channel, the message will be "stuck". Although this fact does not influence the security of both receiving and sending networks, the viability of IBC can be temporarily reduced. IBC messaging can completely stop, if one-third of the validators will stop working.

A scheme of the IBC mechanism is shown in the picture below (source \[here])(https://0xpostman.medium.com/part-2-cross-chain-security-models-compared-c4f91107cad4))

\* _The green arrows show the stages of transaction verification of validator, and the purple ones show the transaction (or any other cross-chain message) path_

![](https://telegra.ph/file/de18cb6908699b3bf74e9.png)

In fact, IBC transactions are information packages that are transferred from one zone to another by Merkle-proofs publishing (more information about Merkle-proofs [here](https://ethereum.org/pt/developers/tutorials/merkle-proofs-for-offline-data-integrity/)) as a proof that the information was sent and received.

In order to verify this proof, the receiving network must be able to keep track of sender's block headers. This mechanism is similar to the mechanism used by sidechains (more info here), which require that two interacting networks know about each other through a bidirectional flow of existence-validating transactions.

The IBC protocol uses two types of transactions: IBCBlockCommitTx , which interacts with the last block hash of any zone, and IBCPacketTx, which contains data about the legitimacy of the information package and the sender's application.

For example, to update a "Zone1" block to "Hub" (or "Hub" to "Zone2"), an IBC BlockCommitTx transaction must be placed on "Hub" with a "Zone1" block hash (or on "Zone2" with a "Hub" block hash). (More information in the [whitepaper](https://v1.cosmos.network/resources/whitepaper#ibcblockcommittx))

![](https://telegra.ph/file/97bd3b1e1bd282435bf2b.png)

To summarize: IBC allows interacting networks to function with each other like read-oracles. The security of this model is resource-intensive, but it allows the networks to interact with each other without a third party. For this reason, IBC is a very popular model always mentioned as an example of one of the alternatives among some other messaging models.

IBC was launched in March 2021, and today (July 2022) it is enabled on 49 networks. Nowadays there are over 2.5M IBC transactions per month (check it out [here](https://www.mapofzones.com/?testnet=false\&period=720\&tableOrderBy=ibcVolume\&tableOrderSort=desc)).

### **Peg zones**

Peg zone is an account-based blockchain that connects zones within Cosmos to external blockchains such as Bitcoin or Ethereum. Cosmos uses deterministic finalization, while Ethereum, for example, is probabilistic, there is a necessity for peg zones.

![](https://telegra.ph/file/1c83c9b2998526787f661.png)

Here are the components used for the interaction with external blockchains:

1. Ethereum smart contracts that act as asset custodians, capable of taking responsibility for their own Ethereum tokens and issuing their own Cosmos tokens.
2. Witness (oracle): The witness component witnesses events in Ethereum. It waits for 100 blocks, the finality threshold, and then implements this pseudo-finality. The witness runs a full Ethereum node to confirm state changes in Ethereum by sending \`WitnessTX' to the peg-zone. A common security model is used here, Cosmos Hub validators also act as witnesses to the peg-zone.
3. Peg-zone is a translator blockchain built on Tendermint. It allows users to execute and request transactions. This is the way Cosmos connects to Ethereum.
4. Authorizing party (signer) signs messages using the secp256k1 scheme. The signer component generates secp256k1 signatures via a SignTx message and sends it to the binding area to relay transactions for verification in the smart contract via the pipeline.
5. Relayer: The relayer component transports an array of transactions signed by the Signer component and sends them to the Ethereum smart contract.

### **Interchain Security (ICS)**

One of the reasons why people argue Polkadot is better than Cosmos is the Shared Security model (more info [here](https://wiki.polkadot.network/docs/learn-security)). In short, all parachains (in Polkadot blockchains are called parachains) are using shared security. Polkadot ensures all the blockchains security and guarantees that any interactions between them are done correctly. The difference between traditional isolated security and shared security is well illustrated in the diagram.

_On the left is the traditional (isolated) security model, which Cosmos has now. On the right is the shared security model of Polkadot, which Cosmos will implement soon._

![](https://telegra.ph/file/8050d53cf4ef190181ea2.png)

At the moment, the block creation in Cosmos is the responsibility of validators for each zone separately, but in the Q3 of 2022 it is planned to introduce Interchain Security. Interchain Security will allow a pool of validators, such as Cosmos Hub, to create blocks for a new zone. The mechanisms of penalties for downtime or double signing remain as for the "donor" hub, and an attack on the blockchain becomes economically inexpedient. Also, it is really important that IBC will be used for Shared Security, and ICS is not required for each zone.

\
Although the introduction of the technology has already been announced, there are no details yet. The only thing that is known is known, the first version will use all donor-chain validators, and later the possibility of partial donation will be implemented. Read more[ here](https://github.com/cosmos/gaia/blob/main/docs/interchain-security.md).

### **Cosmos Hub**

To avoid the process of connecting each new blockchain to all existing ones directly through an IBC, Cosmos offers a modular architecture. There are regular heterogeneous blockchains - zones, as well as hubs - blockchains, specifically designed to connect to each other.

The first hub launched on Cosmos Network was Cosmos Hub. Cosmos Hub is a Proof-of-Stake general-purpose blockchain whose native token is called ATOM.

Cosmos Hub is the central ledger, so tokens can be directly sent between zones via the IBC protocol. Cosmos Hub is the central blockchain of the Cosmos ecosystem. In fact, it is the place where the entire ecosystem has started.

![](https://telegra.ph/file/bd28480cc4a5b3e2843e3.png)

The picture source [here](https://mapofzones.com/?period=720\&testnet=false\&tableOrderBy=ibcVolume\&tableOrderSort=desc\&zone=cosmoshub-4\&fullscreen=true)

Development began in 2014, the Cosmos concept appeared in 2016, and on March 13, 2019 Cosmos Hub went live ([here](https://www.youtube.com/watch?v=OALEhpn7ccM) is the recording of the launch broadcast)

![](https://telegra.ph/file/79404f91631c8ae87a048.png)

The Cosmos network's native coin is Atom.&#x20;

It has three main use cases:&#x20;

1. Payment for transaction fees;&#x20;
2. Cosmos Hub governance;&#x20;
3. Staking;

ATOM tokens were distributed in the seed-round (5%), 10% went to Tendermint Inc. and 75% went in 30 minutes during the initial coin offering (ICO) in 2017. The cost of 1 Atom was 10 cents, the annual proceeds was 17 million.&#x20;

At the moment the total supply is 302,347,059 ATOM. Due to the fact that Tendermint Core rewards are paid to stakers with new coins, the maximum supply is unlimited. At the same time, the inflation rate is adjusted in real time depending on the amount of coins in the staking and the number of stakers. At the time of writing, it was 12.4%. You can find the current information in Bro'n'Bro [dashboard](https://monitor.bronbro.io/d/cosmos-stats/cosmos-stats?orgId=2\&refresh=5s).

### **Links:**

Cosmos whitepaper: [here](https://v1.cosmos.network/resources/whitepaper)

Tendermint: [here](https://docs.tendermint.com/)

IBC: [here](https://ibc.cosmos.network/)

Peg zones: [here](https://blog.cosmos.network/the-internet-of-blockchains-how-cosmos-does-interoperability-starting-with-the-ethereum-peg-zone-8744d4d2bc3f)

About slashing: [here ](https://medium.com/p2peconomy/slashing-in-cosmos-network-bbbaff949ee5)and [here](https://docs.cosmos.network/master/modules/slashing/)

### Wallets and dashboards in Cosmos ecosystem <a href="#yine" id="yine"></a>

#### **Wallets**

Crypto wallets store your private keys and give you access to your own assets. There are many different types of crypto wallets, from mobile apps and web wallets to hardware wallets.

#### **Keplr**

![](https://telegra.ph/file/83bf46d303d26af59b14a.png)

Keplr has quickly become one of the main wallets for the Cosmos ecosystem, and staking with Keplr wallet and dashboards is really easy (full [guide](https://antropocosmist.medium.com/%D0%BA%D0%B0%D0%BA-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D1%8C%D1%81%D1%8F-%D0%BA%D0%BE%D1%88%D0%B5%D0%BB%D1%8C%D0%BA%D0%BE%D0%BC-keplr-462d430615b3)). Keplr offers a mobile wallet app for iOS and Android, as well as a browser extension similar to Metamask, which is the easiest way to staking safely. In addition to the browser extension, Keplr provides a simple [monitoring dashboard ](https://wallet.keplr.app/)to view available tokens, the balance of staked coins and rewards across 20+ networks. Cosmos chains can also integrate a dashboard [staking management](https://wallet.keplr.app/#/dashboard), so users can stake tokens in their own ecosystems.

According to Keplr 2022 roadmap, Keplr is planning several interface improvements that will make the interface even better. For example, one of the upcoming improvements is the "Validators" section.According to Keplr's 2022 roadmap, Keplr is planning several interface improvements that will make the interface even better. For example, one of the upcoming improvements is the "Validators" section.

When you are the Cosmos newcomer, It is very important to choose a right validator. Keplr aims to help validators from the active set get a significant vote. The team plans to reach this goal by updating the validator page and providing detailed descriptions that will make it easier for users (potential delegators) to choose the right validator. Also communication between validators and delegators will be possible. It should encourage validators and delegators to work together. You can find various staking resources on [Keplr](https://keplr.crunch.help/).

You can also connect your Ledger following these [guide](https://support.ledger.com/hc/ru/articles/4411149814417-%D0%9A%D0%B0%D0%BA-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-Keplr-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-%D1%81%D0%BE-%D1%81%D1%87%D0%B5%D1%82%D0%B0%D0%BC%D0%B8-Cosmos-ATOM-%D0%B2-Ledger?docs=truehttps://support.ledger.com/hc/ru/articles/4411149814417-%D0%9A%D0%B0%D0%BA-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-Keplr-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-%D1%81%D0%BE-%D1%81%D1%87%D0%B5%D1%82%D0%B0%D0%BC%D0%B8-Cosmos-ATOM-%D0%B2-Ledger?docs=true).

#### **Cosmostation**

![](https://telegra.ph/file/6a6f2c24f559dc9f894ae.png)

Cosmostation is a solution providing a mobile wallet for convenient staking just within your mobile phone, as well as a web wallet that allows you to connect and sign transactions from your hardware wallet. As a longtime investor in the Cosmos ecosystem, Cosmostation has earned a solid reputation for providing excellent end-user support with proven products such as Cosmos explorer Mintscan. Cosmostation also supports over 30 networks and provides users a wide range of use cases.

Also Cosmostation has many guides and support resources, which can help users. A video tutorial on how to set up a mobile wallet is here. For example, here you can watch the staking guide.

When you are considering different validators, you can see their history, activity and uptime right in the validators section on Mintscan. Here are some video tutorials that can help you to choose a validator: here and here.

\
Cosmostation will be launching a browser extension this year. To start staking through your mobile wallet, download [Cosmostation for Android](https://play.google.com/store/apps/details?id=wannabit.io.cosmostaion) or [iOS here](https://play.google.com/store/apps/details?id=wannabit.io.cosmostaion).
