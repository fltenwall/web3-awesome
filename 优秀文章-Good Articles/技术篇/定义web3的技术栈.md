

-------------------------------------------------------------------

本文翻译自：[on the Edge & Node blog](https://edgeandnode.com/blog/defining-the-web3-stack)

更多的 web3 中文资料： [web3-awesome](https://github.com/fltenwall/web3-awesome) 


------------------------------------------------------------------

### 前言

我在做了10年的传统全栈开发人员后，于2021年4月过渡到web3。在深入研究这些新技术和新思想时，我首先想知道的是“web3技术的技术栈是什么?”

在构建一个传统的web或移动应用程序时，我经常依赖于一些组件来完成工作。

1. API /应用服务器(REST或GraphQL)

2. 身份验证层(管理或手动)

3. 数据库

4. 客户端框架、平台和库

5. 文件存储

使用这些核心组件，我可以构建出我想要的大多数应用程序类型，或者至少实现其中的大部分。这在web3中是什么样子的呢?

事实证明，这个问题的答案并不那么简单，因为:

1. web3的范式在许多方面是完全不同的

2. web3的工具、技术和生态系统都不如web2成熟


对我来说，理解如何建立、运行和构建web3应用程序也更加困难，因为web3中处理问题的方式和在web2世界中的方式相同。

在过去8个月的工作、研究、实验和总结之后，我想分享我所学到的东西。

### 什么是web3?

在定义 web3 的技术栈之前，让我们先来定义 web3 。它可以有无数的定义，这取决于你问的是谁，但我发现下面👇这个定义是正确的:

`Web3是支持完全去中心化应用程序的协议栈。`

有了这个去中心化的技术栈，我们可以开始构建具有自己的含义和特征的去中心化应用程序。

web3支持的一些特性有:

- 分散的网络基础设施

- 所有权(数据、内容和平台)

- 原生数字支付

- 自我主权身份

- 分布式、去信任化、健壮的基础设施

- 开放、公共、可组合的后端

尽管一些模块在去中心化技术栈上的应用程序将取代它们的前辈，但区块链支持的新原语也使一种新的应用程序范式成为可能。

原生数字支付和公共后端基础设施——如机器学习、移动设备、虚拟现实和其他技术原语、平台和模块—能够构建全新类型的应用程序，其中一些还没有被想象到。

这是否意味着一切都将被web3所取代?不一定。虽然我确实认为构建在去中心化的技术栈上对于某些类型的应用程序是一个更好的选择——就像几乎所有的技术决策一样，这取决于你正在构建什么。

现在让我们开始深入web3技术栈，分成以下几类:

1. 区块链
2. 区块链开发环境
3. 文件存储
4. 链外数据协议
5. API(索引和查询)
6. 身份
7. 客户端(框架和库)
8. Oracles
9. 其他协议


![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9752cb3ef65d4e67ab33351b09392d4b~tplv-k3u1fbpfcp-watermark.image?)

### 区块链

你可以选择在无数的区块链上进行构建。没有哪一个是“最好的”，相反，你应该考虑它们之间的各种权衡。

当我学习新东西时，有一件事对我来说很重要，那就是把`帕累托原理`应用到我所学的东西上。也就是说，怎样才能最有效地利用这些时间和精力。遵循这个想法，我可以在最短的时间内获得最大的动力和动力来学习新东西。

在区块链世界，学习 solid 和[EVM](https://ethereum.org/en/developers/docs/evm/)(以太坊虚拟机)可能是作为区块链开发人员开始的最佳选择。使用此技能栈，你不仅可以为以太坊构建，还可以为其他以太坊2层、侧链，甚至其他区块链，如Avalanche、Fantom和Celo进行构建。

也就是说，Rust开始在区块链世界变得越来越受欢迎，Solana、NEAR、Polkadot和其他一些公司都提供了一流的Rust支持。你可能真的不会在学习中遇到问题，但是对于初学者来说，如果今天有人问我该如何选择，我会说 solididity 仍然是更好的选择。

除了上述建议，以下是一个不完整的区块链样本，它结合了技术、效用、社区、势头和未来可行性:

1. [以太坊](https://ethereum.org/en/)——原始智能合约平台

2. ZK汇总：[ZKSync](https://zksync.io/), [Starknet](https://starkware.co/starknet/), [Hermez](https://hermez.io/) -高吞吐量以太坊 Layer2（以太坊解决方案的统称），但不兼容EVM

3. Optimistic汇总：[Arbitrum](https://offchainlabs.com/) & [Optimism](https://www.optimism.io/) -以太坊 Layer2，与EVM兼容(在[这里](https://vitalik.ca/general/2021/01/05/rollup.html)了解更多关于Optimistic和ZK之间的差异)

4. [Polygon](https://polygon.technology/)-以太坊侧链

5. [Solana](https://solana.com/) -高吞吐量，便宜的手续费，快速的阻塞时间，但比EVM (Rust)更难学习

6. [NEAR](https://near.org/) - Layer 1 区块链，可以在Rust或Assemblyscript中编写智能合约

7. [Cosmos](https://v1.cosmos.network/)  - 一个互操作区块链的生态系统

8. [Polkadot](https://polkadot.network/) -基于区块链的计算平台，使构建在其上的区块链能够在它们之间执行交易，创建一个互联的区块链网络

9. [Fantom](https://fantom.foundation/?__cf_chl_tk=hkVqppeUFDfRzFwd6Ln5eCa_672VgYpga52iuUhMR4Q-1639611813-0-gaNycGzNCZE) - EVM兼容 Layer2

10. [Avalanche](https://www.avax.network/)- EVM兼容 Layer2

11. [Celo](https://celo.org/) - EVM兼容 Layer2，旨在使任何拥有智能手机的人都可以轻松地发送、接收和存储加密

12. [Tezos](https://tezos.com/) -非EVM兼容 Layer2，很多NFT项目都在使用它

[注：关于 layer1 和 layer2 看这里 ](#layer)

当与网络交互时，您需要使用RPC端点。

有几种方法可以做到这一点:

1. 访问公共RPC端点
2. 运行自己的节点
3. 将节点提供者作为服务访问
4. 将分散节点提供者作为服务访问

公共RPC端点通常由网络提供，但是对于大多数生产dapp，您希望利用自己的端点，因为它们不是稳定的，也不推荐用于生产。

有一些RPC服务提供商在那里，这里有一些:

-   [Infura](https://infura.io/)
-   [Figment Datahub](https://datahub-beta.figment.io/)
-   [Ankr](https://www.ankr.com/)
-   [Coinbase Cloud](https://www.coinbase.com/cloud)
-   [Cloudflare](https://developers.cloudflare.com/distributed-web/ethereum-gateway/interacting-with-the-eth-gateway)
-   [Alchemy](https://www.alchemy.com/)
-   [Genesis Go](https://genesysgo.com/) (Solana)

还有一个web3 /去中心化的解决方案，还有一个web3 /去中心化的解决方案 —— [Pocket](https://www.pokt.network/)，它似乎正在获得大家的注意。

这些选项中的任何一个都可能是与您的网络直接交互的好选择。似乎正在获得吸引力。

这些选项中的任何一个都可能是与您的网络直接交互的好选择。

### 区块链开发环境

对于EVM开发，有几个不错的开发环境:

- [Hardhat](https://hardhat.org/) (JavaScript)是一种较新的选择，但它越来越受欢迎。他们的文档很棒，工具和开发人员体验都很完善，我个人也一直在用它来构建dapps。

- [Truffle](https://trufflesuite.com/) (JavaScript)是一套用于在EVM上构建和开发应用程序的工具。它是成熟的，经过战斗测试的，并且有很好的文档。它已经存在一段时间了，许多开发人员都在使用它。

- [Foundry](https://github.com/gakonst/foundry) 这是来自Paradigm的一个新的solid开发环境，它显示出了很多的潜力。最突出的是用Solidity编写测试的能力、对fuzzing的支持和速度(它是用Rust编写的)。我在[这里](https://mirror.xyz/sha.eth/6Mn3HjrqKLhHzu2balLPv4SqE5a-oEESl4ycpRkWFsc)写了一个单独的介绍。

- [Brownie](https://eth-brownie.readthedocs.io/en/stable/)是一个基于python的开发和测试框架，用于solid / EVM开发的智能合约。

对于Solana的开发来说，[Anchor](https://project-serum.github.io/anchor/getting-started/introduction.html)正迅速成为新开发者的切入点。它提供了一个CLI，用于搭建、构建和测试Solana程序，以及用于构建前端的客户端库。它还包含了一种DSL，它抽象掉了开发人员在开始Solana和Rust开发时经常遇到的许多复杂问题。

### 文件存储

在web3中，我们在哪里存储图像、视频和其他文件?在链上存储这么大的东西通常是非常昂贵的，所以我们可能不想将它们存储在那里。

相反，我们可以使用以下几种文件存储协议之一:

- [IPFS](https://ipfs.io/)—对等文件系统协议
    
    优点:它是可靠的，有良好的记录，有一个大的生态系统
    
    缺点:如果数据没有固定，它可能会丢失
    
- [Arweave](https://arwiki.wiki/) -允许您永久存储数据，支付单一交易费用。我是Arweave的粉丝，并在[这里](https://edgeandnode.com/blog/developers-guide-to-arweave)写了一篇关于它的博文。

- [Filecoin](https://arwiki.wiki/)——来自协议实验室(Protocol Labs)，与构建IPFS的团队相同，它是一种旨在提供持久数据存储系统的协议。开发人员在Filecoin上进行[构建的方法](https://docs.filecoin.io/store/)有很多，包括web3。储藏很好。

- [Skynet](https://siasky.net/) -我还没有在生产中使用它，但已经尝试过了，它似乎工作得很好。[这里](https://siasky.net/developers)的API看起来很棒。我有一些问题，比如数据可以保存多久，以及天网与其他协议的互操作性。

### 链外数据协议

除了文件存储和链上存储，您可能还需要链下存储数据。您可能会像使用传统技术栈中的数据库一样使用这些类型的解决方案，但相反，它们是在分散的网络上的n个节点上复制的，因此更可靠(至少在理论上)。

一些选择是:

- [Ceramic Network](https://ceramic.network/)  —— 一个分散的，开源的平台，用于创建，托管和共享数据。Ceramic 也有一个很好的身份协议，我稍后会讲到。可能是我目前最喜欢的脱链存储解决方案。[这里](https://twitter.com/ceramicnetwork/status/1364631929262235648)有一个很好的演示。

- 一个建立在IPFS和Libp2p上的[ThreadDB](https://docs.textile.io/threads/)数据库。如果我理解正确的话，它可能正在经历一个大的API变化。我已经尝试过了，它显示出了一些希望，但文档和DX需要一些改进。

- [GunDB](https://twitter.com/ceramicnetwork/status/1364631929262235648) 这是一个去中心化的，点对点的数据库。Gun已经存在很长一段时间了，已经有一些[非常有趣的应用程序](https://www.starlinglab.org/challenges/)使用它来构建。

就成熟度而言，我认为，链下存储解决方案的生态系统还没有达到开发人员可能想要的更高级用例的水平。这里的一些挑战包括实时数据、冲突检测和冲突解决、写入授权、文档和一般开发人员经验。

将链外数据解决方案与区块链协议集成是我们需要跨越的最后一个大障碍，之后我们将拥有一个完全分散的协议栈，能够支持任何类型的应用程序。

### API(索引和查询)

与传统技术栈中的数据库相比，我们在区块链上进行交互和构建的方式有很多不同。使用区块链，数据不能以一种可以直接从其他应用程序或前端高效或容易地使用的格式存储。

区块链针对写操作进行了优化。您经常听到创新围绕每秒的交易、阻塞时间和交易成本发生。区块链数据在一段时间内以块的形式写入，这使得除了基本的读操作之外的任何操作都不可能实现。

在大多数应用程序中，需要关系数据、排序、过滤、全文搜索、分页和许多其他类型的查询功能。为了做到这一点，需要对数据进行索引和组织，以便有效地检索。

传统上，这是数据库在集中式技术栈中所做的工作，但索引层在web3栈中缺失了。

[The Graph](https://thegraph.com/en/)是索引和查询区块链数据的协议，它使这个过程更加容易，并为此提供了一个分散的解决方案。任何人都可以构建和发布开放的GraphQL api，称为子图，使区块链数据易于查询。

要了解更多关于Graph的信息，请查看这里的[文档](https://thegraph.com/docs/)或[我的教程](https://dev.to/dabit3/building-graphql-apis-on-ethereum-4poa)。

### 身份

身份在web3中是一个完全不同的范例。

在web2中，身份验证几乎总是基于用户的个人信息。这些信息通常是通过表单或者OAuth提供者来收集的，OAuth提供者要求用户提交信息以换取对应用程序的访问权。

在web3中，身份完全围绕着钱包和[公钥加密](https://blog.mycrypto.com/the-basics-of-public-key-cryptography)的概念。

虽然“钱包”这个名称达到了它的目的，但我发现web3的新手发现这个术语令人困惑，因为它与身份验证和身份相关。我希望未来我们能找到其他方式来传达钱包是什么，因为它结合了金融、身份和声誉等方面。

作为一名开发人员，您需要了解如何以各种方式访问用户的钱包和地址并与之交互。

在非常基本的级别(也是非常常见的需求)，您可能希望请求对用户钱包的访问权。要做到这一点，你通常可以在窗口上下文(web浏览器)中访问用户的钱包，或者使用[WalletConnect](https://walletconnect.com/)或[Solana钱包适配器](https://github.com/solana-labs/wallet-adapter)之类的东西。

例如，如果他们有一个可用的以太坊钱包，您将能够访问window.ethereum。Solana (window.solana)、Arweave (window. arwevewallet)和其他一些网站也是如此。WalletConnect适用于移动web和React Native，因为它允许用户直接从设备上授权使用他们的移动钱包。

如果您希望自己处理身份验证，您可以允许用户对事务进行签名，然后在某个地方对其进行解码，以验证用户，但这通常需要服务器。这有一个[使用EVM钱包](https://mirror.xyz/sha.eth/i6ry1Mxez53z91ef375sMe2rO1NvK2ipACyzKA4SR9g)的例子，以及[使用Solana / Phantom](https://docs.phantom.app/integrating/sending-a-transaction#signing-and-sending-a-transaction)的例子。

以分散的方式管理用户档案怎么样?[Ceramic](https://developers.ceramic.network/learn/welcome/)网络提供了最健壮的协议和工具套件来管理分散的身份。他们最近发布了一篇[博客文章](https://blog.ceramic.network/the-next-architecture-for-building-web3-data-applications/)，概述了他们最近的一些更新，并就所有这些工具如何协同工作给出了一些指导方针。我会从那里开始，然后探索他们的[文档](https://developers.ceramic.network/learn/welcome/)，以了解如何开始构建，并考虑查看我在[这里](https://github.com/dabit3/decentralized-identity-example)使用Ceramic 构建的[self.id](https://developers.ceramic.network/tools/self-id/overview/)示例项目。

如果你想获取用户的[ENS](https://docs.ens.domains/)文本记录，[`ensjs`](https://github.com/ensdomains/ensjs)库提供了一个很好的API来获取用户数据:

```javascript
const ens = new ENS({ provider, ensAddress: getEnsAddress('1') })
const content = await ens.name('sha.eth').getText('avatar')
```

[SpruceID](https://spruceid.com/)看起来也很有前途，但我还没有尝试它。

Ceramic和[Spruce](https://spruceid.dev/docs/didkit/)都实现了[W3C DID](https://www.w3.org/TR/did-core/)规范，我认为W3C DID规范本身也是web3的一个模块。话虽如此，任何集中的DIDs实现都违背了规范试图实现的思想。

### 客户端

就JavaScript框架而言，您实际上可以使用任何您喜欢的东西进行构建，因为客户端区块链sdk基本上是与框架无关的。也就是说，绝大多数的项目和例子都是在React中构建的。还有一些像[Solana Wallet Adapter](https://github.com/solana-labs/wallet-adapter)这样的库为React提供了额外的实用工具，所以我想说学习或熟悉React可能是一个明智的举动。

以太坊的客户端sdk有[web3.js](https://web3js.readthedocs.io/en/v1.5.2/)和[ethers.js](https://docs.ethers.io/v5/)。虽然web3.js出现的时间更长，但对我来说，ether更容易使用，文档也更好。

在Solana中，你可能会使用[@solana/web3.js](https://docs.solana.com/developing/clients/javascript-api)和/或[Anchor](https://project-serum.github.io/anchor/getting-started/introduction.html)。我发现锚客户端库是我构建Solana程序的首选，因为我一直在使用锚框架，而且我发现它比`@solana/web3.js`更容易理解。


### Oracles

oracle允许开发者从智能合约中读取真实世界的数据和外部系统。

例如，大多数金融应用程序需要了解真实世界的数据和发生在链外的事件，因此oracle在DeFi中尤其重要。

[Chainlink](https://chain.link/)是一款Oracle软件，能够访问真实世界的数据和链下计算，同时保持区块链技术固有的安全性和可靠性保证。

[Flux](https://www.fluxprotocol.org/)是一个跨链的oracle，提供智能合约访问经济安全的数据源。

### 其他协议

[Radicle](https://radicle.xyz/)是一个基于Git的代码协作协议。它可以被认为是GitHub的去中心化版本。

[Livepeer](https://livepeer.org/)是一个去中心化的视频流媒体网络。它已经成熟并被广泛使用，网络上有超过70,000个gpu。

### 结语

这篇文章将会是一个持续更新的文档，在我学习、试验和收集使用web3开发人员的反馈时，我会一直更新。

如果你有任何反馈或想法，我在这里错过了什么，请与我分享你的想法。
所有围绕web3发生的活动都是令人兴奋的，因为很多开发人员都参与进来了。虽然基础设施仍在发展，但构建真正的去中心化协议和应用程序的是一个非常重要的愿景：它允许人们在不将权力和控制权交给大公司的情况下进行协调，而我们即将实现这一愿景。

### 推荐

[原文地址](https://edgeandnode.com/blog/defining-the-web3-stack)

[web3-awesome](https://github.com/fltenwall/web3-awesome) web3百科全书👏🏻 旨在打造 web3 全球第一中文资源


### 名词解释

####  <p id="layer"> Lay1 和 Lay2  </p>

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d5cda350254d492f91d2bb793d2b9c65~tplv-k3u1fbpfcp-watermark.image?)

一、分层

通过借鉴计算机网络通信体系架构的OSI模型，可将区块链逻辑架构划分为三层。

1. layer0
其中第0层（Layer 0）对应OSI模型的1-4层（底层协议），包括传输层。

2. layer1
第1层和第2层对应OSI模型的5-7层（上层协议），第1层（Layer 1）包括数据层、网络层、共识层和激励层.

3. layer2
第2层（Layer 2）包括合约层和应用层。

二、作用
Layer 1 解决信任，Layer 1 的代币的存在是为了让这条底层公链能够抵抗 51% 攻击。

Layer 2 搞定性能，对于 Layer 2 协议来说，唯一能够捕获价值的方式是存储某种外部的、有价值的状态。

三、应用
现有的扩容方案分别针对不同层级进行改进，分为第0层扩容、链上扩容和链下扩容。

第1层扩容，即链上（On-Chain）扩容，通过优化、改进公链基本协议提升区块链性能。

第2层扩容，即链下（Off-Chain）扩容，不改变公链基本协议，通过链下在应用层进行改进提升性能。

第0层扩容通过优化区块链底层数据传输协议提升区块链性能，不改变区块链的上层架构，是一种保留原有链生态规则的性能提升方案。


![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/70b0bd9025994300a70653b5d9c81743~tplv-k3u1fbpfcp-watermark.image?)

像我们所熟悉的比特币网络、以太坊主网等主流公链都属于Layer 1的范畴。只不过，由于在当前众多的公链项目中，以太坊是运行智能合约、DAPP最多的公链，也是锁仓资产价值和日均交易量最大的公链，所以在有关以太坊网络Layer1和Layer2不同扩容方案的讨论也是最多的，所以在本文中，如没有特殊说明，所提到的Layer1和Layer2一般以以太坊为主。通俗来说，在以太坊网络中，Layer 1的主要作用就是确保网络安全、去中心化及最终状态确认，做到状态共识，并作为一条公链网络中可信的“加密法院”，通过智能合约设计的规则进行仲裁，以经济激励的形式将信任传递到 Layer2 上；而Layer2 则以追求更高效的性能为终极目标，从上面区块链技术逻辑架构示意图中，我们可以看到，作为第二层网络，可以替 Layer1 承担大部分计算工作，近年来，不少项目都是基于Layer2搭建的，从而将交易行为从主链上分离出来，降低一层网络的负担，提高业务处理效率，从而实现扩容。在这个过程中，Layer2 虽然只做到了局部共识，但是基本可以满足各类场景的需求。

目前行业内比较贴切的是将Layer1和Layer2的关系和中央银行与商业银行的关系来类比：把Layer1承担着中央银行的角色，而layer2则是各大商业银行。在现行主流的金融系统中，所有的资产都必须在中央银行结算，而具体的流通过程可以同时发生在中央银行和商业银行。因为如果所有人都去央行结算的话，势必会发生业务拥堵的情况，更好的解决办法当然是由商业银行来先处理大量交易业务，然后由各个商业银行和中央银行结算一次整体业务，这样才能使得整个金融系统更加高效有序的运转起来。所以从中我们能够得到的启示就是，对于在以太坊网络中存在的交易拥堵、手续费居高不下的问题，一个可行的解决方案就出炉了——将以太坊的资产存入Layer2，之后的资产流动交易环节都在Layer2上进行，只把最终结算过程放到Layer1上就可以了。

【说明】：

来源1 [区块链 layer0、layer1和layer2是什么 有什么作用](https://zhuanlan.zhihu.com/p/410557922)

来源2 [区块链 layer0、layer1和layer2是什么 有什么作用](https://blog.csdn.net/u013288190/article/details/110862569)


