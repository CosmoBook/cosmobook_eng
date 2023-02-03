# Page 1

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

Even newbie crypto-enthusiasts are well aware that stacking allows to earn a certain passive income. Also the more tokens are stacked to honest validators the harder it’s for bad actors to attack the network. However staking has its own drawback - a decrease in liquidity and the inability to perform any activity with the locked capital. To solve this problem some protocols began to offer the user so-called liquid staking. In the Ethereum network liquid staking has been used for a long time (for example Lido Finance) but in Cosmos ecosystem it has not been so common yet.

**Stride** is a blockchain designed specifically for liquid steaking. With Stride users can simultaneously generate income from both staking and DeFi activities.

Currently Stride provide a liquid staking for the following Cosmos zones:

* Cosmos Hub (stATOM)
* Osmosis (stOSMO)
* Juno (stJUNO)
* Stargaze (stSTARS)
* Terra V2 (stLUNA)

During 2023 Stride team is planning to onboard for liquid staking almost all major zones and tokens including Evmos (stEVMOS), Terra V2 (stLUNA), Injective (stINJ), Secret (stSCRT), Kava (stKAVA), Oasis (stROSE), Axelar (stAXL), Akash (stAKT), Regen (stREGEN), Sommelier (stSOMM), Band (stBAND), dYdX (stDYDX), , Kujira (stKUJI), Umee (stUMEE) and many others.

In the long term any user will be able to use Stride platform to stake any IBCv3-compatible token

## Technical architecture or how Stride works

Users stake their tokens from any Cosmos-supported network on the Stride platform and receive stTokens. At the same time platform automatically stakes native tokens into the corresponding network. In this way users can get their staking rewards and use stTokens to perform any DeFi activity and generate additional yield at the same time. There is no minimum amount for staking and rewards accumulate in real time. Unstaking is possible at any time but native tokens will only arrive in the user's wallet after the subscription period set for a particular network expires.

Let's take a closer look at the whole staking process using ATOM as an example

### Initiating the staking

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

**Step 1.** User sends his ATOM tokens to the Stride network.

**Step 2.** User initiates liquid stacking. This sends ATOM tokens from the User Account to the Module Account from which they are sent to Cosmos Hub for staking (more on this later).

**Step 3.** User receives stATOM tokens

**Step 4.** User can send his stATOM tokens to any Cosmos zone (but most often to Osmosis) for all available DeFi activities&#x20;

### Native token stacking and reward generation

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

**Step 1.** Every epoch (once every 6 hours) Stride sends ATOM tokens from the Module Account to the Delegation ICA (delegation interchain account) on the Cosmos Hub network. Stride makes a corresponding record in the depositRecord with the status of 'Stake'. (\*as we understand at this stage tokens are only received in the Cosmos Hub network but not yet staked).

**Step 2.** Each epoch (once every 6 hours) Stride uses the Delegation ICA to stake new ATOMs and also credits the staking rewards to the balance of the interchain account.

In the next epoch staking rewards for the current epoch will first go to the Withdraw ICA (withdrawal interchain account).

**Step 3**. Every epoch (once every 6 hours) Stride uses ICQ (interchain queries) to transfer the previous epoch's staking rewards to Withdraw ICA. Then 90% of these rewards are sent to the Delegation ICA, to be staked in the next epoch. And 10% of the reward are sent to Revenue ICA as a commission Stride takes for their services.

### Native tokens redeem

Users can request withdrawal of their native tokens at any time by selecting the "Redeem" option on the Stride website. Stride sends a withdrawal request and at the end of the unbonding period native tokens will go to the user's wallet.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

**Step 1.** The user initiates a redeem process. The stATOMs are sending to the Module Account.

**Step 2**. Every epoch (every 3 days, in another source we found a figure of every 4 days, in any case this is due to the fact that the Cosmos ecosystem prohibits sending more than 7 requests in 21 days period) Delegation ICA checks the native token redeem request and sends a command to perform ATOM token unbonding (the unbonding period starts).

**Step 3.** In the epoch following next after the unbonding period unstaked ATOMs are sent to the Redemption ICA.

**Step 4.** The msgClaim function sends native tokens from the Redempiton ICA to the User Account.

**\***Stride currently staked tokens to 30 different validators. Stride holders can vote to add a particular validator to the active set, as well as decide what "weight" the validators will have, i.e. what validator gets what percentage of tokens for staking.

**\*\*** 10% of the staking rewards is the only commission Stride takes.

### &#x20;A step-by-step guide how to use the Stride platform (Keplr Wallet and ATOM tokens as examples)

\
If you love to watch video guides more here is the link to Youtube [video gide](https://www.youtube.com/watch?v=Y-1snnqBx-0)

The whole process is as simple as possible and takes just a few minutes.

&#x20; 1\. Go to the Stride site. Here's the [link](https://app.stride.zone/).

2. Connect your wallet.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

The following wallets are available to choose from, we use Keplr Wallet

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

3\. Once the wallet is connected we enter the number of tokens we want to stake. As mentioned above you can stake any amount even the smallest. Then press Liquid Stake.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

4. A menu appears showing the next steps we have to go through after we click Start Staking. Everything will happen automatically, we just need to give our approval for the transfer. There are essentially only 2 steps here not 4 - transferring ATOM from Cosmos Hub to the Stride network and staking ATOM. The whole process took us about a minute but may takes a little longer if the network is overloaded.

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

5. Our ATOMs are staked, we will soon be rich, but to speed up our enrichment process we can send our stATOMs in available liquidity pools and receive a certain APR. Remember that providing liquidity to pools has some risks and the APR can change!

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

The process is also quite fast and intuitive. But we decided not to do any DeFi degen things as for now but to continue the review of the Stride.

6\.  When you decide to unstake your ATOM, you should go to the Unstake menu and start a reverse process. Keep in mind that the unbonding period is from 21 to 24 days, if you urgently need to get your ATOM back, you can swap stATOM to ATOM on Osmosis or another DEX that has this trading pair.&#x20;

### Stride's roadmap and plans for 2023

1\.       Implementation of ICS V1 - Security Interchain. Stride intends to connect their network to ICS as soon as it is launched. This means that Stride's security will be equal to Cosmos Hub’s security itself.

2\.       Using the IBC rate-limiting model (limiting the possible number of tokens withdrawn from the network per day). This model is already used by Axelar and Osmosis and its purpose is to mitigate possible damage in case of network hacking.

3\.       Stride's code has already been audited three times by independent auditors by this point (January 2023), a trend that will continue in 2023 (in general, at least according to Stride, they pay very close attention to network security).

4\.       Launch a bug bounty program in the first quarter of 2023 with total rewards of 500k STRD tokens

5\.       Liquid Governance. This is more of a general direction in the development of the Cosmos ecosystem. The goal is to give users ability to use liquid staking and still participate in the native networks governance.

6\.       UX improvements, such as adding Liquid Staking module (new Cosmos SDK module being developed by Iqlusion), improving platform interface, reducing Liquid Staking process to just one step (IBC transfer and transaction in Stride network will be done with one click), etc.

7\.       Use Bonded Liquidity Markets - an opportunity for instant unbonding. The principle is as follows: if one user wants to stake 100 tokens and another user wants to unstake 100 tokens, they make some kind of "exchange" between themselves.

8\.       Allowing users to stake their stTokens to certain validators from the Stride validators set.

9\.       Using stTokens in Ethereum network (via Axelar) and NEAR/Polkadot networks (via Composable Finance).

10\.       Staking derivatives from other ecosystems (using GMPs). \*but as we understood, this is unlikely to be possible in the short term, but projects such as Axelar and Composable Finance are actively developing in this direction

### Tokenomics

The Stride network's native token is the STRD token. The total supply is 100 million STRD. Unlike many other projects, which try to “stretch” emission of their tokens for a long period, Stride went the other way – 18 months after the launch in circulation will already be 50% of all tokens, and after 36 months - 95%.

On the picture below you can see the Token allocation diagram and the Emissions Schedule graph.

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

#### STRD tokens are issued in 3 ways:

1\. **9,450,000** STRD tokens will be issued block-by-block. The halving period is 1 year

2\. **31M** tokens go for the reward pool. Who and how to distribute these rewards is determined by Stride DAO. However in order to make the distribution of tokens more predictable certain quotas are set - 20M tokens must be distributed in the first year, and the rest in subsequent years.

3\. **16.7M** tokens go for Stride partners and 24.2M tokens for core contributors. This tokens are vested linearly over two years with a one-year cliff. Vesting tokens are staked to secure the network, but are not eligible for staking rewards. This ensures high network security without diluting staking rewards.

Read more about the of STRD distribution [here](https://stride.zone/blog/stride-tokenomics) and [here](https://stride.zone/blog/strd-tokenomics-updates-and-clarifications).

STRD token as many other tokens on the Cosmos ecosystem has both governance and utility functions. As mentioned above, 10% of the liquid-stacking rewards go to the protocol. Initially all of these rewards will go to the Stride Foundation but STRD holders may vote for any other distribution of these rewards in the future\*. STRD holders also vote on key decisions such as choosing a set of validators, "weight" of those validators, distributing rewards, managing community pool funds, adding new features to the protocol and so on.

\*At the end of January STRD holders voted that 100% of the commission for Stride’s services would go as rewards to STRD holders.

### Links

1\. Stride's official website: [https://stride.zone](https://stride.zone/)

2\. All documentation: [https://docs.stride.zone/docs](https://docs.stride.zone/docs)

3\. Blog: [https://stride.zone/blog](https://stride.zone/blog)

4\. Twitter: [https://twitter.com/stride\_zone](https://twitter.com/stride\_zone)

5\. Discord: [https://discord.com/invite/e4bzG6zNdf](https://discord.com/invite/e4bzG6zNdf)
