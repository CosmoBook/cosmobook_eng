# Oraichain

<mark style="color:red;">**The English version of CosmoBook is currently available in draft form. We are working on corrections.**</mark>

![](https://telegra.ph/file/75d2525e66b9c3dcf5910.png)

## Oraichain

Oraichain is a data oracle platform, which aims to connect smart contracts to AI.

The blockchain and smart contracts operate on-chain and have no access to the external systems (i.e., off-chain). Oracles are the platforms that connect blockchains to external systems. Thereby allow smart contracts to find outside information, as well as transfer data.

You can learn more about Oracles on Binance Academy. Here is the [link](https://academy.binance.com/ru/articles/blockchain-oracles-explained).\
And [here](https://www.bloomberg.com/press-releases/2022-03-24/oraichain-launches-mainnet-2-0-to-boost-scalability-enable-mass-adoption-of-ai-in-the-blockchain-ecosystem) is the extract from Orai Mainnet 2.0 press release on Bloomberg.

Oraichain Mainnet 2.0 is a major upgrade that paves the way for mass adoption of AI and interoperability with other chains in the blockchain. It provides stronger interoperability through relaying protocols, bridges and IBC in the Cosmos SDK-based networks, creating AI L1 for dApps.

### AI and Smart Contracts. Compatibility Issue

\
AI models use complex approaches (such as [SVM](https://en.wikipedia.org/wiki/Support\_vector\_machine), [supervised learning,](https://en.wikipedia.org/wiki/Supervised\_learning) neural network, and clustering). Therefore, smart contracts are not able to run AI models in the code, and it is almost impossible to integrate an AI model into a smart contract.

The reasons come from three characteristics of smart contracts as follows:

* Strictness: smart contracts always follow strict rules in which the inputs must be 100% accurate (e.g. signature) to generate an output. However, AI models can hardly give such accuracy (a good example is face recognition).
* Environment: smart contracts are mostly written in high-level programming languages such as Solidity and Rust that provide stricter syntax and better security. At the same time, the AI models are typically written in Python or R.
* Data size: On one hand, smart contracts often have relatively small storage since it helps reduce transaction fees in some blockchain networks such as Ethereum. On the other hand, the size of an AI model is much bigger.

### **How it works**

First of all, it is important to remember how the oracles work: a user requests the execution of a contract, that on-chain requests an oracle contract. The contract, in turn, requests the oracle server (off-chain), which is connected to the outside world. Then in reverse order.

<figure><img src="../.gitbook/assets/image (17) (4).png" alt=""><figcaption></figcaption></figure>

To better understand oracles' working principles, we recommend exploring this [article](https://research.thetie.io/blockchain-oracle-comparison/)**.**

![](https://telegra.ph/file/71c60e1c497ffee4b49e0.png)

The process of requesting an AI API is shown in the picture of Oraichain's System overview. To execute a request, users or smart contracts need to call an oracle script that is available on the ORAI gateway or marketplace. In an oracle script, there are AI data sources (provided by AI providers), test cases, test source (optional), and transaction fees for each request. When a request comes, a random willing validator is chosen to perform this request. The chosen validator will fetch data from one or more AI providers on behalf of the user after executing the test scenarios, and if the AI provider fails in testing, the request is canceled.

A request is considered successful if its result is written to the Oraichain blockchain. The transaction result, which can be fetched from smart contracts and regular applications, is proof of execution, and fees are applied in this transaction. There is an overhead of reading results from Oraichain’s transactions, but it helps ensure that the AI API quality is good and there is no data tampering during the process of fetching data from AI providers.

Compared to Band Protocol and Chainlink, API testing based test cases is the unique functionality. Since Oraichain focuses on AI APIs, testing is very important to control the quality of AI providers. Besides, test providers can propose suitable test cases that users can choose to test an AI API. Test cases in the Oraichain marketplace can encourage AI providers to improve the accuracy of AI models.

Another interesting feature is that the Oraichain community has the power to rate the validators’ reputation for quality AI APIs improvement. If a validator has bad behavior, such as failing to perform test cases and validate AI providers, slow response time, and low availability, its holding token will be slashed.

However, validators in Oraichain are responsible for performing many important tasks and could be a centralized point. Therefore, the number of chosen validators should be high in order to increase request performance, scalability, and high availability. Meanwhile, because we need many validators to participate in the Oraichain network and maintain their quality work, block reward and transaction fees must be applied for such validators to earn more ORAI tokens.

### **$ORAI Token**

The first thing you need to know - ORAI exists in three networks: Ethereum, Binance Smart Chain and Oraichain. The tokenomics is confusing, and that leads to some thoughts.

Now the max supply is 9,779,272 ORAI. The initial supply was 86,000,000 ORAI.

There were three token burnings:

1. On December 22, 2020 73% of initial total supply was burnt: [https://medium.com/oraichain/oraichain-tokenomics-v3-73-token-burn-and-key-updates-4e99d1972bcf](https://medium.com/oraichain/oraichain-tokenomics-v3-73-token-burn-and-key-updates-4e99d1972bcf)

2\. On March 28, 2021 258,449.4 ORAI burnt from Team (a big gesture, however, it is only 1% of the current supply at that time: https://etherscan.io/tx/0xa66c06593dc8559f565e4a480c32c698ccbb128c49404f8a07a203a5f37902e1&#x20;

3\. The 3rd token burn was held on June 23, 2021. 3,000,000 ORAI tokens from Team, Advisors, and Foundation were burnt: https://etherscan.io/tx/0x953694d378f036ff0e136441e78875ae241d9f212b583007eb4814bab64cf7e3&#x20;

Despite the fact that the fire was lit three times, the chart seems to be cold:

![](https://telegra.ph/file/e22dff4c05c196a6220e2.png)

The current distribution of ORAI is as follows:

![](https://telegra.ph/file/285a13802f24b83441613.png)

The idea with almost 30% in the hand of the team does not seem good, but I make no claims to an objective assessment.

The token has standard Cosmos utility:

1. Staking: all validators are required to stake ORAI in order to be selected to create a block or fulfill data request from AI providers
2. Transaction fee: the ORAI token is required in order to run an AI request sent to the Oraichain network
3. Participation in governance: the Oraichain network is organized in the DAO manner, all protocol upgrades and parameter changes must be voted by token holders

Separately, I note that the ORAI staking APR is about 29%, imho, it looks presumptuous, considering that circulating supply is about 2.5 million ORAI and the emission by 2027 is planned to be 100%.

![](https://telegra.ph/file/e0618b8229ba6ff885e3b.png)

### **Dashboard**

You cannot stake your ORAI with Keplr or the Keplr dashboard, there is no zone there. However, Oraichain has its own dashboard, combined with governance, transaction scanner and the IBC map.

It is needed if you decide to delegate your ORAI or participate in network governance. Furthermore, there you can find channels' numbers, needed for manual Keplr adding to transfer tokens between the zones.

![](https://telegra.ph/file/ae1da84e58205b3c7e099.png)

### **OraiDEX**

Along with the mainnet, on March 22, 2022 Oraichain has launched OraiDEX, CosmWasm-based decentralized exchange platform.

It has the following functionality:

1. Token transfer between Ethereum, Binance Smart Chain, and other networks
2. Token swapping. Easy, obviously, with a high APR. This is not the author's sarcasm, this is just freely interpretation of the press release
3. IBC compatibility, allowing trustless communication between ORAI, ATOM, OSMO and gems like LUNA, UST and CRO (as for gems, well, now I am rofling)
4. NFT Bridge. Relocation of NFT assets from Oraichain to other networks like Ethereum or Binance Smart Chain and vice versa will be enabled. The feature is not available for now.

Now a bit about the personal experience. It is really possible to transfer tokens between BSC and Cosmos, and it is also possible to swap tokens. However, it is not possible for Eethereum yet. I will note that the possibility of USDT transfer from BSC to Oraichain, swap ATOM and withdrawal through the bridge in Cosmos Hub is the third option of the decentralized entrance to the Cosmos ecosystem.

* Option #1 (Сaution! EVMOS)**:**: https://teletype.in/@creeptah/evm\_to\_cosmos
* Option #2 (Axelar): https://teletype.in/@creeptah/evm\_to\_cosmos\_2
* Option #3 (ORAI): https://teletype.in/feed/@creeptah/BSCtoCosmos

By the way, you can see the trading volume and estimate the liquidity volume on info.oraidex.io/tokens&#x20;

![](https://telegra.ph/file/f6a8c636ff3eceaadb080.png)

OraiDEX also has its own token, OraiX, which was launched on June 22, 2022, and was selling for $0.01. The current price is 0.007414.

Use-cases: meta-staking fees (the fee is taken directly from profits), pay pool creation fee, OraiBridge and NFT bridge fees, and airdrop ticket purchases for newly listed NFT projects. Total supply is 1 billion ORAIX, 30% will go to the staking rewards (including fairdrop), 50% to the liquidity mining incentives, 15% to the developers pool, and 5% to the community. Staking rewards, liquidity mining incentives, and developer pool will be vested in 5+ years.

The 117,000,000 ORAIX is split between OSMO, ATOM, JUNO and ORAI, KWT and MILKY stakers. Check and see if you are eligible[😋](https://getemoji.com/): [https://oraidex.io/claim-oraix](https://oraidex.io/claim-oraix)

### **WTF VRF**

Random number generators (RNG) is one of the most difficult tasks in programming. You should write a code that generates a random number… but in this case, the number will come by an algorithm, so it means that it is not random? This is where VRF (Verifiable Random Function), which is widely used in cryptography, comes into play. It is impossible to verify the accuracy of the result, and that's why the Verifiable Random Function was created. The point is that a randomly generated number can be verified for the accuracy, excluding, for instance, the tampering in the Lamba drop with 10000000 participants.

Each validator holds his or her own public key with which the collective group signature is generated.  Similarly, a group signature is formed to validate the creation of a random value, or a set of it.

![https://docs.orai.io/vrf/introduction](https://telegra.ph/file/17fa71959c7084ede997e.png)

I will not go too deeply, but know that Oraichain believe that validators can be compromised, and so the group signature can also be compromised, so the random number will not be generated randomly. That's why they developed VRF v.2, details of which can be found here. https://docs.orai.io/vrf/introduction&#x20;

Oraichain is competing with Chainlink in this field, so if VRF v2 makes sense, then Oraichain is a gem ;) DYOR

![](https://telegra.ph/file/23e41eb39f4cedb1ae61b.png)

Oraichain has already launched contracts to generate random numbers via VRF 2.0 for Fantom, Avalanche and Binance Smart Chain.

### **Ecosystem**

There are not so many dApps right now, I will list the ones that catch my eye.

#### **yAI.Finance**

[yAI.Finance](https://yai.finance/) - is a yield aggregator platform based on artificial intelligence. Yeah, now you can justify your rektas with dumb artificial intelligence. APY doesn't look rich, but maybe I did not get in deep enough.&#x20;

![](https://telegra.ph/file/4a387208075234be38e43.png)

#### **Ai.Right**

[aiRight](https://airight.io/) — is an NFT marketplace based on…Yes, it is AI again. The thing is that the jpeg originality is evaluated by artificial intelligence (Solana Minte, or what?)

![](https://telegra.ph/file/95f72a9eca3fb57874ca0.png)

#### **Dino Hub**

This is the thing I like the most. Dino Hub (was formerly called Oraichain Data Hub) is a decentralized data hub and a data labeling platform. Meaning that if you have raw data, you are able to download a raw dataset, set a reward for labeling, and users will do it for you (and make money from it). Processed data can be sold. Moreover, this is where you can create a test case for the AI providers.

In short, I recommend you try it yourself. I do not promise the golden mountains, but the experience is cool.

![](https://telegra.ph/file/6ffbe10ac23e97b4a79f3.png)

### **Overall Impression**

Oraichain is rather a foundation, than a zone. The tokenomics and the roadmap change every year, and there are many development directions based on AI and revolving around the oracle with VRF and the API AI integration. At the same time, Oraichain is not fully related to Cosmos. They are closely working with Avalanche, Fantom and BSC, and their main competitor is Chainlink. Within the ecosystem they mention, for example, Trava - ludo, based on Fantom/Avalanche/BSC. In the context of Cosmos there are probably only OraiDEX and IBC with CosmosHUB and Osmosis.

If Oraichain will not bail on the oracle boosting, they would be getting somewhere.

### **Links**

**Twitter:** [https://twitter.com/oraichain](https://twitter.com/oraichain)

**Telegram:** [https://t.me/oraichain](https://t.me/oraichain)

**Discord:** [https://discord.com/invite/wwjg2ddfzd](https://discord.com/invite/wwjg2ddfzd)

**Medium:** [https://oraichain.medium.com/](https://oraichain.medium.com/)

**Documentation:** [https://docs.orai.io](https://docs.orai.io/readme/decentralized-validator-sampling)

**GitHub:** [https://github.com/oraichain](https://github.com/oraichain)

**Actual roadmap (2022):** [https://orai.io/roadmap](https://orai.io/roadmap)

**Articles:**

[https://morioh.com/p/100f231834f5](https://morioh.com/p/100f231834f5)

[https://www.bloomberg.com/press-releases/2022-03-24/oraichain-launches-mainnet-2-0-to-boost-scalability-enable-mass-adoption-of-ai-in-the-blockchain-ecosystem](https://www.bloomberg.com/press-releases/2022-03-24/oraichain-launches-mainnet-2-0-to-boost-scalability-enable-mass-adoption-of-ai-in-the-blockchain-ecosystem)
