# Duality

<figure><img src="../.gitbook/assets/image (2) (2) (2).png" alt=""><figcaption></figcaption></figure>

**Duality** is a decentralized exchange offering users and protocols a wide range of different customizations. Duality is scheduled to launch in 2023 as an app-chain on the Cosmos network. The main idea behind Duality is to create a trading platform that would take all the AMM and Orderbook advantages, but be devoid of their disadvantages.

<table><thead><tr><th width="108.33333333333331"></th><th>AMM</th><th>OrderBook</th></tr></thead><tbody><tr><td>Pros</td><td><ol><li>Liveness</li><li>Computational efficiency</li><li>Composability</li></ol></td><td><ol><li>Capital efficient</li><li>Tried and tested</li><li>Familiar</li></ol></td></tr><tr><td>Cons</td><td><ol><li>Overly complicated</li><li>Unsustainable emissions schemes</li><li>Capital inefficient / high slippage</li></ol></td><td><ol><li>Computationally inefficient</li><li>Non-composable</li></ol></td></tr></tbody></table>

Probably even newbie degens already know that the simplest formula by which AMM (automatic market maker) can work is the one proposed by Uniswap:

$$
x*y = k
$$

{% hint style="info" %}
```
x – is the number of the first token in the trading pair, 
y – is the number of the second token in the trading pair,
k – is a constant.
```
{% endhint %}

In this way token swap can be simply and conveniently implemented. However this approach requires a lot of liquidity and is prone to so-called price slippage during large purchases or sales. To get rid of these disadvantages of AMM bright crypto minds come up with new mechanics and models (for example, Uniswap V3 or Curve’s Stable Swap). One of the projects developing a better AMM is Duality.

**Duality** is so named precisely because it tries to take the best of both worlds (AMM and Order book), getting rid of their shortcomings.

### How it works

**1. Simplicity and flexibility**

Duality uses liquidity pools with a constant price\* which makes it much easier to create AMMs with concentrated liquidity. Duality also offers a set of tools through which you can customize the AMM (change the static or dynamic curve according to the required precision).

\* Instead of providing liquidity to one specific pool liquidity providers provide it in specific price ranges (constant-price pools). You can read more about this [here](https://duality.gitbook.io/duality-documentation/concepts/liquidity-pools).

**2. Ability to use limit orders and create an arbitrage strategy**

**3. Shared liquidity**

Any AMM curve created on Duality uses shared liquidity pools which together with concentrated liquidity (like the one used by Uniswap V3) results in less price slippage and makes any price manipulation to be difficult.

**4. MEV protection**

Duality can enforce safeguards to prevent any "dirty" MEV activity (i.e. actions such as sandwich attacks, TWAP manipulation, etc.). Duality also directs MEV profits back to the liquidity pools (\*the official documentation says there will be more information on this topic soon).

Thus Duality seeks to solve the main problem of liquidity providers who are constantly losing their money while rebalancing assets in the pool and also suffer from MEVs. The main goal is to get the maximum benefit exactly from the liquidity provider.

### Duality team

It's great to see the Cosmos ecosystem attracting talented developers from Ethereum:&#x20;

[@eljhfx](https://twitter.com/eljhfx) is a DEX / AMM researcher who previously led a research team and worked with teams such as Balancer & Trader Joe. [https://www.linkedin.com/in/elijah-fox-765a07174/](https://www.linkedin.com/in/elijah-fox-765a07174/);

[@nicholasevans14](https://twitter.com/NicholasEvans14) is an Ethereum OG developer who worked at ConsenSys and was an engineer and co-founder of several successful EVM protocols. [https://www.linkedin.com/in/nicholas-evans-b1592b151/](https://www.linkedin.com/in/nicholas-evans-b1592b151/);

[@ronmiasnik](https://twitter.com/RonMiasnik) is a production/operations specialist. He sold his own startup SaaS (Adora) and has worked at several startups and large tech companies (Microsoft, Houzz, JFrog). [https://www.linkedin.com/in/ronmiasnik/](https://www.linkedin.com/in/ronmiasnik/);

Duality is supported by [@BainCapCrypto](https://twitter.com/BainCapCrypto), [@robotventures](https://twitter.com/robotventures), [@Galileo\_xyz](https://twitter.com/Galileo\_xyz) and [@strangelovelabs](https://twitter.com/strangelovelabs).

They also work closely with big crypto names:

[@alexhevans](https://twitter.com/alexhevans), [@GuilleAngeris](https://twitter.com/GuilleAngeris),[ @tarunchitra](https://twitter.com/tarunchitra).&#x20;

### What Duality will bring to crypto sphere (according to the Duality team)

Efficient liquidity usage in the stabelcoins pools. AMM on the Duality platform allows you to implement almost any trading strategy and apply a lot of customization to liquidity pools. Trading with no slippage and minimal or even zero commission costs is possible.

Constant price pools provided by Duality may be of interest to traders accustomed to working in traditional currency markets. Such pools guarantee low volatility and narrow spreads. In addition protocols built on top of Duality can act as plug-in DeFi applications for trading ForEx (foreign exchange) tokens.

Thanks to the flexibility and features of its AMM, Duality can become a suitable platform for trading various derivatives and provide an opportunity for convenient trading both on the traditional strategy (based on spreads) and on the more typical DeFi strategy (based on the commissions income).&#x20;

### Conclusion

There is too little information about the project at the moment to prepare a full review. We will follow the updates and add new infirmation as more details emerge. &#x20;

We've concluded that the team knows how to do math and knows how to do AMM (you can check it by reading their [Git](https://github.com/duality-labs)), but all of the above is just taken from official sources, it sounds to be pretty good but who knows how it will be in practice).&#x20;

Interestingly that Duality has no plans to launch their token in the short term. This means that as for now fees will be paid entirely in $ATOM.

### Links <a href="#9fuu" id="9fuu"></a>

1. **Litepaper:** [https://blog.duality.xyz/litepaper/](https://blog.duality.xyz/litepaper/)
2. **Twitter:** [https://twitter.com/dualityxyz](https://twitter.com/dualityxyz)
3. **Website:** [www.duality.xyz](http://www.duality.xyz/)
4. **GitBook:** [https://duality.gitbook.io/duality-documentation/](https://duality.gitbook.io/duality-documentation/)
5. **Blog:** [https://blog.duality.xyz/](https://blog.duality.xyz/)
6. **Github:** [https://github.com/duality-labs](https://github.com/duality-labs)
