# Nym Network

![](https://img2.teletype.in/files/90/be/90be1283-ddff-49ca-bbe1-ed32730189cd.png)

## Nym Network

According to the Nym team's statement, "The Nym Network is a decentralized and tokenized infrastructure providing holistic privacy from the network layer to the application layer". Nowadays the existing end-to-end encryption models can protect/hide the content of communications data, but they cannot do that with the metadata about whom a user is communicating with and when. Nym, in its turn, protects both content and metadata, making it impossible for a third party to associate specific network activity with any device.

Nym consist of two core components:

1\. Decentralized Mixnet, that aims to protect users’ network traffic. The mixnet is an improved version of the models such as VPNs and Tor

2\. A tokenized credential system that provides application-level privacy and allows users to access the mixnet

The Nym Network's native token $NYM is a utility token, used to pay for different network operations, and also serves as a reward for mixnodes operators, validators and service providers.

### Nym Architecture

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Users (indicated in the figure as Alice, Bob, and Carol) get secure and confidential access to the services they need through the client software ("client apps" in the fig.). This software allows users to create credentials and then send the information packages to the Nym mixnet.

Validators distribute partial credentials (more details in the following section), produce blocks and maintain synchronization with other blockchains that require privacy.&#x20;

_Mixnet_ is a network of mix-nodes ("mix-nodes" in the fig.) that “mixes” the information packages to ensure the network-level privacy (meaning that a third party cannot identify who is connecting with whom).&#x20;

_Gateways_ serve as a buffer that stores clients' messages in case a client temporarily goes offline.&#x20;

_Service providers_ are applications that use the mixnet. Service providers can utilize their own blockchains.

_Nyx Blockchain_ (or Nym Blockchain) was originally used only for the CW smart contracts deploying, and tracking the topology of the Nym network, vesting contracts and the NYM token itself. However, at the moment Nyx Blockchain is an open-source smart contracts platform, so every user or developer can deploy there their own smart contracts.&#x20;

_Indentity providers_ (are not indicated on the figure) - providers that can verify, upon user request, attributes that are encoded in the Nym credentials.&#x20;

_Mix guards_ (are not indicated on the figure) - check whether clients have a valid Nym credential to use the mixnet and provide resistance against denial-of-service attacks and censorship

### Nym Mixnet

1. User requests a service provider to perform a certain task. The service can be paid (a user pays the service provider) or free, but in both cases a small commission is charged to reward validators and mix-node operators.
2. Users gather attributes that a service provider needs (e.g. proof of age or nationality). If a service provider requires more "secure" user verification, users can choose to obtain certified at- tributes from external identity providers (such as when registering on Coinlist). Next, a user passes on encrypted attributes to the validators. The validators generate and sign partial credentials and pass them back to the user. The client software collects these partial credentials and generates the credentials required by the service provider and the mixnet guards. Since the client software re-randomizes the credentials, they cannot be associated with the validators that signed the credentials. So, the user remains anonymous (at least this is what I understood).
3. Then, the user provides credentials to the mix guards. The mix guards send user traffic to the mixnet (in so doing check the network throughput and protect users against the attacks like denial-of-service attack). Thus, credentials reach the service providers through the mixnet. Meanwhile, it is impossible to connect data to the sender, since the mixnet sends data with a random delay, and also hides the traffic.
4. Next, according to the mix-mining algorithm, rewards are distributed to the Nym network users

### **Mix-mining Rewards**

Mix-mining – is an algorithm combining both proof-of-work and proof-of-stake designs. Mix-nodes are rewarded for performing the computing work, associated with privacy ensuring (sort of PoW). The mix-nodes operators and validators both stake their NYM tokens. In case of bad behavior, a percentage of staked tokens will be slashed (PoS). Additionally, they receive staking rewards. Any user can delegate tokens to a specific node and get rewards for this.&#x20;

Full whitepaper: https://nymtech.net/nym-whitepaper.pdf.&#x20;

Litepaper: https://nymtech.net/nym-litepaper.pdf.
