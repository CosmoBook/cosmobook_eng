# Kyve

### The Problem

As blockchains continue to expand, they’re creating more and more data every second. In order to prioritize scalability, proper management of historical data is typically overlooked, leading to major risks and issues for the blockchain and its ecosystem/users. For example:

1. A blockchain losing blocks
   * [This has already happened on Solana](https://github.com/solana-labs/solana-bigtable?tab=readme-ov-file#restoring-missing-blocks)
2. A blockchain is growing faster than it can handle data (Solana, Injective, Sei). If it takes one second to sync a block, but the chain moves with 400ms block time, it is impossible to sync a node from the beginning to live height.&#x20;
3. There are no standards for data: In Web2, everything is standardized for a reason. In Web3, it isn’t staking; delegating is the same term, but the schema is completely different, resulting in huge operational lifts needed by teams to support both transaction types.
4. Ethereum pruning historical data for scalability, [leaving L2s built on top of them with no historical data support](https://twitter.com/KYVENetwork/status/1767224043269189714)
5. Relying on a centralized RPC provider in order to get access&#x20;
   * RPC providers showing wrong balances for certain wallets to create panic

### KYVE’s Solution

KYVE provides Data Rollups-as-a-Service (DRaaS), enabling blockchains to off-board their historical data management to ensure its permanence and streamlined, reliable accessibility for developers, node operators, and more while still achieving optimal scalability.&#x20;

**Tagline:** We handle the data, you build the future.

### KYVE Technical Description

KYVE is its own Layer 1 modular blockchain built with the Cosmos SDK. It has two layers: the chain layer, which has 100 nodes to secure the network, and the protocol layer, which consists of data pools (each pertaining to a specific historical data set, like Osmosis blocks).&#x20;

The Protocol layer runs on a (D)PoS mechanism to incentivize its network of over 60 protocol validators working within the data pools to fetch, validate, and archive specific data onto permanent, decentralized storage solutions like Arweave, Filecoin, EthStorage, or others. The protocol is interacted with via [KYVE’s web app](https://app.kyve.network/#/).

<figure><img src="https://lh7-us.googleusercontent.com/docsz/AD_4nXcMgIEI0ZXq0zdxnVyiAoWSlbfm8Kp34QIiQ_3BEq-k9x2QhM661M3DgNTMkK8o87_bnVkrWjqOc_vbnhuTb62z1FpiX6E8OFY85B2366lTVWRKyA-iOgcv0CrNsS-xcCWoqOoAKBZTawxF80dOCNjMVpg?key=53O3UxNg48EHnRS4E6jq1w" alt=""><figcaption></figcaption></figure>

KYVE’s solution is fully interoperable, which makes it usable by any ecosystem as long as the data is deterministic. Currently, KYVE supports Cosmos Hub, Cronos, Osmosis, Axelar, Archway, Noble, and Celestia. KYVE is already testing support for Ethereum L2s like Arbitrum and Optimism. Being backed by NEAR, Polkadot, Ava Labs, and other larger ecosystems, KYVE aims to support those as well in due time.

### KYVE Tooling

On top of its decentralized protocol, KYVE provides a network of tooling to further streamline the data experience and overall accessibility:

* [KSYNC](https://docs.kyve.network/validators/ksync/) for node operators[:](https://docs.kyve.network/validators/ksync/) Node operators are at the heart of blockchains. In order to enhance the node experience and overall scalability, KSYNC enables rapid node syncing to any historic block, state, or height of a chain made trustless by KYVE. [See a demo here for auto-generated syncing of Archway data via the web app.](https://youtu.be/1Sq-yuleu00)
* [Trustless API](https://docs.kyve.network/developers/data\_engineers/accessing\_data/trustless\_api) for developers: Via KYVE’s trustless API, developers can connect their applications to Avail’s trustless historical data within seconds for free without having to trust a central entity. It can also be used to spin up their own API endpoint.
* [Data Pipeline](https://docs.kyve.network/developers/data\_engineers/accessing\_data/elt\_pipeline/overview) for devs and data analysts: For analytics purposes like explorers, marketing tools, or accounting solutions, developers need to be able to analyze big data sets quickly. KYVE’s Data Pipeline provides a solution for importing trustless data into BigQuery, Snowflake, MongoDB, and others. [See a demo here for querying Axelar blocks. ](https://youtu.be/Rtrds6Q0MHQ)

### $KYVE Utility

$KYVE is KYVE’s native coin. It has multiple utilities across the KYVE Network:&#x20;

* On the chain level, $KYVE is used for delegating (staking), securing the network through Proof of Stake;&#x20;
* On the protocol level, $KYVE is used for funding the data pools (integrations), and delegating to protocol validators, providing security for uploaded data.&#x20;
* On the governance level, $KYVE is used for submitting and voting on proposals, allowing stakeholders to have a say in the evolution and growth of KYVE.&#x20;

Read KYVE’s tokenomics further in detail [here](https://www.kyve.network/tokenomics). KYVE is also inflationary, find details on this [here](https://docs.kyve.network/community).&#x20;

### KYVE’s Latest Milestones

* KYVE mainnet launch and TGE was in Q1 2023;
* KYVE has already integrated Cosmos Hub, Osmosis, Archway, Axelar, Cronos, Noble, and Celestia on mainnet;
* KYVE has started testing integrations to support ZetaChain, Ethereum, Arbitrum, Optimism, and many other blockchains on its testnet, aiming to extend its solution to all ecosystems;
* [Q1 2024 highlights](https://blog.kyve.network/kyves-vision-unfolds-q1-2024-strategic-milestones-recap-a3893275f242).

### KYVE Narratives

* Modular: KYVE is a modular chain and fits seamlessly into modular builds as a data validation layer. [Read further into this. ](https://blog.kyve.network/understanding-modularity-in-web3-a-beginners-guide-kyve-s-role-in-modular-innovation-4a0f2ef2c585)
* Public Good: KYVE makes historical data a public good — free for anyone to access forever.
* Layer 1: KYVE is its own L1 chain built with the Cosmos SDK, with 2 layers (the protocol and the chain layer).
* Token Analysis: Analyzing token trading and staking is always more insightful if you have something to compare it to. With KYVE archiving and validating all historical data of Osmosis, dYdX, and soon others, this can be a very easy and reliable resource for those building token analysis dashboards or indexers.
* AI: Data rolled up by KYVE is very easily implementable into any preferred data backend and transformable into any data format, AKA, can be plugged into any AI framework to build out an AI solution based on trustless historical data. For example, a developer created Crypto Queries, an AI that helps query for specific NFT metadata sourced through KYVE.
* Rollups: KYVE provides Data Rollups-as-a-Service (DRaaS), creating custom data rollups per data set/blockchain, which allows blockchains to offboard their historical data management onto KYVE, enabling full scalability while ensuring a permanent, trustless backup of their historical data.&#x20;
* Data Availability/Celestia: KYVE focuses on data validation and storage, and can be leveraged by a DA layer like Celestia. KYVE has also integrated Celestia, meaning that KYVE is managing the historical data of Celestia and its entire ecosystem of rollups — seeing that Celestia deletes its data every 30 days. We’re looking into doing this for Ethereum as well.
* Appchains: KYVE provides data rollups/makes the historical data of app chains trustless and easily accessible to all (like Noble, Celestia ecosystem, etc.). This also applies to Rollchains ([see partnership announcement](https://x.com/KYVENetwork/status/1773372446898303214)).
* Interoperability: KYVE is fully interoperable and agnostic; it can store data onto any storage platform (BNB Greenfield, Filecoin, etc.) and can work with any ecosystem’s data as long as it’s deterministic. KYVE is very much a plug-and-play kind of infra.

### Links

* [Web app (protocol layer)](https://app.kyve.network/#/)
* [Explorer](https://explorer.kyve.network/kyve)
* [Website](https://www.kyve.network/)
* [Twitter](https://twitter.com/KYVENetwork) (75.4k followers)
* [Linkedin](https://www.linkedin.com/company/kyve/) (4.2k followers)
* [Telegram](https://t.me/kyvenet) (4.8k members)
* [Discord](https://discord.com/invite/PATvZvEmxF) (50k members)
* [CMC Community ](https://coinmarketcap.com/community/profile/KYVENetwork/)(3k members)
* [Investors/Backers](https://www.kyve.network/backers)
* [In-depth intro article](https://blog.kyve.network/introducing-kyve-88aa50bb7933)
* [Tokenomics](https://www.kyve.network/tokenomics)
* [Documentation](https://docs.kyve.network/)
* [Media Kit/Logos](https://www.figma.com/file/aq5NHz4O5VrEiagcm4lCbw/Assets?type=design\&node-id=0%3A1\&mode=design\&t=EtNsRBTrDCh51YRO-1)

\
