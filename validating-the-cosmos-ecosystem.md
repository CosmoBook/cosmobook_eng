# Validating the Cosmos Ecosystem

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Introduction

Questions about validation and choosing a validator in the Cosmos ecosystem are often discussed in thematic chats. This topic is not fully covered (and is unlikely to be).

We have tried to gather information about all aspects of validation in one big article.

We hope for active help from the community, and most importantly, validators, in editing and filling the article.

### Briefly about the Cosmos ecosystem and key terms <a href="#7i9h" id="7i9h"></a>

The security of the Cosmos ecosystem is based on **DPoS** (Delegated Proof of Stake).

Unlike classic PoS, where each user with a stake can choose a new block, in DPoS, validators select blocks through voting. The number of validators is limited, and they receive a reward for this. In order to choose blocks, a validator needs to accumulate stakes above a threshold value or join the active network.

This is why validators are interested in attracting user tokens.

Let's figure it out.

#### **How Cosmos Works** <a href="#0q6g" id="0q6g"></a>

The Cosmos network operates on three different levels.

1\. Network level: allows transaction confirmations and other consensus messages to interact with hub blockchains.

2\. Consensus level: orders nodes in accordance with validator decisions to add new transactions.

3\. Application level: updates the network by tracking changes in transactions and balances.

**Note:** In the text, we highlight important validator selection criteria with the ⚠️ icon. Use it.

<figure><img src="https://img2.teletype.in/files/1d/e8/1de8ed79-2b5c-4ad2-97a2-0fb160dee647.png" alt=""><figcaption></figcaption></figure>

_Tendermint_ is a solution that combines Layer 2 and Layer 3 (pBFT family consensus and networking) into a common engine, allowing developers to focus on application development rather than the complex underlying protocol.

> pBFT — Practical Byzantine Fault Tolerance. Read more about the problem of fault tolerance of Byzantine generals and consensus algorithms, for example, here: [https://3commas.io/ru/blog/alternativnye-algorytmi-consensusa](https://3commas.io/ru/blog/alternativnye-algorytmi-consensusa)

#### Staking <a href="#t2wi" id="t2wi"></a>

Staking is the process of locking tokens to secure the blockchain through proof of ownership. Rewards are paid for participation in steering, proportional to the blocked tokens.

#### Validator <a href="#6gl2" id="6gl2"></a>

Validators check transactions and sign new blocks in the blockchain. They receive income for this.

Validators also participate in governance by voting on proposals. The weight of a validator's vote depends on the amount of tokens staked in them.

Often, the term "validator" refers to a broader concept. In general, a validator is a person (organization, group of people) who ensures the operation of the validator entity and organizes all related services.

Validators in the network are selected randomly proportional to the share of their stake of the total number of locked coins (i.e., in a completely standard way).

#### Validator States <a href="#vtss" id="vtss"></a>

A validator can be in one of three states:

1\. **Validator active set (bonded)**. The validator is in the active set and participates in consensus. They earn rewards and can be slashed for bad actions (more on slashing in the next section).

2\. **Validator inactive (unbonded)**. The validator is not in the active set and does not participate in consensus. Accordingly, they do not receive rewards and cannot be slashed. It is possible to delegate tokens to a validator in this state.

3\. **Validator jailed**. The validator has been slashed and is in jail. In this state, they do not participate in consensus or governance. If a validator is jailed for missing blocks, they will be released after sending an unjail transaction. If a validator is jailed for double-signing blocks, they cannot be released from jail.

#### Slashing <a href="#lnrm" id="lnrm"></a>

Slashing is a "punishment" for a validator that involves confiscating part of their tokens. The percentage of tokens to be slashed depends on the violation committed by the validator and the threat it poses to the security of other network participants. This is not only a financial incentive for a validator to faithfully perform their duties, but also a measure that forces validators to "risk their own skin." At the same time, it motivates delegators to choose validators more carefully, as there is a risk of losing part of their tokens too.

There are two types of events that lead to slashing (using CosmosHub as an example):

**A slashing of 0.01%** can occur if a validator misses blocks (is offline) for too long. Downtime is recorded if a validator does not sign at least 500 blocks out of the last 10,000.

Additionally, a validator drops out of consensus and does not receive a block reward for at least 10 minutes (term: "jail"). After resolving the issues, the validator can rejoin the validator set by sending an unjail transaction.

<figure><img src="https://telegra.ph/file/f6a5f216f13d513987a2b.png" alt="" height="231" width="978"><figcaption></figcaption></figure>

**Slashing can occur by 5%** if a validator signs two different blocks at the same time. This malfunction is harder to anticipate and can result from poor operational practices or overtly malicious intent by the node operator. In addition to losing 5% of their tokens, the validator loses the right to propose blocks and receive rewards without the possibility of unlocking (effectively being removed from the validator set permanently). All delegators of the affected node receive a return of their tokens, and the unbonding period (i.e. the time for returning tokens from staking) is 21 days.

<figure><img src="https://telegra.ph/file/97e89b3f303117a84a471.png" alt="" height="295" width="978"><figcaption></figcaption></figure>

#### Delegator <a href="#whja" id="whja"></a>

A delegator is a user who delegates their tokens to a validator, thereby staking them.

Delegators receive rewards proportional to their token share of the validator's total number of tokens and pay the validator a small fee for their services (the fee is set by the validator themselves, as described below).

Since delegators share in the income of their validators, they also share in the risks. If a validator misbehaves, each of its delegators suffers losses in proportion to their stake. This punishment is one reason why delegators must conduct proper due diligence on validators before delegating. Distributing their stake among several validators is another layer of protection.

Delegators play an important role in the system, as they are responsible for choosing validators. Delegation is not a passive role. Delegators must actively monitor the actions of their validators and participate in governance.

### Validator's Work <a href="#qhtq" id="qhtq"></a>

#### Technical Aspects of Validator's Work <a href="#oxrz" id="oxrz"></a>

Managing a validator is a complex process, and the team responsible for managing the validator has at least the following responsibilities:

\- administrating the servers on which the validator is running;

\- preparing for network upgrades;

\- monitoring validator chat rooms to notice vulnerability disclosures, unplanned upgrades, and recommendations;

\- setting up and maintaining monitoring systems to learn about any problems in advance; participating in discussions and votes that affect the network's future;

\- taking security measures to secure validator keys.

#### Administration <a href="#qbvp" id="qbvp"></a>

To become a validator, you need to:

\- rent or buy a server and place it somewhere (taking into account power supply, climate, etc.);

\- set up the network node on this server and wait for it to synchronize;

\- create a validator; delegate enough tokens to it to become an active validator.

#### Preparing for Network Upgrades <a href="#ujtx" id="ujtx"></a>

One of the validators' responsibilities is to prepare for network upgrades. Otherwise, if a validator misses an upgrade, they risk being jailed. To do this, the team must constantly read chats where the network interacts with validators and prepare for upgrades in advance. There is an excellent tool called [Cosmovisor](https://docs.cosmos.network/main/tooling/cosmovisor) that simplifies the upgrade process and allows you to prepare in advance, making life easier, especially if the upgrade happens in the middle of the night.

#### Chat Monitoring for Validators <a href="#khs2" id="khs2"></a>

There are many things that can go wrong in a blockchain network. For instance, the Dragonberry vulnerability was recently discovered in all Cosmos networks, and all networks had to be updated urgently. It is very important to constantly monitor the chat rooms of validators to learn about such things in advance and help the team fix them. Additionally, recommendations that can improve performance, fix bugs, and so on are often published there.

#### Setting up and Maintaining Monitoring Systems <a href="#28w1" id="28w1"></a>

One of the most important technical aspects of validator management is creating and configuring monitoring systems. Monitoring is essential to prevent situations where the validator does not sign blocks, and their team does not know about it. Some examples of such situations are:

* There was a disaster at the data center;
* The server ran out of space;
* The validator forgot to update their node, and so on.

These situations occur quite often, and it is essential to be always prepared.

The standard set of monitoring tools usually consists of the following:

\- [Grafana](https://grafana.com/) - visualization of metrics and a tool for sending notifications;

\- [Prometheus](https://prometheus.io/) - a tool to collect metrics from various sources and store them;

\- [PagerDuty](https://www.pagerduty.com/) - a service for sending push notifications or SMS if something goes wrong.

With a reliable monitoring system, responsible people will receive notifications immediately if something goes wrong so that they can understand what happened and how to fix it.

#### Participation in Discussions and Voting <a href="#swkb" id="swkb"></a>

Validators are entities that ensure the operation of the blockchain. Therefore, it is vital for them to always provide their feedback during discussions and vote for proposals in networks. Thus, validators contribute to the development of the network.

#### Taking Security Measures <a href="#x5h1" id="x5h1"></a>

Each validator has two keys:

\- Consensus key - used to sign blocks;

\- Wallet key - used to make transactions on behalf of the validator.

If either of these keys is lost, made public, or given access to unauthorized people, the validator can be lost, as neither of these keys can currently be changed. So, it is necessary to protect against key leaks or unauthorized access.

Here is a (not exhaustive) list of measures that can be taken to secure your validator:

\- Enabling SSH authorization only by public key;

\- Using hardware security modules for the consensus key;

\- Using cold wallets to store the key.

### Participation in governance <a href="#vauu" id="vauu"></a>

#### Voting <a href="#zif9" id="zif9"></a>

Validators and delegators in Cosmos can vote on proposals to change operational parameters (such as gas limit per block), coordinate upgrades, or make decisions on any specific issue.

Validators play a special role in the governance system. As the backbone of the system, validators are required to vote on every proposal ⚠️. This is especially important because delegators who do not vote will follow their validator's vote.

Often, the absence of a vote on a particular proposal is a criterion for a drop. If you do not vote, your validator will vote on your behalf. If your validator does not vote, your vote will not be counted.

Sometimes, even the validator's vote is not taken into account for a drop, so it's important to vote yourself, keep this in mind.

Let me give an example: your validator voted "yes" with its 1000 tokens (let's say it has exactly 1000 tokens) on a proposal. Afterwards, you vote "no" with your 100 tokens. As a result, there will be 900 votes in favor and 100 votes against.

For instance, Cosmos Hub ("Gaia") has an intra-network governance mechanism for [proposing changes](https://hub.cosmos.network/main/governance/proposal-types/text-prop.html), modifying [consensus parameters](https://hub.cosmos.network/main/governance/proposal-types/param-change.html), and spending funds from the [community pool](https://hub.cosmos.network/main/governance/proposal-types/community-pool-spend.html). It is good practice to discuss the proposed topic on the official forum, Discord, Twitter, etc., before creating a vote.

Let's look at the voting process for Cosmos Hub in general terms.

When voting in Cosmos Hub, the following **criteria** are determined:

**Minimum deposit:** 64 ATOM;

**Maximum deposit period:** 14 days;

**Voting period:** 14 days;

**Quorum:** 40% of the total stake (voting power);

**Threshold for passing:** 50% of the total stake;

**Veto threshold:** 33.40% of the total stake.

Before a governance proposal enters the voting period, the initiator of the proposal must have a deposit of more than the minimum amount of ATOMs (64) submitted. Anyone can contribute to this deposit, although it is usually done by the proposal initiator. Deposits for successful and unsuccessful proposals are returned to the contributors. The voting initiation process lasts for 2 weeks and can be initiated collectively.

Deposits are burned when a minimum of 1/3 vote "no with veto". Proposals are rejected in this case, as specified in [the Cosmos SDK gov module specification](https://docs.cosmos.network/main/modules/gov#deposit-refund-and-burn).

Deposits are not burned for failing to meet quorum or for rejecting a proposal.

The voting period is currently a fixed 14-day period. During the voting period, participants can choose to vote "yes", "no", "abstain", or "no with veto". Voters can change their vote at any time before the end of the voting period.

#### What do the voting options mean? <a href="#fpcb" id="fpcb"></a>

Abstain: The voter wants to contribute to the quorum, but does not want to vote "for" or "against" the proposal.

**Yes:** Approval of the proposal in its current form.

**No:** Disapproval of the proposal in its current form.

**No with veto:** A "no with veto" vote indicates that the proposal is either (1) considered spam, i.e. insignificant to the Cosmos Hub, (2) unreasonably infringes on the interests of the minority, or (3) violates or encourages the violation of interaction rules currently established by the Cosmos Hub governance.

[Proposal 75](https://ipfs.io/ipfs/QmVHVH9WeGy9tTNN9dViqvDn7N79XJJUseKXD1rpyLVckK) recommends voting "no with veto" for proposals that are spam, infringe on the interests of the minority, or violate interaction rules (i.e. social protocols adopted by governance). This proposal was an extension of the ideas put forth in P[roposal 6](https://ipfs.io/ipfs/QmRtR7qkeaZCpCzHDwHgJeJAZdTrbmHLxFDYXhw7RoF1pp). A "no with veto" vote does not have any direct additional financial value to the voter - you are not risking your tokens by using this option.

#### What determines whether a governance proposal will pass or not? <a href="#fw2g" id="fw2g"></a>

There are four criteria for a decision to be considered accepted:

**Deposit filled**: A minimum deposit of 64 ATOM (in our example) is collected for the proposal to enter the voting period.

**Quorum reached:** A minimum of 40% of the total network stake is required to participate.

**Simple majority of "yes" votes:** More than 50% of participating votes must support the "yes" vote by the end of the 14-day voting period.

**No veto imposed:** Less than 33.4% of the total stake supported the "No with Veto" vote by the end of the 14-day voting period.

All "Yes", "Abstain", "No", or "No with Veto" votes are counted for the quorum.

Validators not in the active set can vote, but their vote (including the votes of their delegators) will not be counted in the vote if they are not in the active set when the voting period ends. This means that if a token is delegated to a validator who is jailed or not in the active set at the end of the voting period, their weight in the vote will not be counted.

Although a simple majority of "Yes" votes (i.e. 50% of participating stake) is required for a governance proposal, the "No with Veto" vote, representing 33.4% of participating stake or more, can override this result and lead to the cancellation of the proposal. This gives the minority representing more than 1/3 of the participating voting stake the ability to reject a proposal that would otherwise have been accepted.

### Validator earnings <a href="#cy1m" id="cy1m"></a>

#### Commission <a href="#j53k" id="j53k"></a>

Validators receive income from commissions for their services.

Take a look at how validator commissions vary using the example of the top of the Cosmos Hub active set table.

<figure><img src="https://telegra.ph/file/7b6f75db4aa1772c9f8da.png" alt=""><figcaption></figcaption></figure>

Even from this table, it's apparent how validators set different goals for themselves and solve them differently.

Exchange validators (classification will be below) are not interested in attracting delegators from outside and essentially work with their exchange clients. Delegators of such validators are usually excluded from drops.

Validators often face the difficult choice of setting the commission fee since the higher the fee, the more income they will receive, but the less the delegator will receive and attracting delegators will become more difficult.

Networks usually recommend setting the commission fee in the range of 5-20%.

The most popular commission fee is 5%.

Many fall for the 0% trap, but such validators often seek to attract a large number of clients in this way, and then raise the commission fee without notice, taking a high place in the active set. Validators with a 0% commission fee also often do not qualify for the drop.

Each validator can set their initial commission fee, maximum daily rate of commission fee change, and maximum commission fee.

Sometimes there are questions about who stakes to validators with a 100% commission fee? Most often, the stake of such validators is their own. They set up a node only to delegate their own assets there and do not pursue the goal of increasing the stake size. Sometimes CEX validators do the same (Kraken validator in the example above).

In summary: when choosing a validator, pay attention ⚠️ to the commission fee (optimal 5-7%) and the availability of a means to notify your delegators about the validator's work (including commission fee changes), for example, through a telegram channel, bot, Twitter, etc.

#### Example of validator profitability calculation <a href="#qchs" id="qchs"></a>

Let's calculate the profitability of the CosmoBook validator on the Secret Network as of 11.04.2023 (detailed methodology review here).

The calculations will not take into account APR and restack changes, as well as user fees for transactions (here the goal is just to show the kitchen):

<figure><img src="https://telegra.ph/file/5e2ae90bdd06c247b1123.png" alt=""><figcaption></figcaption></figure>

In general, the formula will look like this:\
**profit = APR\*(self bond + (delegation-self bond)\*commission of the validator)** self bond - own delegation (those tokens, which the validator loads into itself).

**Initial data:**

Delegation 5285 SCRT;\
Validator Commission 5%;\
APR 24.43% (here);\
Own delegation (self-bonded) 20 SCRT.

<figure><img src="https://img2.teletype.in/files/dc/be/dcbedecc-5cc6-488f-a0e5-f6bc8f3f85a8.png" alt=""><figcaption></figcaption></figure>

The total revenue of the steking due to network inflation for the year will be 69.19 SCRT.\
If we talk about the profitability of the validator, it is important to understand that the validator incurs significant costs (the cost of infrastructure, software, monitoring tools, nodrunner time, the cost of means-reserving, etc.) and validation is not always a profitable activity.

#### Additionally: Reinvestment of rewards (auto re-staking) <a href="#vimu" id="vimu"></a>

In this topic, we will not consider the concept of compound interest. We will only say that autore-staking is the process of periodically transferring received staking rewards to the staked amount in order to increase profits.

Autore-staking became possible thanks to the presence of the authz module in the Cosmos SDK.

Authz - authorization of accounts to perform actions on behalf of other accounts, which allows the validator to execute messages on behalf of the delegator.

In other words, thanks to the authz module, the delegator can give the validator the right to perform certain cyclical processes on his behalf. Essentially, the delegator grants the validator the right to collect staking rewards from his wallet and report them to the staked amount. The next rewards the delegator will receive will be from the increased staked amount.

This is where the concept of APY (**annual percentage yield**) comes into play, which represents the APR (**annual percentage rate**) taking into account restaking.

The validator chooses the frequency of restaking. He also pays the gas for restaking for the delegator.

If you stake for a long time, enabling restaking is profitable. If the token is rapidly losing value, users often decide not to enable restaking and sell the rewards, paying off the staked amount. This strategy is relevant with shields at a high APR.

Before enabling restaking, make sure your validator has this function enabled. The presence of restaking ⚠️ can also be an argument when choosing a validator.

To analyze the APR and ARY of the network, the number of validators with restaking enabled, token prices, and the actual activation of restaking, we recommend using the application [https://restake.app/](https://restake.app/)

The image shows the Osmosis network, validators with restaking enabled, the validator's number in the network, restaking frequency, APY, and validator commission:

<figure><img src="https://telegra.ph/file/399c16c9868cb05b41901.png" alt=""><figcaption></figcaption></figure>

***

**Appchain issues and network responsibility to validators**

In this chapter, it is important to mention that the network is responsible for taking care of its validators for its own stability. A validator is not a freeloader who reaps the benefits without doing anything. Validators continuously bear financial costs for maintaining infrastructure and responsibility to their delegators. They spend a lot of time monitoring changes in the network, updates, and maintaining functionality.

**Appchains are not for everyone** (Some material taken from Kam Benbrik's article "Cosmos Hot Takes for 2023," published in Imperator Research.)

"If there is one lesson we must learn from the past two years, it is that the thesis of Appchain (a project that builds on its own network) is not the best solution for new projects. Appchains are difficult to manage because the main team must focus not only on their main product but also on network infrastructure and security. This is a challenging task.

The biggest problem for teams was how to make the blockchain economically sustainable to cover the expenses of validator infrastructure and incentivize people to stake tokens to ensure network security. The bear market demonstrated that many low-capitalization projects failed in this regard. In 2023, if the bear market persists, we will see many validators leave networks that were once promising application networks but have since become zombie networks."

<figure><img src="https://telegra.ph/file/56b17e969a01153990d9b.png" alt=""><figcaption></figcaption></figure>

As an alternative, new teams will focus more on attracting new features and solutions, such as Celestia, Interchain Security, or SAGA, rather than creating their own application network. This will allow them to concentrate on their product, attract users and liquidity, and create an Appchain if necessary after achieving success.

Thus, any Appchain, to ensure its sustainability, should dedicate significant time to infrastructure development (including interaction with validators), in addition to developing its core product.

If an Appchain fails to properly incentivize validators and network validation becomes economically impractical, there is a risk that validators will shut down their hardware, with all the resulting consequences for the network. The network must ensure that validators:

* Receive timely information on updates;
* Receive timely assistance with updates;
* Are incentivized to validate:
*
  * Through lower hardware requirements, reducing overhead costs;
  * Through increased economic benefits (higher profitability due to well-designed tokenomics and delegation from the team).

The network is responsible for its validators! If the network fails to pay attention to its validators, validators have the right to act accordingly.

***

### Classification of Validators <a href="#oqyf" id="oqyf"></a>

Here we attempted to classify validators for a better understanding of validation approaches, delegation organization, contribution methods, and so on. Delegation is the main source of income from validation (usually 5% of the delegator's income). Many validators cannot be classified as a specific type, but understanding these directions is important to us:

**1. Exchange Validators**

A centralized exchange (CEX) accumulates a significant portion of tokens, offering its clients a staking service. To increase their profits, the exchange launches its validator in the network (sometimes several validators) and loads their users' stake into it. These validators are seen by many as harmful because they create a significant imbalance in token distribution in the network, negatively affecting decentralization. Also, such validators usually do not participate in the network's life. The ecosystem responds reciprocally, and the stakers of these validators often do not participate in the distribution of drops. Also, these validators usually do not participate in the voting process (it is their initiative).

**2. Large (early) Validators**

These are validators that have been validating since the ecosystem's launch and hold a significant portion of staked tokens (they are often seen in the top of the active set). Everyone knows these mastodons. It was they who stood at the origins of the ecosystem's launch, and it was they who faced a bunch of difficulties, solving which allowed us to be at the current stage of development. Very often, new projects are interested in attracting such validators themselves (because it positively affects the project's image) and themselves send them a significant portion of their own tokens. Such validators are a full-fledged significant part of the ecosystem, often actively participating in its development, participating in open discussions, visiting meetups, actively developing their products and content.

**3. Media Validators (humanitarian validators)**

These validators build work to attract delegations around working with the community. The goal is to attract the community to delegate specifically to them. There are many ways to attract community delegation. Let's consider the main ones:

financial (deduction of part of the income by generating their tokens and allocating them to their delegates); generating media content (videos, articles, streams, creating thematic chats, channels, and other platforms where users are provided with interesting content). Such validators are always in sight, carry increased reputational costs, and their economic state directly depends on community loyalty.

**4. Tech Validators**

These are validators who contribute to the network by creating useful dApps, scripts, etc. The work of such validators in terms of receiving delegations is more focused on working with the project itself.

**5. Testnet Validators.**

This is a separate part of validators that joins the project at an early stage of launch (testnet), contributes to help the network get up and running, identify and fix bugs, and prepare for the mainnet launch. It should be noted that at this stage, the validator bears the expenses for their own infrastructure, constantly monitors updates and works to fix bugs, but has no guarantees of return on investment. These validators aim to become so-called genesis validators and enter the mainnet with a delegation from the network. Often, such validators have their own channel (chat). Also, after receiving rewards for the testnet, such validators often make agreements and provide funds to a partner validator, while shutting down their own infrastructure and not going into the mainnet, earning rewards for the testnet.

**6. Project Validators.**

There are examples of projects (built on top of the network) that raise their own node, thereby contributing to the network they work on. Usually, such validators run delegations of their own tokens and tokens of their project's users.

Of course, there are very few validators that fit into one specific category. Often, a validator contains several characteristics and works in several directions to attract delegations.

The classification is open for discussion. We welcome suggestions.

### Conclusion <a href="#nkzl" id="nkzl"></a>

It is up to you to judge how well we have managed to present information about validation in the Cosmos ecosystem. We are always open to suggestions and ready to make changes and additions if it is not only beneficial to us. We are grateful to everyone who will help spread this material to provide educational assistance to the community.

Writing this article is not intended to gain economic benefits and is motivated by the authors' responsibility to contribute to educational assistance to the community.
