# Mars Protocol

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

The vision of Mars is built on Contract-2-Contract (C2C) lending, which allows smart contracts integrated with Mars to borrow assets from Red Bank for a pre-determined purpose. This will allow for the use of more funds and their more efficient utilization. For example, C2C will be deployed on Osmosis, allowing users to take an OSMO loan for farming LP on Osmosis with leverage, i.e. increasing their OSMO position for greater impact.

Red Bank is the place where all user interactions with the Mars Hub occur. This is where we deposit, take out loans, and select C2C strategies.

In Mars, there is also the concept of a Rover - account. This is a single account that reflects the overall collateralization of all open user positions and all utilized strategies. Rover - accounts were created for the optimization of lender operations, the resolution of cross-marginal C2C strategy problems, and for the convenience of managing one's positions.

This architecture provides users with the ability to cross-collateralize various strategies with leverage in a single account with a single LTV (Loan-to-Value). It's important to note that in addition to general collateralization between C2C strategies, Rover - accounts can also be integrated with other DeFi. This allows users to interact with any dApp integrated into the Mars Protocol with a single LTV at the account level. Rover - accounts will be represented as NFTs, and the wallet can contain several separate Rover -accounts, similar to sub-accounts on CEX. Rover - accounts create a "unified" DeFi experience as users will be able to access their favorite tokens, farms, and other protocols using leverage on Mars..

As Rover -accounts are NFTs, they perform the following functions:

* Identity: credit accounts can reveal their own capital in the network, a health factor, and profit/loss, giving them the ability to contribute to the network's identity and allowing them to use social functions such as leaderboards, "whale watching", copy-trading, etc.
* Transfer/Sale: users can sell or transfer their credit account to another user, including all positions within it.
* Fractionalization: users can fractionalize their credit account into interchangeable parts and sell or distribute them. Provided there are the appropriate management means, this can allow other users to effectively own a share of the user's trading activity, and a secondary market can be created for these fractional parts of credit.
* Network behavior and competence: can be tracked for creditworthiness assessment.

The team decided to launch its own appchain because there is a problem of liquidity fragmentation in Cosmos. Mars Protocol plans to integrate with all networks with liquidity using its own Mars Hub.

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

Architecture Mars Hub. Currently, only OUTPOST 1 (Osmosis) has been launched, where all features of Mars are gradually being introduced and tested.

<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption><p>OUTPOST architecture</p></figcaption></figure>

It is important to note that Mars Hub does not store liquidity for OUTPOST, but rather manages the activity that takes place on OUTPOST. In other words, if you want to use the Osmosis OUTPOST, you do not need to deposit money into the Mars network. Mars Hub manages all OUTPOST smart contracts, receives commissions from OUTPOST and distributes them among the Mars management participants. Mars Hub can be compared to a franchising company: it sets standards but leaves the interaction with customers to the discretion of individual divisions (in our case, networks). Similarly, traders and other market participants who are not interested in management are unlikely to interact with Mars Hub. Instead, the Hub serves as a coordination mechanism in the background, while users directly interact with the liquidity aggregated on each of the Mars OUTPOSTs.

So, let's summarize how Mars Protocol works for a user:

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

Users of Mars Protocol are divided into the following types:

* Validators/Stakers: protect the Mars Hub network, manage the OUTPOST, implement new features, and set Red Bank risk parameters. In return, they receive a portion of the protocol's revenues.
* Creditors: deposit assets into Mars liquidity pools, receiving a commission equivalent to the interest rate.
* Borrowers (secured by collateral): borrow assets from Mars liquidity pools, using their deposited assets as collateral. In this way, these borrowers are also depositors.
* Borrowers (based on contracts): smart contracts integrated for borrowing assets from Mars liquidity pools without collateral (since the contracts themselves will contain the collateral). Each smart contract must be approved by management with a established credit limit to reduce the risk associated with the protocol. These credit lines support Mars credit accounts, providing end-users access to credit leverage without the requirement for prior Red Bank deposits.
* Liquidators: Third parties who liquidate positions at Red Bank by settling the debt of users with insufficient collateral in exchange for a commission. The liquidation mechanism at Red Bank is classical.

### Tokenomics <a href="#c5cw" id="c5cw"></a>

The main utility of MARS is network management and protection.

Red Bank's revenue is distributed as follows:

80% of interest payments for loans go to users providing liquidity.

10% of the fees are exchanged for axlUSDC, then exchanged for MARS and sent to stakers as a reward.

The remaining 10% are converted to axlUSDC and sent to the Safety Fund. Funds from the fund will be used to eliminate the deficit within the pool and in case of any force majeure.

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

Mars Contributors include both investors and the team. These 30% will not start hitting the market until September of this year and the unlock will last for 3 years. Token Claim is a drop for Mars users from Terra, all already in the market. Community Pool is incentivization for validators, rewards for users, etc.

### Roadmap <a href="#z5et" id="z5et"></a>

<figure><img src="../.gitbook/assets/image (6) (4).png" alt=""><figcaption></figcaption></figure>

On February 8, 2023, the first OUTPOST was launched on Osmosis, and preparations are underway for the launch of C2C.

### Conclusion <a href="#hae9" id="hae9"></a>

Osmosis is the main liquidity hub on Cosmos. And Mars is the first protocol that will be integrated into Osmosis. There should be no problems with liquidity. Then integrations will go with other projects on Cosmos. And this is amazing, liquidity in the ecosystem will finally stop rotating in a pair of points, and will be dispersed to many places. But it should be remembered that all this will take a lot of time, not one or even six months. But as they say, Sic Parvis Magna.

### Links <a href="#r5ev" id="r5ev"></a>

​[https://osmosis.marsprotocol.io/redbank](https://osmosis.marsprotocol.io/redbank)​

​[https://github.com/mars-protocol/whitepaper](https://github.com/mars-protocol/whitepaper)​

​[https://twitter.com/mars\_protocol](https://twitter.com/mars\_protocol)
