# Canto

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

The Canto concept is built around the idea of creating true decentralization.

After the appearance of DAI in late 2017 the main achievements of DeFi became decentralized exchanges (Uniswap, Sushiswap), lending platforms (AAVE, Compound) and stablecoins (DAI, USDT, USDC).

However, as each DeFi protocol developed, each came to the launch of its own management token with the main value being the receipt of rent from users.

Canto, on the other hand, uses a completely different approach, making the launch of the main DeFi protocols as public service protocols or Free Public Infrastructure (FPI).

For example, Canto DEX is unmanaged and cannot be updated. It will forever be in the same state as it is now. No tokens will be launched, no additional fees will be introduced. This is a desire not to exploit its user.

The Canto Lending Market is controlled by Canto stakeholders as only they are interested in the development of the ecosystem and creating the best conditions for network developers and users, and therefore profit extraction is not their main goal. In the case of the NOTE unit of account, the fees charged for stabilizing its price will be directed to the Treasury. The algorithm responsible for adjusting this interest rate is designed to change the interest rate to promote a less volatile value, not to maximize income. All interest paid by borrowers will be distributed among creditors without taking commissions at the protocol level.

With such methods, the Canto team expects the network to naturally develop in the direction chosen by users themselves, leading to the formation of a truly decentralized healthy ecosystem without the eternal pursuit of money by protocols.

### Principles of Canto: <a href="#6blb" id="6blb"></a>

\- Liquidity is a public good. There is no commission for liquidity providers (LP). Liquidity should be free for everyone, from traders to protocols.

\- No monetization of basic DeFi protocols. No token control, no elite circle of individuals capable of making decisions. Development in the interests of users, not the creators' interests of filling their pockets.

\- Minimalism. Where possible, Canto deliberately avoids creating its own user interfaces. Thus, Canto DEX has no interface. It can only be interacted with through third-party aggregators or directly with the smart contract.

\- There is no official fund. The team is independent and anonymous. No outside influence. No ICO. No vesting. No venture investors.

### Canto DeFi Protocols <a href="#qcay" id="qcay"></a>

#### **NOTE token**

NOTE is over-collateralized and algorithmically rebalanced regularly to a value of 1$.

NOTE cannot be created like stablecoins, it can only be borrowed from the smart contract associated with the Canto Lending Market (hereinafter CLM). All the interest charged for holding NOTE goes to the Treasury and is managed exclusively by Canto DAO.

Since NOTE cannot be created, only borrowed, the smart contract uses interest rates to manage the circulating supply of NOTE and, indirectly, its price. The interest rate on NOTE automatically increases or decreases every 6 hours depending on the market price of NOTE. The algorithm responsible for adjusting this interest rate is designed to drive a more stable value, not maximize profits. If NOTE is trading below 1$, the interest rate is increased to increase the incentive to buy NOTE on secondary markets and lend through CLM. If NOTE is trading higher than the dollar, the interest rate decreases to make borrowing NOTE from CLM and selling it on secondary markets more attractive. Each interest rate epoch will last for 6 hours, and the interest rate will be adjusted by 0.25 (correction factor) of the difference between the NOTE price and 1.00 dollar.

For example, in the current epoch, the interest rate on NOTE is 4%, and the exchange rate is 1.04$, then in the next epoch, the interest rate will be determined by the formula newInterestRate=max(0,(1-1.04)\*0.25+4%)=3%.

If NOTE is trading above 1$ - the interest rate decreases to weaken the price of NOTE. If NOTE is trading below 1$ - the interest rate increases to strengthen the value of NOTE.

And most importantly, no one can change the way NOTE works, it will always follow the specified algorithm forever.

If we simplify the idea, NOTE can be called a stablecoin, but it is not. According to the team, a stablecoin should always equal the base unit (e.g., one dollar), while NOTE strives for 1$, but does not equal it.

Important: no one has tried this yet, and there may be unknown design problems. Please limit your financial risk in Canto only to the money you can afford to lose. Many things Canto is trying for the first time, and there is a great risk of loss.

​[**Canto Lending Market(CLM)**](https://canto.io/lending)​

<figure><img src="https://2989248415-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FNLXjhNAjOAqCX49dO0ql%2Fuploads%2Fdmm1EYuLT0DhEhNOpwp7%2Fimage.png?alt=media&#x26;token=095e5709-bf90-4e1f-b1bf-120cdb13e8aa" alt=""><figcaption></figcaption></figure>

CLM is controlled by Canto stakeholders who are interested in developing the ecosystem and creating the best environment for both developers and DeFi users. As a result, they have no incentive to extract profit at an applied level. The main feature of CLM is the ability to use LP tokens from Canto DEX as collateral. This collateral is placed on the credit market as an offering, but users cannot borrow LP tokens.

#### **Canto DEX** <a href="#canto-dex" id="canto-dex"></a>

To prevent the possibility of predatory evolution towards a money chase, Canto DEX: cannot be improved, does not have an official interface, operates indefinitely and without the ability to charge fees. At present, the main interaction with Canto DEX takes place through the DEX aggregator [Slingshot](https://app.slingshot.finance/swap/CANTO).

<figure><img src="https://2989248415-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FNLXjhNAjOAqCX49dO0ql%2Fuploads%2FkMArg9gPNxxfjYbiK3m7%2Fimage.png?alt=media&#x26;token=a182ed05-d86b-4892-8b1e-4001ead973ba" alt=""><figcaption></figcaption></figure>

Canto DEX is an AMM and supports classic xy=k swaps and concentrated liquidity pools.

To provide liquidity on Canto DEX, users can supply liquidity on the website. Users who provide liquidity receive LP tokens, which can be used in CLM.

The list of possible liquidity pools can be found below:

<figure><img src="https://2989248415-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FNLXjhNAjOAqCX49dO0ql%2Fuploads%2FJuVFMU3LodUWGVx0o5hc%2Fimage.png?alt=media&#x26;token=b6bdbf6a-1eb0-40d1-bc23-3ff15a924d07" alt=""><figcaption></figcaption></figure>

All of the above are applications initiated by the Canto team, but there are also user applications.

#### ​[**Alto**](https://alto.build/)​ <a href="#alto" id="alto"></a>

A zero-commission NFT marketplace (in line with the Canto ideology) with a nice jazz accompaniment (the author wrote the entire breakdown with an open tab).

Below are the top collections on Canto as of February 9, 2023.

<figure><img src="https://2989248415-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FNLXjhNAjOAqCX49dO0ql%2Fuploads%2FuxuefdWkLRk7uDBc6AoS%2Fimage.png?alt=media&#x26;token=8af61f72-3b08-44c7-b309-e8eee6d11524" alt=""><figcaption></figcaption></figure>

[**Cantoswap**](https://www.cantoswap.fi/)​

A fork of Uniswap with its own token - [MATRIX](https://dropstab.com/coins/matrix-3)​

#### ​[**CantOHM**](https://app.cantohm.money/#/)​ <a href="#cantohm" id="cantohm"></a>

A fork of Olimpus with its own token - [cOHM.](https://dropstab.com/coins/cantohm)​

Currently, they are developing a Liquid Governance Derivative (LGD).

#### ​[**Y2R**](https://y2r.finance/)​ <a href="#y2r" id="y2r"></a>

Simple, it converts APR to APY and makes your farming more efficient.

You can find a complete list of launched protocols on DefiLlama. But keep in mind that Canto has only recently been launched, and all applications are just appearing on the wave of Canto's success and are made in a hurry. Check everything several times before putting your funds in and only put in an amount you can afford to lose.

### Technical Features of Canto <a href="#p6pg" id="p6pg"></a>

Canto network is a sovereign network built using the Cosmos SDK and custom modules. The Cosmos SDK networks can be formed, created, and interacted with using the Ignite command-line interface. Canto supports the EVM and uses the Ethermint module, which deploys the EVM runtime environment, allowing Solidity code to be deployed directly from the Ethereum network.

Canto has its own [bridge](https://canto.io/bridge) between CosmWasm and ERC-20.

Block creation in Canto takes half the time of Ethereum, taking 6 seconds compared to 12 seconds respectively.

The active validator set consists of the top 100 largest participants.

Canto has undergone 3 audits - [one](https://code4rena.com/contests/2022-06-canto-v2-contest), [two](https://code4rena.com/contests/2022-06-canto-contest) and [three](https://code4rena.com/reports/2022-07-canto).

### Tokenomics <a href="#nam4" id="nam4"></a>

CANTO is the native token of the Canto network. It is used to pay for gas fees in transactions and can also be used for staking to protect and manage the network. At the time of creation, the initial total supply of CANTO is one billion tokens.

The initial circulating supply of CANTO is distributed as follows: 130 million CANTO (13%) for early investors, 20 million CANTO (2%) for early Canto users who participated in the test network. The remaining total supply of CANTO is allocated according to the Canto DAO votes: 450 million CANTO (45%) for long-term liquidity mining that will be distributed over the next 5-10 years. 350 million CANTO (35%) for medium-term liquidity mining that will be distributed in the coming months. 50 million CANTO (5%) for future development grants to the network.

To maintain the security of the Canto network, the total maximum supply of CANTO increases over time at a constantly decreasing rate. All tokens from inflation are distributed among CANTO stakers proportional to their share in the network. Early participants in Canto propose that these releases be structured in 30-day periods with daily rewards distribution. During the first 30 days, CANTO will increase by 19.84% annually. In subsequent periods, the Canto DAO will vote on adjusting the APR as necessary. Over time, the inflation of CANTO should tend towards zero. As of February 9, 2023, stakers receive 20.3% annually.

### Conclusion <a href="#ggai" id="ggai"></a>

Canto is an intriguing experiment supported by Satoshi Nakamoto's ideology. While the ecosystem and project development are still in their early stages, Canto has gained popularity so quickly that it could take things to the next level. Experimenting with everything, including tokenomics where there are no tokens for the team and ending with the algorithmic calculation unit NOTE, everything about Canto is an experiment. It will be interesting to see where all this leads.

### Links: <a href="#vlxn" id="vlxn"></a>

​[https://canto.io/](https://canto.io/)​

​[https://docs.canto.io/](https://docs.canto.io/)​

​[https://twitter.com/CantoPublic](https://twitter.com/CantoPublic)
