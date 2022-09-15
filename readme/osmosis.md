# Osmosis

![](https://img2.teletype.in/files/50/71/507178a3-549e-41ef-b704-83e2f9f50b51.png)

## Osmosis

Good DEX is a necessary part of any blockchain ecosystem. DEXs allow you to attract liquidity to the network, invest in projects, swap tokens and generally provide a strong economic model. The most significant DEX inside the Cosmos ecosystem is Osmosis. It has the largest liquidity, trading and commissions volume among other Cosmos based DEXs.

### What is Osmosis

Osmosis is a high-tech AMM (automated market maker) protocol that allows you to run customized liquidity pools with a wide range of adjustable parameters. It was founded in January 2021 by Sunny Aggarwal, Josh Lee and Dev Ojha. All three are experienced blockchain developers who worked at Tendermint, where they developed the architecture of Osmosis DEX. Their company, Osmosis Labs, is currently responsible for developing and code writing. Inspired by projects such as Balancer and Uniswap the Osmosis team set out to provide users and developers with best-of-breed tools for development and customizing AMMs that go far beyond the functionality of a simple swap platform.

### **How Osmosis works**

At its functional level, Osmosis works like any other AMMs - tokens are locked in the liquidity pools via smart contract, which ensures the functioning of trades (swaps). Liquidity providers deposit their tokens in the liquidity pools and receive LP tokens (liquidity pool tokens). They also earn commissions generated in the pool (proportionally to their share). The pricing model of Osmosis DEX is also standard - the share of a token in a pool must remain constant. What makes Osmosis so remarkable and unique we will explain later.

### **Incentives to provide liquidity**

Osmosis uses two key mechanisms to provide the necessary liquidity: the bonded liquidity gauge and exit fees.

#### **Share of provided liquidity**

This mechanism allows liquidity providers to get extra (in addition to the yield from the commissions received by the pool) rewards. These rewards are based on their share in the liquidity pool and on period they lock their LP tokens in this pool. 45% of the OSMO tokens daily issue is allocated to this extra reward. Every user has multiple options (these options are called “gauges”) of the locking period of their LP tokens. For example, in the ATOM/OSMO pool there are options for a day, a week and a month period. Let’s call them gauge 1, gauge 2 and gauge 3. In this case the extra rewards are distributed between these options in a certain way.

Some practical cases:

1\. John adds his assets to the pool, receives LP tokens, but does not want to lock them. Then his income will consist of commissions received by the pool, he will not receive any additional remuneration.

2\. John chooses option 1. Now his income consists of pool commissions and additional remuneration provided by option 1 (of course, proportionally to the share of LP tokens of John's total share of LP tokens receiving remuneration from option 1).

3\. John chooses option 3. Which means that now his income in addition to the pool commissions will now include additional rewards provided for option 1, option 2 and option 3. In short, the guy is taking life by the maxes.

Users also have the option to split their LP tokens into different gauges, for example, send 50% to the first gauge and 50% to the second gauge.

Not all liquidity pools can receive extra rewards in OSMO tokens. OSMO stakers choose the pools, which will receive this reward and the proportion of distribution among the various gauges, by on-chain voting. For this purpose stakers assign so-called "allocation points" to pools and their gauges. For example, if a vote results in a total of 20 allocation points and 2 of these allocation points are allocated to gauge 1 of pool X then that gauge will receive 2/20 = 10% of all extra rewards.

Besides the "official" extra rewards (45% of the daily OSMO token issue) any project or user can add its own additional reward and set gauge distribution for some specific pool.

Bonded liquidity gauge has another important function - they serve as a protection against "vampire attacks". When users have to lock their funds to get additional income, third-party DEXs have no opportunity to entice liquidity providers to their platform with a short-term super profitable offer.

You can learn more [here](https://medium.com/osmosis/osmosis-liquidity-mining-101-2fa58d0e9d4d).

### **Exit fee**

Exit fee is a small percentage of LP tokens which is charged from the liquidity provider when he sends a request t0 withdraw funds from the pool. In so doing, these LP tokens are burned.

### **Liquidity pools customization**

Liquidity providers can experiment with different market making functions. It means that unlike other AMMs, Osmosis doesn't have any specific mathematical function by which liquidity pools work (for example, Uniswap uses x\*y = k function, where x and y are an amount of the first and the second tokens in the pool, and k is a constant value (If you do not know about the concept of Uniswap, we recommend you to learn about it more, because it is a basic knowledge). Pool's parameters such as the initial share of tokens (the share of a certain token in a pool), swap commissions and TWAP calculation (Time-Weighted Average Price, something like average price over a certain period of time) are chosen by pool founders. But LP token holders of each pool have the right to vote on any changes in the pool. Their voting power is determined by their LP share and by how long users have been a liquidity provider for this pool. The customization of pools in the original vision of the Osmosis team should serve to find optimal pool parameters experimentally. Moreover, such flexible settings should allow for new types of DeFi activities (such as options, AMM with dynamical commissions, etc.) on Osmosis in the future, as well as help pools function better during periods of high volatility.

### **Superfluid staking**&#x20;

Multi-chain ecosystem has one big disadvantage – a difficulty of providing network security which is achieved via staking. For example, ETH 2.0 network's security provided by Ether stakers, Polkadot ecosystem security provided by relay-chain. Both have a large number of locked tokens, so there is a high security level. In its turn, the Cosmos ecosystem at the moment does not have its own "core" responsible for security. That's why there can be a problem when on the one hand, native tokens are necessary for staking and securing, and on the other hand, native tokens are necessary for providing liquidity. Osmosis has figured out how to kill two birds with one stone. Superfluid staking is a mechanism that allows you to use some of the OSMO tokens from liquidity pools for their simultaneous staking.

A small example:

A user adds $1000 worth of liquidity to the ATOM/OSMO pool ($500 in ATOM tokens and $500 in OSMO tokens) and chooses a lock period in the pool that guarantees him a certain APR (annual percentage rate). Let this APR = X. The user then has the option to stake some of his OSMO tokens locked in the pool. How much of those tokens the user can add to the staking is determined based on security considerations. Initially that portion was equal to 50% of the OSMO tokens. So in our example the user will receive income X for providing liquidity to the pool and additional income Y for staking OSMO tokens by the equivalent of $250 (50% of $500 in OSMO tokens added to the liquidity pool). It is worth considering that income Y is a dynamic variable as the ratio of ATOM/OSMO tokens constantly changes as their price changes relative to each other. These changes are accounted for by TWAP (time-weighted average price) oracle.

_Official video about superfluid staking is_ [here](https://www.youtube.com/watch?v=JRBOUrrKa3s)

Superfluid staking allows liquidity providers to earn more rewards (liquidity pool rewards + staking rewards) while improving the security of Osmosis (more OSMO in staking).

### **Osmosis Frontier**

![](https://img4.teletype.in/files/b2/0d/b20d0dcc-cba5-46bc-9f82-cae60dc757c1.png)

There is a problem associated with the fact that there is no efficient and secure multi-chain bridge. Using multiple bridges creates different wrapped token variations of the same asset (e.g. you want to transfer Ether to the Cosmos network using bridge X so you get xETH, if you use bridge Y you get yETH), this firstly dilutes liquidity and secondly causes confusion for ordinary users who see a bunch of different wrapped variations of the same token and do not know what to choose. Osmosis categorically doesn't want that to happen on their platform but waiting for the perfect bridge to appear isn't an acceptable option either. So they launched a kind of experimental DEX - Osmosis Frontier, where any user can create their own pool with any asset. That's the wild west for any experiments (you can list even scam coins, play with pool customization or test bridges).

_This is a_ [_link_](https://frontier.osmosis.zone/) _of Osmosis Frontier !!! Remember that there is always a possibility of scam, and the pool can be empty. In this case slippage will hurt you and your deposit. So be very careful while experimenting!!!_

\*It should be noted that on the official Osmosis Medium it was mentioned that in the future Osmosis potentially will be able to display all the different wrapped versions of the same asset as a single token.

\*\* Users are able to add some assets from the Ethereum network to Osmosis using the Axelar interface. At the moment of June 2022 these assets were limited to USDC, WBTC, WETH and DAI.

&#x20;[Here](https://medium.com/osmosis/bridging-ethereum-assets-to-osmosis-a-guide-to-the-axelar-interface-ac63c16cfb98) is the link to the official guide

\*\*\* At the end of June 2022, through the integration of the Kado app Osmosis provided users the ability to directly purchase axUSDC and OSMO tokens from their credit cards or bank accounts.

More information can be found [here](https://medium.com/osmosis/osmosis-integrates-kado-for-direct-fiat-on-ramping-to-the-dex-a1a49f2cf157).

### **Tokenomics**

![](https://telegra.ph/file/d05af7bfa92167816b705.png)

The native Osmosis token $OSMO has two main functions: governance and utility.

Firstly, it is used for economic security to Osmosis via staking. When the general security feature will be launched, Osmosis is going to become a part of the Cosmos Hub. Secondly, $OSMO allows holders to participate in the on-chain voting. Thirdly, the token is used to pay commission fees and provides additional reward to liquidity providers.

It is also worth noting that the maximum supply is only 1 billion tokens, and the deflationary model is achieved by reducing the issuance of new tokens by a third each year. New tokens serve as rewards for staking, providing liquidity to pools and liquid mining. These tokens are also used as a reward for the ecosystem developers.

### **UPD**

Recently Osmosis has announced they are planning to collaborate with Polkadot and work with ERC tokens. It will be possible thanks to their integration with Axelar and Moonbeam. You can read more about it [here](https://blockworks.co/osmosis-co-founder-doesnt-see-cosmos-and-polkadot-as-competitors/).
