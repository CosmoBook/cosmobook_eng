# Sifchain

![](https://img4.teletype.in/files/3c/2c/3c2c61bb-beac-45a2-b742-0b58f315f921.png)

## Sifchain

According to the Sifchain team statement, "Sifchain is committed to creating a blockchain and cryptocurrency world where any asset across the globe can move freely between different blockchains, and do so quickly and at the cheapest price possible".

SifDEX is a decentralized exchange (DEX) that enables users to swap digital assets from a wide variety of blockchain ecosystems in one place, by connecting all major blockchains together using advanced bridging technology that we call "Peggy".

At the moment Sifchain enables routing from Ethereum main net to the Cosmos Ecosystem. This is achieved using Peggy (from Ethereum to Sifchain) and IBC (from Sifchain to other Cosmos-based blockchains). In the future up to 25 blockchains will be able to interact seamlessly through the Sifchain interface.

Within SifDEX, all trading is made possible through pooling with the native ROWAN token.

Sifchain is built using the Cosmos SDK. In addition to the Sifchain connection to Cosmos Hub via IBC, it already supports cross-chain transactions for Ethereum ERC-20 tokens. 20-25 of the top blockchains, such as Bitcoin, Polkadot and EVM-networks, like Avalanche and Polygon, also will be connected through Sifchain in the long run.

### **Peggy & Peg-zones**

In order to provide cross-chain support Sifchain uses a concept called Peggy to create a pegged token model. Peggy's model is inspired by the Cosmos peg zone model. A 'peg zone' is an account-based blockchain which bridges 'zones' within Cosmos to external chains like Bitcoin or Ethereum. These peg zones allow assets to be easily transferred between Sifchain and external chains.

Sifchain utilizes the 2WP protocol, which allows to swap pegged tokens. For instance, the swap of LTC to BTC would be executed as transactions of pegged versions of those tokens (cLTC and cBTC) on the Cosmos SDK blockchain. Sifchain users will trade with pegged tokens within the Sifchain system.

The utilization of pegged tokens also provides unique crypto-economic incentives for its participants. For example, Sifchain validators only need to run "Sifnode" (Sifchain's network) and leave the work with cross-chain transaction to peg zone validators.

After the run of the first Peggy implementation in the later half of 2021, the team started approaching the launch of Peggy 2.0, which will allow the fast deployment of connection to all EVM blockchains.

### **IBC connection**

Thanks to IBC users can seamlessly transfer assets between Sifchain and IBC-enabled blockchains. With IBC and Peggy Sifchain users will be able to export approved Cosmos-specific assets into Ethereum, as well as transfer Ethereum assets across any blockchain IBC-enabled blockchain. This is a huge step towards the Sifchain's goal of becoming the world's first omni-chain DEX.

#### Governance

Sifchain will use decentralized governance with SifDAO (This strong statement was made back in 2021, when decentralized community governance was on the wave of popularity).

SifCore (the core Sifchain team) pays great attention to the development of SifDAO and a total transition of governance power over all aspects of the protocol to its participants.

For true self-sovereignty, Sifchain’s development should be self-funding and self-sustaining. Linux and Wikipedia are considered as examples of organizations that have maintained the funding needed to continually produce critical open-source resources. You can find details about SifDAO [here](https://sifchain.notion.site/SifDAO).

### **Security**

To ensure the security of the Sifchain ecosystem, the SifCore team will lead the development and deployment of each bridge. The SifCore team intends to provide all bridges with the same security guarantees. The team plans to use the ROWAN native token as a collateral, where required. Or a new token with the only aim to be used by peg zones will be created, depending on a successful implementation of the rebalancing mechanism and market conditions.

### $ROWAN

$ROWAN is the native token of Sifchain. It has a variety of uses within the ecosystem:

* ROWAN is the universal liquidity pairing token of SifDEX. To enable swaps between tokens, each asset is paired with ROWAN to make an LP pool. As such half of the TVL of the DEX is made up of ROWAN. As TVL expands, demand for ROWAN expands too
* ROWAN also plays a central role in the crypto-economic security of Sifchain. Node validators should stake an amount at least equivalent to the TVL of the DEX, to ensure that the network is secure and the cost of malicious activity (slashing) is not worth anything a validator can gain from fraudulence - as per Tendermint consensus. Thus, the additional TVL has a multiplier effect on the market cap of ROWAN. As TVL on DEX expands, half of the TVL must be made from ROWAN. To ensure this, an amount at least equal to the TVL should be bonded by validators. Thus, for every $1 of any external asset added to SifDEX, $3 of ROWAN is required by the system
* Node validators must stake ROWAN to compete to enter the validator pool. Only the top 100 validators (ranked by number of ROWAN staked) are able to earn block rewards. Block rewards are paid in ROWAN
* Transaction fees for swaps and transfers are paid in ROWAN&#x20;
* Rewards for liquidity provision are also paid in ROWAN
* ROWAN is the Governance Token of Sifchain - the more ROWAN held by a party, the more weight their vote has in governance

More detailed description of ROWAN and its tokenomics could be found in the [whitepaper](https://assets.website-files.com/60ec70152eafa8dd30cb2fb5/6100250b18eca84d2952ea0e\_sif\_tokenomics\_latex.pdf).

Rowan was also discussed on Sifchains's Medium.

Current situation:



<figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

There are also some concerns about TVL. Supply increased higher than it was previously announced - to 1 billion tokens.

However, have a look at[ the results of the Q1 of 2022](https://medium.com/sifchain-finance/sifchain-update-spring-summer-2022-ec7cda4896c8):

* Sif’s Acsension liquidity mining program was launched&#x20;
* Launched the Protocol Monetary Trade Policy (PMTP) with SifDAO control over policy-setting to SifDAO
* Forming numerous DAO councils, including Validator Delegation, Token Listing, and the PMTP council
* Decentralizing the Sifchain Front-end. Six different front-end providers now host Sifchain DEX front-ends
* Hired & grew the Sifchain team with hiring key personnel across engineering, business, and marketing
* Launched the Sifchain Ambassador program, now with 11 ambassadors
* Raised 35 on-chain proposals, including software upgrades, community pool funding initiatives, expansion of our validator set, policy parameter updates, and council member elections
* Issued the first how-to guide for validators, for setup, delegation, and chain upgrades
* Expanded the list of community-owned and operated tools, which now includes three different dashboards, a ROWAN faucet, and a block-explorer

Furthermore, the team of engineers performed the following work on the back-end, which leaded to the improvement of Sifchain's performance:

* Sifchain.js&#x20;
* Native Integration testing&#x20;
* Admin module launch&#x20;
* New IBC Connections & formed partnerships with several IBC relayers&#x20;
* Migrated to non-Sifchain RPC endpoints to external vendors&#x20;
* Implemented better ways of working, including Agile practices and a Support Ticket system to help improve the user experience with Sifchain&#x20;
* Finally, up until the recent market crash, Sifchain has been seeing incredible growth numbers

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

Key development areas, the ream wii be focused on:

* Margin Trading
* &#x20;Omni-EVM&#x20;
* Sifchain DEX&#x20;
* Upgrades Engineering Pipeline & Sifchain Back-End Optimizations
* &#x20;Partnerships, Marketing & PR&#x20;
* Team Building&#x20;
* Crypto-economic Updates

Sifchain became the first bridge to connect Ethereum and Cosmos, so now the team believes that their mission is to connect Cosmos to the world of EVM-based blockchains.

Over the past several months, Sifchain business development team has been hard at work building relationships with these other EVM chains. 45 different EVM chains have been analyzed to identify best fit. Today the list of top contenders has been narrowed to six possibilities for the next EVM connection.

<figure><img src="../.gitbook/assets/image (16) (2).png" alt=""><figcaption></figcaption></figure>

At the same time, the engineering team is working on the crucial Peggy 2.0 upgrade. The Peggy 2.0 codebase is in the midst of migration of smart contracts and load testing. The code has undergone 3 audits and has a 4th in process.

Timing: Peggy 2.0 release scheduled to Q3 2022.

The following updates are also scheduled to the rest of this year:

* Cosmos SDK 0.45 upgrade. This will bring proper support for ledger and AuthZ support and enable installation of CosmWasm
* Complete CLP Refactoring, which will make it easier for other external devs to work on core Sifcore functionality (and make it easier to build new products into Sifchain)
* Several DevOps Pipeline Optimizations and Monitoring Improvements
* Data integrity, monitoring & optimization strategy implementation

**Links:**

* [Medium](https://medium.com/sifchain-finance)
* [Gitbook](https://docs.sifchain.finance/welcome-to-sifchain/start-here)
* [Website](https://sifchain.finance/)
* [Twitter](https://twitter.com/sifchain?s=20)
* [Discord](https://discord.gg/sifchain)
* [Telegram](https://t.me/sifchain)
