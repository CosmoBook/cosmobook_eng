# Gravity Bridge

![](https://img3.teletype.in/files/25/69/2569f548-689e-4733-b6af-97857ab7a2a6.png)

## Gravity Bridge

​​In December 2021, together with more than 100 validators, the Swiss non-profit organization, Interchain Foundation, which manages the Cosmos ecosystem, launched Gravity Bridge, a bridge created by decentralized service provider Althea.

Gravity is a bridge between Ethereum and Cosmos-based blockchains.

First, a high-level overview: Gravity lets users transfer their tokens from Ethereum to Cosmos and back by locking up tokens on the Ethereum side and minting equivalent tokens on the Cosmos side. Unlike many other bridges, Gravity is non-custodial, so you only need to trust in the security of the Cosmos chain, not a third party bridge administrator, who can run off with your funds.

### **Here's how you can use Gravity in a practical example:**

For instance, you send 25 DAI to Gravity's contract on Ethereum, specifying that your address on Cosmos should receive DAI.

Cosmos validators see that this happened and then mint 25 DAI on Cosmos for your addressI. Now your DAI can be sent to other Cosmos accounts, used in Cosmos applications, transferred to other Cosmos networks via IBC, etc.

To return to Ethereum, you send DAI to the Gravity module on the Cosmos chain, specifying that your address on Ethereum should receive it.

The Cosmos validators burn DAI on the Cosmos chain and send an Ethereum transaction causing the Gravity.sol contract to send the 25 DAI to your Ethereum address.

### **How it works**

The Gravity Bridge consists of several components:

* Gravity.sol: an Ethereum smart contract on the Ethereum blockchain
* Gravity Cosmos module: a Cosmos module designed to run on the Cosmos Hub
* Orchestrator: a program that runs on Cosmos validators, monitors the Ethereum chain and submits events that occur on Ethereum to Cosmos as messages
* Relayers: a network of nodes competes for the ability to receive payment for transactions on behalf of the Cosmos validators

<figure><img src="../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

Tokens are locked up on the Ethereum side by sending them to the Gravity.sol smart contract. This triggers an event that can be observed by the validators running the orchestrator. When a quorum of validators agrees that the tokens have been blocked on Ethereum, including the requisite confirmation blocks, a relay is selected to send an instruction to the Cosmos Gravity module, which issues new tokens.

To transfer tokens from the Cosmos hub to the Ethereum blockchain, tokens in the Cosmos network are destroyed and an equal number is released (they were previously deposited) from the Gravity.sol smart contract.

The Cosmos Gravity Bridge is designed to run on the Cosmos Hub. It focuses on maximum simplicity and design efficiency. The bridge can transfer ERC-20 assets created on Ethereum to the Cosmos-based chains and back to Ethereum. Transactions are batched, with transfers netted out. This provides efficiencies at scale and reduces the transaction cost per transfer.

Bridges to Cosmos chain derive their trustworthiness from the degree of trust associated with the Cosmos network to which they connect. Peg-zone validators must maintain a trusted Ethereum node. This is mandatory. This removes all of the trust and game theory issues that typically arise when involving independent relayers. This also significantly simplifies the design.

You can view all the details on the bridge [here](https://www.gravitybridge.net/post/how-gravity-works).&#x20;

Today Gravity Bridge allows to transfer the following tokens:

<figure><img src="../.gitbook/assets/image (36) (1).png" alt=""><figcaption></figcaption></figure>

Gravity is also compatible with any EVM-chain, so a community proposal to implement other tokens from other networks, such as Polygon.

### **Security**

Gravity Bridge was developed with security in mind. The code has been in test networks with a decentralized set of validators for over a year, and has passed three audits: Code4Arena-based, Informal and Least Authority audits.&#x20;

The Althea team (one of the creators of Gravity Bridge) works closely with the Interchain Foundation to support Gravity Bridge renting security from the Cosmos Hub, which will improve Gravity Bridge security with the value of the Cosmos Hub’s staked tokens.

### **$GRAV token**

Cosmos® Gravity Bridge™ was launched with a decentralized set of validators and approximately half of the tokens allocated to the DAO community discretion for airdrops, future ecosystem support and liquidity mining. It is supported by an active and healthy community of token holders and validators, who will make guiding decisions, such as implementation of interchain staking, LM and airdrops.

<figure><img src="../.gitbook/assets/image (20) (1).png" alt=""><figcaption></figcaption></figure>

****[**Statistics**](https://monitor.bronbro.io/d/gravity-stats/gravity-stats?orgId=2\&refresh=5s)**:**&#x20;

<figure><img src="../.gitbook/assets/image (17) (1).png" alt=""><figcaption></figcaption></figure>

### **NFT Bridge**

There are a number of NFT projects being developed or implemented in the Cosmos ecosystem today. Although, much remains to be done before the Cosmos projects get a robust and fully functional NFT protocol. To that end, Gravity Bridge is working closely with one well-known project, Stargaze, to provide an NFT bridge between the Cosmos ecosystem and Ethereum via Gravity Bridge.&#x20;

Thus, while it is currently possible to mint NFTs and even connect EVM/ERC721 NFTs to Cosmos, the standard for transmitting NFT between networks via IBC has not yet been implemented. It severely limits the adoption and use of NFT in the ecosystem.&#x20;

ICS721 is a proposed standardization of Cosmos-based NFTs similar to the ERC721 standard for Ethereum. It was created by the IRISnet development team and describes the requirements needed for NFT cross-chain interaction.&#x20;

Gravity Bridge and Stargaze are currently working together on interoperability between ERC721 and ICS721, and establish a framework and initial test transactions sending ERC721 NFTs across the bridge to Cosmos.

Nevertheless, further work on the ICS721 standard is needed to implement cross-chain, properly utilizate the Cosmos NFTs, and also to send ERC721 NFTs through the Cosmos ecosystem in an interoperable way.&#x20;

For this reason, Gravity Bridge is initiating an NFT ICS721 working group to bring together representatives of NFT projects across the Cosmos ecosystem to strategize and implement the ICS721 standard. Details can be found [here](https://www.gravitybridge.net/post/announcing-the-ics721-workgroup).&#x20;

Also, the [cooperation](https://www.gravitybridge.net/post/irisnet-to-integrate-gravity-bridge-providing-eth-cosmos-liquidity) with IRISnet has been announced.

### **DAO**

Gravity Growth is a multi-organizational management and curatorial concept: a system of checks and balances, that allows to not only ensure smooth operation of infrastructure, but also to prepare it for any storm and carry it into the future (same thing from project to project, but everyone outdo one another).&#x20;

The federated DAO will consist of representatives from the Gravity Grants team and working groups known as Gravity Groups, which manage the GRAV multisig wallet. This multisig is designed to curate and manage Gravity Grants.

Gravity groups can be divided into the following categories:&#x20;

* community development
* marketing
* recruitment and ecosystem growth
* development toolkit
* Cosmos public goods

Instead of a corporation or a board of insiders, each Gravity group or sub-DAO will elect a representative to become a member of Gravity Grants and sign 2/3 multisig. After the original members have served their term, new members must be elected at least once a year, or a special election may be scheduled through the board. These members evaluate the completion of Gravity Grants and release the remaining funds.

<figure><img src="../.gitbook/assets/image (1) (1) (2).png" alt=""><figcaption></figcaption></figure>

### **Airdrop**

On February 9, 2022, the GRAV airdrop was announced and passed by a vote:&#x20;

_Proposal 16_ - Provide 13,750,000 GRAV to the Osmosis community general fund, the use of which will be determined by Osmosis management. In addition, this proposal allocated 1,100,000 GRAV to ION token holders during the Vega upgrade on December 15, 2022 (Snapshot was taken on 12/15/2021).&#x20;

_Proposal 14_ and _Proposal 15_ - to provide 110,000,000 GRAV in total to ATOM stakers who voted on Cosmos Proposal #49, which occurred on June 29, 2021 (Snapshot was taken on 06/29/2021). \~80,000 ATOM addresses were qualified for the airdrop, which means that participants received an average of 1,350 GRAV. The actual number obtained was calculated based on the number of ATOM held at the time of the snapshot.

#### Gravity Bridge roadmap for 2022-2023

* Improved user interface and smoother UX
* ICS721 + NFT bridge implementation
* Closer integration of Evmos
* Multiple EVM-chains support + permanent integration with new projects
* Liquidity for DEX/AMM Increased volume and reduced commissions/time of tx for bridge users

**Links:**

* [GitHub](https://github.com/Gravity-Bridge/Gravity-Docs/blob/main/docs/upgrading.md)
