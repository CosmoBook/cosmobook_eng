# Nomic

![](<../.gitbook/assets/image (2) (1) (1).png>)

## Introduction <a href="#nomic" id="nomic"></a>

**Nomic** is a PoS Bitcoin sidechain, powered by the Tendermint consensus protocol. Nomic aims to provide fast circulation and utilization of tokens fully backed by BTC.

These tokens are referred to as nBTC. The chain is parallel to the Bitcoin timechain mainnet. nBTC tokens can be exchanged for BTC at a 1:1 ratio.

The **security** of the PoS chain is improved by periodic synchronization of the Nomic sidechain and Bitcoin timechain: the clients, synchronized with the chain, can always rely on Proof-of-Work security, while confirming blocks consensus.

The **Tarpoot upgrade** set the foundation for the Bitcoin multisig contract development for the Bitcoin bridge administration.

### Bitcoin Reserve Management

A reserve of Bitcoin is maintained through a Bitcoin multisig contract, where signatories of the reserve who control the funds, are all sidechain validators. A voting power of each validator is represented as a share of signature in multisig.

📌 Before the Tarpoot implementation multisig could not be realized with more than 16 participants. Now it is possible to operate multisig with a whole validator set (usually >64).

The terms of the funds disbursement are enforced on the blockchain through the reserve witness script.

### Reserve script

{% hint style="info" %}
Script is a set of programmed instructions on Bitcoin. The script controls the mechanism of locking and unlocking scripts.
{% endhint %}

The script works as follows:

**Base signatory set**

To disburse funds from the reserve, more than 2/3 of the validator set must sign the transaction. NOMIC calls this subset of validators the base signatory set.

**Fallback script**

If one of the conditions is not met, the disbursement will be allowed through the mulltisig, which contains all signatories' public keys and their voting power. Nomic calls this a fallback script.

It is expected that in most cases the signature will be approved through the basic scenario: PoS validators have been shown to have extremely high uptime. However, the fallback script will be used if:&#x20;

* At least one signatory of the base signatory set is offline&#x20;
* The base signatory set does not complete the aggregated signatures after the time out.

### Deposit BTC into reserve pool

To move funds into the reserve pool, depositors need to send a Bitcoin transaction to the reserve script, which is modified to contain an extra script in its script path tree, that indicates where the nBTC should be credited on the sidechain (this scheme is called Script Path Commitment Scheme). A depositor should indicate the desired destination address in Nomic.

{% hint style="danger" %}
_Detection of deposits by relayer nodes_

Output of the above script has a unique hash, since the destination address on the sidechain is unique. This meant that relayers could face an issue with the matching of Bitcoin transactions with the reserve script. To solve this problem, relayers will have to keep the sidechain's destination address, receive from depositors, and match each Tarpoot output, which they see in the Bitcoin transaction with all active validator sets and possible destination addresses.
{% endhint %}

**Deposit Finality**

To avoid the risk of providing the pegged nBTC on the Nomic sidechain while Bitcoin deposit-transaction refund, the system should consider a deposit final until it has been confirmed sufficiently deep on the Bitcoin timechain. It is achieved through the waiting, the time needed to mine blocks, that consist of the equivalent amount of the waiting BTC deposits.

For instance, if 8 BTC is deposited, and 6.25 BTC is mined per block on mainnet, then waiting for 2 confirmations is a safe depth since a miner would likely consume more costs in a chain reorg than in gains they made from the fraudulent deposit.

The total number of BTC waiting for the deposit, consists of the amount of all deposited individual sums.

A deposit progresses from "pending" to "final" in a FIFO ordering (first in, first out). The scaling confirmation block counts for all deposits based on the total waiting time.

{% hint style="info" %}
For example, the total quantity of BTC is deposited by 3 depositors, in the amount of 3 BTC, 5 BTC and 4 BTC. The block reward is 6,25 BTC. Then, the confirmation of 2 blocks and almost 20 minutes are required. The first deposit is confirmed in 5 minutes (3/1220), the second is in 8 minutes 20 seconds (5/1220), and the third deposit is confirmed in 20 minutes.
{% endhint %}

**Speculations on Deposits**\
The user-experience of the system using, based on the above-described conservative approach, is worse in comparison with traditional centralized platforms (which usually wait for only the 1 or 2 blocks confirmation). Thus, a market for speculation on transaction confirmations was created. A depositor could sell the unconfirmed deposit tokens to traders, who are sure that at the end the deposit will be confirmed.&#x20;

The price depends on such factors as the estimated risk, the intermit value of money before the confirmation of deposit and the liquidity on the market of unconfirmed deposits.&#x20;

The probability of deposit cinsirmation is evaluated with the data such as the presence of transaction in the BTC miners' mempools, if there is a possibility to apply to the transaction replace-by-fee, the state of a hashrate, indicating the possibility of reorganization, info on a depositor, etc.&#x20;

{% hint style="info" %}
replace-by-fee is a mechanism that allows an unconfirmed transaction in a mempool to be replaced with a different transaction with higher commission and another recipient's address. It also allows the changing of tokens transfer parameters in the Bitcoin mempool.
{% endhint %}

### Deposit Reclamation & Unbonding Period

It may be possible that the deposit transaction takes a long time to confirm due to, for example, an outdated reserve script. The sidechain does not honor deposits to outdated reserve scripts, since the signatories are not necessarily available anymore, or may have unbonded their stake. This can lead to loss of funds.

To solve this problem, the reserve script is modified to make it possible for the depositor to reclaim the funds after a given time or block height. The unlock period on the sidechain increases.

**Deposit Reclamation:**&#x20;

After the timelock is set to a time or block height, significantly exceeding the time it would take for the deposit transaction to be confirmed on the Bitcoin network, relay to the sidechain network, collection into a checkpoint, and the checkpoint be confirmed on the Bitcoin network. It is expected that this could be on the order of 1 day or 144 blocks in the future. The choice of this field can be left up to the depositor, but a minimum value should be enforced by the network to prevent a denial-of-service attack where the depositor reclaims the deposit just before the sidechain signatories are about to broadcast their spend of it.

**Unbonding period**

If the deposit transaction is sent, and the validator set has changed a bit before the confirmation, the deposit still should be considered valid. In order to ensure this, the unbonding period on the Nomic sidechain will be much more than the time of proceeding the deposit-transaction.

### BTC Deposit on Sidechain: nBTC

Once a relayer node detects a valid Bitcoin transaction which has outputs matching the above format, it will broadcast a deposit proof to the sidechain network, which contains:

* the bytes of the complete deposit transaction data&#x20;
* the address bytes committed to in the deposit transaction (when using the script path commitment scheme)&#x20;
* the hash of the Bitcoin block which contained the deposit transaction&#x20;
* the Merkle branch proving the transaction was included in the Bitcoin block

These components are enough to guarantee the BTC deposit. After the sidechain network receives a valid deposit proof, it will then mint Bitcoin-pegged tokens on its ledger, paid out to the destination address committed to by the depositor. nBTC can be transferred, used in smart contracts, or burnt to trigger a withdrawal from the reserves paid to a given destination on the Bitcoin blockchain.

#### **Checkpoints** <a href="#depositing-and-withdrawing-bitcoin" id="depositing-and-withdrawing-bitcoin"></a>

Periodically, the network will make transactions on the Bitcoin blockchain which are called checkpoints.

They are spent from the reserve wallet and serve the purpose of:

* collecting deposits&#x20;
* updating the reserve script to reflect the latest signatory set&#x20;
* disbursing pending withdrawals&#x20;
* providing a way for light clients to verify the state of the sidechain network
* &#x20;invalidating the previous "emergency disbursal" transaction (mentioned later in this document).

Each checkpoint is made up of 3 connected Bitcoin transactions:&#x20;

* the deposit collection transaction&#x20;
* the checkpoint transaction&#x20;
* the disbursal transaction.

The deposits get together into disbursal transactions that pay assets to different Bitcoin addresses.

A checkpoint transaction spends from the latest deposit collection output, and the output of the previous checkpoint transaction. It will have the following structure:

**Inputs**:

* The reserve output of the previous checkpoint transaction
* The deposit collection transaction output (If there have been deposits)&#x20;

**Outputs**:&#x20;

* The reserve output, equal to the amount of Bitcoin which is to be held in reserve. Paid to the updated reserve script based on the most recent signatory set.&#x20;
* The disbursal output, equal to the total amount of Bitcoin to be disbursed. Paid to the updated reserve script based on the most recent signatory set (If there are pending withdrawals)

**Checkpoint Interval**

A checkpoint is created every time the signatory set changes by a certain threshold, or on a certain time interval. One checkpoint per Bitcoin block is a perfect option.

**Prevention of Long-Range Attacks. PoS**

A known issue of Proof-of-Stake consensus is the so-called long-range attack, when a validator is forking the network which is out of date, and after the attack reproduces the alternative network without "unnecessary blocks" and the risk of being punished for the burning of their staked tokens. Thus, an attacker will deceive the clients, synced to the fake network.

<details>

<summary>What is Long-Range Attack </summary>

Michael (М) decides to perform a long range attack. In order to do this, he eliminates Vasiliy’s (B) and Anfisa’s (A) blocks. Eliminated blocks are displayed in staples. At the top you can see attacker’s fork, which is parallel to the main-chain of blocks (at the bottom).

__![](<../.gitbook/assets/image (1).png>)__\
__

To compete with the main-chain M has to produce blocks ahead of time (Triple dots denote forfeited blocks). Thus, M creates an alternative branch of the blockchain, and when the blocks are eliminated, goes back to the genesis block, forks the blockchain and produces blocks similar to the main-chain. Then the attack is completed.

![](<../.gitbook/assets/image-2 (1) (1).png>)\


</details>

Bitcoin checkpoints allow to prevent long-range attacks:&#x20;

* A client will first SPV-verify the headers of the Bitcoin blockchain, ensuring they are on the highest-work chain
* Then possess each checkpoint transaction and its Merkle branch proving its membership in the containing Bitcoin block&#x20;
* Verify that a checkpoint transaction is the successor of another

### Relayers

Every time a new Bitcoin block is mined, or a deposit transaction is broadcast to the Bitcoin network, the data will need to be carried to the Nomic sidechain. Conversely, when a transaction is signed by the signatory set in the checkpointing process, it will need to be carried to the Bitcoin network. This job is done by relayer nodes, which can be any node with knowledge of both networks running software to broadcast the relayed data.

Relayer nodes carry out the retranslation.

**Bitcoin to Nomic:**

* Deposit transaction is confirmed - transaction and Merkle proof are relayed to sidechain
* Bitcoin block mined - header is relayed to sidechain

**Nomic to Bitcoin**:&#x20;

* Checkpoint transaction

### Security

Since sidechain networks may hold large reserves of Bitcoin. In comparison with many blockchain projects, a security incident resulting in the loss of funds.

In addition, if more than ⅔ of signatories want to steal their reserve, they can do that for this reason:

* Emergency disbursal process is set to avoid the failure&#x20;
* Signatories bond their NOM, and it guarantees that they are economically disincentivized from stealing from the reserves

Along with the well known [slashing](https://www.cosmobook.io/cosmobook/v/russian/readme/cosmoshub#sleshing) rules in PoS networks, signatories are also subject to it when it is discovered that some of them sign the reserve expenditures transaction, while the other validators did not.

### Token Generation

&#x20;There are many ways to identify how a staking token gets in the circulation.\
To maintain fair and decentralized distribution, tokens, for instance, can be minted on the basis of provided proof of BTC burn, or they can be minted by miners as block reward.

### BTC Deposit

The signatories should be overcollateralized in relation to the BTC reserves they manage.

The minimum collateralization ratio is 1.5, meaning that a collusion of 2/3 subset of signatories to steal the reserves will pass with the loss of all of their collateral.

<figure><img src="https://lh3.googleusercontent.com/43JazVN569nWaZGZfinOV2dbK9KnohCkZ7nIdnUtobdpjy1VLieae22Qc6vbSrtTwNKgZyTCcSkBPkO4Lhmm6XkE7JHndH7Tm9tQqhlFvx1V2osIJ7wMWhGx-K6Yx6iNPqJdF5XW7eG7EwW1R8AZvXIFKyAsaZLPq5HmJG_KtFOwxTQALeXOL3AlQQ" alt=""><figcaption></figcaption></figure>

However, this strategy is not effective in terms of the capital. To hold $1B in its reserves, signatories would need to invest more than $1.5B. That's why there is an additional staking rewats, called reserve rate.

The commission is charged from all accounts that hold nBTC. Thus, collateral grows in proportion to the BTC deposits.

There are different possible schemes of collateralization ratio maintaining:

* &#x20;Regulation of the reserve ratio, depending on the collateralization ratio. (if it decrease the incomes increase)&#x20;
* Capped Collateralization: If the collateralization ratio falls below its target, BTC-claims would be removed from the network through a forced disbursal, with priority for keeping the claims with higher maximum reserve rates. The conservative approach is that collateralization should be higher than 1.5

### Emergency Disbursal&#x20;

In the case of an extended liveness failure, signatories also include the "emergency disbursal" transaction into the checkpoint process, and pays out each BTC claim.

This transaction is timelocked for 2 weeks If the checkpoint transaction will not be processed within this period.

Validators do their best to prevent extended periods of liveness failure and emergency disbursal process, because if this happens, tokens, deployed on the sidechain, will become valueless and will be equivalent to the whole network slashing.

It is possible to create a secondary market, where traders will be able to speculate on the possibility of an emergency disbursal process, estimating the risks of a catastrophic failure and serves as an indicator for the rest of the network.

### Network launch&#x20;

The network will be gradually deployed in the coming months.

**Phase 1:** Stakenet (February 2022, completed)

The Stakenet bootstraps the network by releasing the NOM staking token via an airdrop to ATOM holders and stakers, allowing them to stake NOM and begin accumulating rewards. The bridge functionality and NOM token transfers are disabled during this phase to allow launching in a controlled way where the impact of potential issues is minimized.&#x20;

**Phase 2**: IBC upgrade&#x20;

The first upgrade of the network will connect Nomic to other Cosmos chains (via IBC), and to the Bitcoin blockchain (via our bridge protocol). This will be a key milestone for the Cosmos ecosystem since Nomic will be the first IBC network not based on the Cosmos SDK, and the Bitcoin blockhain will officially become part of The Interchain. NOM token transfers will also be enabled at this point (both locally and over IBC) - however, nBTC will still not be available for deposit or withdrawal.

**Phase 3**: Full Bitcoin Bridge&#x20;

In this upgrade, the network will fully enable the Bitcoin Bridge, allowing anyone to deposit BTC in exchange for nBTC, and withdraw nBTC in exchange for BTC. nBTC will also be available to move over IBC, so at this point we expect BTC to instantly be utilized in Osmosis pools and other protocols.

### Bitcoin upgrade

Activated on July 5, 18:00 UTC. From this moment Bitcoin rewards are available in the Nomic app.

Some interesting security features of Bitcoin-bridge (e.g, emergency disbursal) are not included in this release and will be implemented later, in the coming upgrades. These security features will bring key differences between Nomic and other bridges.



<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

### Airdrop

**Airdrop #1**

_Eligibility_: ATOM holders/stakers with a balance of at least 1.5 ATOM Snapshot: Cosmos block 9,150,000 (21 January, 2022 11:22:43 UTC)

_Distribution_: Total: 3,500,000 NOM&#x20;

Formula: _`(min(liquidBalance, 1000) + (4 * min(stakedBalance, 1000))) / 20.299325 (The limit of current balance and pledge balance is 1000 ATOM, and the pledge balance is 4 times)`_

**Airdrop #2** \
_Eligibility_:

* ATOM, OSMO, JUNO, EVMOS, KUJI stakers
* Only staking to validators out of top 20

_Snapshot:_ September, 27&#x20;

_Distribution:_ 3.5M $NOM Limitation: maximum 10,000 NOM per one wallet

The testnet unlocks 25% of the NOM Airdrop on the mainnet. Airdrop #2 is available for testnet participants who completed 4 missions.

Watch the video [guide](https://www.youtube.com/watch?v=ORz\_PLfhF5A). Check your eligibility [here](https://testnet.nomic.io/#/airdrop). More than 209K wallets are eligible.

**Airdrop #3**

The 3rd airdrop planned with no details available yet. The tokens are reserved, but are not in circulation.

### Tokenomics <a href="#tokenomics" id="tokenomics"></a>

The NOM token is used for securing the Nomic network.

The NOM distribution is modeled after the OSMO token. The network has started with a supply of 21,000,000 NOM. The maximum supply after 9 years of inflation is 210,000,000 NOM (as an homage to Bitcoin’s 21,000,000 BTC).

**Initial Allocation**

Total: 21,000,000 NOM&#x20;

Airdrop I - 3,500,000 NOM&#x20;

Airdrop II - 3,500,000 NOM&#x20;

Airdrop III - 3,500,000 NOM&#x20;

Strategic reserve - 10,500,000 NОМ

Based on the standards of $OSMO and other Cosmos projects, the strategic reserve is used to create strategic partnerships for Nomic. It is held in multi-signature by the directors of the Nomic DAO Foundation and is solely to achieve Nomic's long-term goals. It will not be used for marketing, and strategic partners will be subject to vesting periods. All funds raised from the strategic reserve will be used to fund Nomic's development efforts.

At the discretion of the multisig members, reserves can also be used to delegate to validators who provide services to Nomic, such as operating infrastructure like block explorers and relayers, or contributing open source tools/resources to the ecosystem. In order to keep the network decentralized, the strategic reserve will not be "excessive" to control the network's share.

_Total distribution after the launch:_ 189,000,000 NOM

NOM will be distributed over 9 years, reducing inflation by 1/3 each year.&#x20;

* Staking Rewards - 47,250,000 NOM

Rewards will be distributed to NOM validators and delegators in the same way as other Cosmos chains. Protocol Incentive - 85,050,000 NOM

* Protocol Incentive - 85,050,000 NOM&#x20;

This portion of the NOM supply will be used for future incentives, which will be determined by governance or will be proposed in future upgrades. For instance, potential incentives could be paid to nBTC holders or liquidity pools providers for NOM or Osmosis pools.

Since no protocol incentives will be activated at Stakenet launch, issued NOM will be accumulated into a pool for distribution later.

* Community Pool - 9,450,000 NOM&#x20;

A portion of NOM will be collected into a pool that can be used by network governance. The Stakenet phase will not include a mechanism to use these funds, they will accumulate to a later upgrade that adds a governance system

### Long-term vision



* **Developer rights vesting** - 47,250,000 NOM

The developer share will be distributed to the Nomic team over time. Note that because the network is decentralized, in the event that the Nomic team ceases to be the primary contributor to development, the developer's share may be redirected to vest in other teams or individuals.

* **Total pool** - 9,450,000 NOM

Part of the NOM will be collected into a pool that can be spent by network management. The Stakenet phase will not include a mechanism for spending these funds, so they will be accumulated until a later update that adds a management system.

### Long-term vision <a href="#long-term-vision" id="long-term-vision"></a>

Nomic has been developed by early Cosmos employees since 2018. At first glance, Nomic is similar to other Cosmos projects, however, it has fundamentally different DNA.

Other chains are based on the Cosmos SDK, a standard framework with many advantages, but also has weaknesses. As for Nomic, it uses Tendermint consensus, but built on a completely custom stackб written in the Rust language and focusing on performance and the ability to rapidly develop new features.

### Links

🔗 Website [:](https://nomic.io) https://nomic.io

🔗 Application: [https:](https://app.nomic.io)//app.nomic.io

🔗 Telegram: [https:](https://t.me/nomicbtc)//t.me/nomicbtc

🔗 Twitter: [https:](https://twitter.com/nomicbtc)//twitter.com/nomicbtc

🔗 Discord: [https://discord.gg/7FjMJ49Vbc](https://discord.gg/7FjMJ49Vbc)

🔗 Blog: https://blog[.nomic.io/](https://blog.nomic.io/)

🔗 GitHub: [https:](https://github.com/nomic-io)//github.com/nomic-io

🔗 Explorer: [http://nomic.zenscan.io/index.php](http://nomic.zenscan.io/index.php)

🌍 Community https://t.me/nomicita
