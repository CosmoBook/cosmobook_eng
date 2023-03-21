# Ojo

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

During the creation of Umee, the development team noticed a lack of an easily usable Cosmos-based oracle that they could easily connect to in order to obtain secure and reliable asset price data. Umee decided to use the design of Terra's oracle to create its own oracle, as it best suited their goals.

**Ojo** is the evolution of Historacle, Umee's native price provider. As the data center of the Cosmos ecosystem, Ojo will be launched to provide an accessible, reliable, and uninterrupted flow of data needed to support the growing web3 economy.

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

As credit protocols are sensitive even to the slightest price movements, the Umee team has enhanced the security of the oracle. The changes have drawn interest from other developers in the field, including those from Kujira and Juno.

**Ojo** is a decentralized network of oracles focused on security and built to support the Cosmos ecosystem. Ojo will receive price data from a diverse range of sources both on-chain and off-chain, using advanced security mechanisms to ensure the integrity of the data provided.

The goal of Ojo is to provide the most accurate and up-to-date price data for all IBC Cosmos assets. To achieve this goal, validators run the Ojo Price Feeder, a utility that queries multiple centralized and decentralized platform APIs to collect a wide range of price data and vote on the median price. Currently, Price Feeder supports the following sources: Binance, Bitget, Coinbase, Crypto, Gate, Huobi, Kraken, Mexc, Okx, Osmosis, OsmosisV2. More information can be found here: [https://github.com/ojo-network/price-feeder](https://github.com/ojo-network/price-feeder).

### Features&#x20;

#### Accessibility&#x20;

All blockchains with IBC and CosmWasm support will be able to access accurate and reliable Ojo data channels. The Ojo team focuses on developing, maintaining, and improving Ojo data streams so that other developers can focus on their own development. Accessing Ojo data is as simple as importing the client module developed by the Ojo team.

#### Reliability&#x20;

As a critical part of the infrastructure built for the entire Cosmos ecosystem, Ojo takes a strict security-based approach to ensure data accuracy and reliability. Ojo data is collected from a diverse catalog of authoritative sources and is verified by a distributed network of validators before publication. Ojo uses advanced security mechanisms, including data filtering and the use of time and volume-weighted average prices (TVWAPs) for supported assets, to ensure the integrity of all provided price data.

#### Time and Volume-Weighted Average Price&#x20;

Ojo uses time and volume-weighted average prices (TVWAPs), which include time-weighted volume and volatility, to prevent short-term trades from affecting prices. By using this technology, Ojo is significantly more difficult to manipulate compared to existing oracles. This can help safely use assets with low volume and liquidity in the Cosmos DeFi ecosystem.

#### Accuracy&#x20;

Ojo operates on a distributed set of validators who vote on prices transmitted through Ojo price feeds. As a PoS blockchain, validators have a financial incentive to provide the most accurate prices, regardless of the state of individual price feeders which may occasionally malfunction or be subject to manipulation. To ensure the accuracy of the data provided, participants actively providing accurate data are rewarded, while those providing inaccurate information or consistently voting for such data are subject to serious financial sanctions.

#### Volume of Data Provided&#x20;

Ojo plans to create a wide range of data channels to provide the most reliable data that meets the individual needs of those who are actively building. These include:

* price feeds for various crypto assets
* information on prices for traditional financial products
* social data obtained from popular web2 applications
* environmental data needed to support sustainable development efforts worldwide
* medical data needed to simplify various medical processes
* scientific and historical data that can be permanently stored on the network
* random number generators
* real-time sports data
* gaming data needed to attract a new generation of gamers to the network.

#### Data Provision Terms

&#x20;Ojo will not initially charge projects that rely on its data. As a Cosmos blockchain, Ojo will use a Cosmos-first approach to help support the growth of the Cosmos ecosystem before monetizing any of its services. By freely providing the most reliable data to all blockchains that support IBC, Ojo can become widely trusted and deeply rooted in Cosmos.

{% hint style="info" %}
**Reference: Oracles**&#x20;

A blockchain is an isolated network that can only use data available within that network, similar to how computers without internet access can only use local data. Thus, a blockchain enables the creation and storage of records that are shared within the network but cannot access or guarantee the integrity of data obtained from outside sources. The oracle problem pertains to the inability of a blockchain to receive and transmit data to external systems without relying on a separate organization. Oracles are agents that securely provide smart contracts with reliable real-world data. Although oracles are primarily used to provide protocols with data about prices for various assets, they can also be used to provide any form of real-world information, including medical information, weather data, or sports competition results. Learn more about oracles, for example, in [Binance academy](https://academy.binance.com/en/articles/blockchain-oracles-explained).
{% endhint %}

### Links:

[Website](https://ojo.network/)

[Twitter](https://twitter.com/ojo\_network)

[Discord](https://discord.com/invite/wWQAhU9q4y)

[GitHub](https://github.com/ojo-network/ojo)

[Blog](https://blog.ojo.network/)

[Reddit](https://www.reddit.com/r/OjoNetwork/)

[Telegram](https://t.me/OjoNetwork)
