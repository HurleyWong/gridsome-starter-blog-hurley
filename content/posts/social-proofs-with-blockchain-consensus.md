---
title: Social Proofs with Blockchain Consensus
date: 2020-07-10T21:00:00+08:00
published: true
slug: social-proofs-blockchain-consensus
tags:
- Android
- smart contract
- solidity
- Blockchain
cover_image: "./images/social-proofs-blockchain-consensus.png"
canonical_url: false
description: Proof of Witness Presence - Social Proofs, to develop blockchain smart contracts that prove social claims (situation awareness) on the smart phone.
---

:::note 📌 Abstract

在 Dr. Evangelos Pournaras 的毕设项目中，我主要负责第二部分的内容：Proof of Witness Presence - Social Proofs, and main job is to develop blockchain smart contracts that prove social claims (situation awareness) on the smart phone. The smart contracts can use a combination of CAPTCHA, QR codes, puzzles tests, social proofs and other. A demonstrator needs to be delivered and later an integration to Smart Agora.

:::

## Background research

### 初探索

在一开始，我对这个项目是十分不了解的。即使我阅读了导师的 [Proof of Witness Presence--Blockchain Consensus for Augmented Democracy in Smart Cities](https://www.sciencedirect.com/science/article/pii/S0743731520303282) 这篇论文以及关于这篇论文的一个 use case 的 work paper: [On cycling risk and discomfort: urban safety mapping and bike route recommendations](https://link.springer.com/content/pdf/10.1007/s00607-019-00771-y.pdf)，我只是大致理清了整个场景中公民（用户）的操作流程：当用户到达地图中的某个兴趣点（地图中具有一定范围的圆圈）附近时，可以使用他们的智能手机回答问题或者评估风险等，公民的这些意见都会为系统设计者或者城市规划者带来巨大的帮助。同时，公民通过制定决策也可以获得虚拟加密货币的奖励。第三部分是关于游戏化的，即问题和兴趣点的设置具有引导式，让公民从兴趣点A到兴趣点B这样的方式，连续回答问题等。当然，第三部分就不是我负责的项目部分了，所以这里不作考虑。

我负责的部分就是除了位置证明之外，需要使用 social proof 来证明公民到达了兴趣点附近。因为只有公民到达了兴趣点附近，才能开始制定决策的过程。可是 social proof 究竟是什么呢？

在我的第一印象中，social 这个词被我理解为社交，所以是社交证明？难道需要其他人来证明一个公民到达了兴趣点附近？这样也太不符合系统的设计了，因为这样如何确定真实性呢？

social 还可以被理解为社会，所以是社会证明？社会是一个十分“大”的词，所有的人和行为都处在社会中。我仍然没有找到合理的答案。

通过谷歌搜索 social proof，我发现大部分有关的结果都是 social proof 如何影响人的行为。例如，用户在购物时会根据评论、评分的高低来判断是否要购买该商品等等。但这些显然与本项目的 witness presence 毫无关联。

终于，导师论文中的这段文字给了我启发：

> Other means to verify witness presence include the following: Contextual QR codes, challenge questions, puzzles and CAPTCHA-like tests, whose solutions re-quire information mined at the point of interests. In addition, collaborative social challenges between citizens are means to introduce social proofs based on social psychol-ogy as well as community trust for protection against social engineering attacks. Moreover, communities can also institutionalize their own digital witnesses based on privacy-preserving forensic techniques introduced in the context of blockchain.

**Entity**!

是的，尽管用证人来证明一个公民到达兴趣点的方式很难实现也很难确定其真实性，但如果公民能用一些实体来证明，就再好不过了。

比如，公民购买了一张火车票前往某地，那么火车票的出发站和到达站、出发时间和到达时间就至少可以证明该公民在这个时间段内到达过这两个火车站，也就成功证明了用户所在的位置。众所周知，无论是线上还是线下购买火车票都是联网的，所以当公民购买了一张火车票时，这条记录以及与这个操作有关的所有数据信息都会被上传到区块链的区块中保存，公民获得的实体票据或者电子票据上也会出现条形码或者二维码以供公民识别真伪。那么，公民就可以通过真实的条形码来实现社会证明啦。Cheers~

### 再研究

通过与导师沟通后确认可以使用二维码的方式来帮助确定公民在某位置出现过，导师又给了我的建议：开动你的脑筋，想出至少六个场景，不需要太过具体，但是基本能够包括地图上的所有不同类型的地点。

具体的意思就是，如果仅仅是在火车站需要用火车票，在飞机场需要用飞机票的方式的话，那么地图上的地点可太多了，这样设计系统的话，可能永远也设计不完。因为在不同的地点就需要使用不同的实体，这相当于我要开发 N 个场景，这显然是不现实的。因此，需要总结为 6 个场景，基本代表地图所有不同种类的地点。

好吧。那就归纳出 6 个场景吧。如之前提到的火车站、飞机场，这些显然都是一些公共交通地点，那么就可以归为一类，统一使用 Transport Ticket 来完成验证。

接下来，门票也是很容易想到的。当公民去一些娱乐场所，例如电影院、博物馆等等，肯定需要购买门票吧。所以，很多公共场所都可以用 Ticket 来完成验证了。嗯，这里其实有一个问题，当时心中也已经产生了疑惑。因为在英国，福利待遇非常好，很多公共场所对用户都是免费开放的。例如，大量的公园，art gallery，甚至一些博物馆等等都是免费开放的。免费就意味着并不需要门票，那怎么证明公民到达了该兴趣点附近呢？这个疑问在之后与导师的探讨中得到了解答。

接着想场景吧。其实设想场景这个阶段花费了我挺长时间的。一来是当时课程并未结束，重心都放在了课堂上；二来是当时真的对于这个项目的整个流程还处于不太了解的状态，并不理解这样做要干什么。

接下来的场景有：

在购物场所可以使用收据来证明。众所周知，在英国，稍微正规店的商店都是提供收据的。在医院或者药房等场所可以使用医疗证明或者处方来证明。在一些办公场所、学习场所等需要证件来能进入的场所，就可以用证件来证明。最后在一些公司、保险机构等可以需要营业资质的场所就用营业资质来证明了。

总结起来就是如下 6 个场景：

* **Transport Ticket** (train station, airport, etc.)
* **Receipt** (shopping mall, store, restaurant, etc.)
* **Id Card** (school, accommodation, workplace, government, etc.)
* **Ticket** (park, museum, etc.)
* **Prescription** (hospital, pharmacy, etc.)
* **Certificate** (company, insurance agency, etc.)

场景是归纳完毕了。但实际上，总结出来后自己也产生了一些疑惑。

第一，按照论文的设想，需要证明公民实时出现在某个兴趣点附近，或者在某个符合条件的时间段内出现在某个兴趣点附近。然而，通过以上 Entity，某些实体例如火车票、收据等，是的确包含时间属性的，即可以通过时间来判断用户在某个时间段的位置。但是对于某些实体例如 ID Card，例如 Certificate，这些也可能包含时间属性，但是指的是有效时间和过期时间。例如 Student ID Card 上的时间是有效期到过期日，总不能这么长的可能一年的时间段都能够证明公民一年内都到达过该地点吧？这显然是不合乎逻辑的。

第二，接着第一点进行分析，那么似乎绝大多数情况下，6 个场景仅需要 4 个场景就能证明所有的地点了，即 Transport Ticket、Ticket、Receipt、Prescription。剩下的两个因为时间属性不明确，并且 **Certificate** 这个营业资质并不容易拿出来进行证明，所以其实个人认为并不是两个很好的场景。但是，有些时候又的确很难证明，因为显然生活中有那么多的地点，并不是所有地点都能用这几个场景就覆盖，也并不是所有地点都能够有实体物证来证明。很简单的一个例子，大学的图书馆，凭借学生卡刷卡进入，那么学生（公民）仅凭学生卡的话，似乎就能完成证明。但是无法通过学生卡证明在某个特定的时间段出现过图书馆（除非学校图书馆后台调取刷卡记录，但这显然我们是做不到的）。除此之外，假设要证明学生在某个时间段出现学校的某个大楼里，例如 EC Stoner，这是一个并不需要刷卡进入的大楼，那么又如何证明呢？

所以，严谨地说，这个系统或者场景设计得并不完美，但是可能也很难面面俱到。

### 辅助法

通过与导师沟通，导师给出了一个“辅助法”的建议：

> Maybe you can extend later the scenario to verify any point of interest by using proximity information for the proofs. For instance, let's say you are at Hyde Park here in Leeds. How can you use social proofs? e.g. use a ticket to a station close to Hyde Park. Or use a receipt from a close by shop. Or... You can write a smart contract that gives more weight to the proof from the closest proximity, e.g. shop.

所以，这也是没有办法的办法了。当无法直接证明公民到达过某个兴趣点附近时，那么只能找该兴趣点附近的地点，通过间接证明的方式来完成。具体如下：

<center>
    <img width="60%" src="https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fa60817e2-dc97-4d41-ab46-d5d06370a110%2FUntitled.png?table=block&id=282a7611-6019-41ba-b7ce-45ee064a587e&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=3350&userId=&cache=v2">
</center>

As figure shown above, setting a park as a point of interest can be given by an oracle. In addition, there are some locations such as a bus stop, a shop, a cinema, a hospital and a train station (from near to far) within the scope of this oracle.

If a user cannot prove that he or she has been to this point of interest directly, then the user can choose to use secondary social proof. The user can find nearby locations that are within the range of this oracle, such as cinema and bus stop, and prove that the user has been to those locations in a period time.

It is not scientifically to assign weights in order, such the nearest weight should be 0.5. Because it is possible that the nearest one is 150 meters apart and do not reach the weight of 0.5 that should be persuasive. The weights should be assigned according to distance with a specific formula to calculate weights:

$$weight = (range - distance) / range$$

For example, a bus stop is 20 meters away from the park, and then weight is calculated to 0.9 (because the range is 200 meters in figure above), which is a very high weight, meaning that the user can prove that he or she has been to this point of interest (the park) by proving that the user has come to the bus stop convincingly.

In fact, direct social proof can also be regarded as secondary social proof. Because if the user can prove that he or she has been to this point of interest directly, then the distance should be 0 and the weight should be 1. This means that if the weight is 1, then the secondary social proof can be regarded as a direct social proof, which can directly prove that the user has been to the point of interest.

Similarly, because the weights are cumulative, if the total weight of each point of social proof after accumulation is greater than or equal to 1, it means that social proof is successful. On the contrary, it proves a failure.

也就是说，当直接社会证明不可用时，那么采用附近点的间接辅助证明就要被派上用场啦！

### 小总结

总的来说，大致流程以及证明的方法我们是确定下来了。但实际上，内心还是觉得与导师那篇论文相去甚远。因为论文中除了使用二维码条形码之外，还需要使用 CAPTCHA，puzzles 等方式进行证明。除此之外，大方向上还推荐用传感器融合 / 随时变化的行为 / 点对点目击的方式证明。但是我这里第一是很难实现传感器的，第二是像 CAPTCHA，puzzles 等方式，我认为是区别机器与真人的，并不能为证明提供任何帮助，所以在系统中并没有添加这种验证的程序。

最后还有一个失误的地方，就是在设想场景的时候。因为这些都属于背景研究吧，还没有进行 Coding 部分。后来在开发过程中，使用 Google Map SDK for Android 的时候才发现，谷歌地图都已经对这些地点进行了详细的分类，如果当时在设想场景时用到，就会更方便地总结 6 个场景了。

## Coding

代码部分主要分为 Solidity 和 Java 部分，Solidity 负责智能合约的编写，Java 则是 Android 部分的实现。

### Solidity

这部分主要是编写智能合约并部署到以太坊网络中。其实逻辑相对简单，主要就是预先存入了大量的测试数据，然后用户就可以根据数据生成的二维码检验这些数据是否在区块链的块中真实有效。

因为之前的分析我设想出了 6 个不同的场景，再加上兴趣点这个对象，所以一共有 7 个。在 Solidity 中则是 7 个结构体。下面以 Transport Ticket 的结构体为例：

```Solidity
struct TransportTicket {
    uint256 id;
    string ownerName;
    string from;
    string to;
    uint256 price;
    string timeDeparture;
    string timeArrival;
}
```

然后就是常规的增删查操作，不过 Solidity 不同在于需要`mapping`和`event`。

```Solidity
mapping (uint256 => TransportTicket) transportTickets;
mapping (bytes32 => uint256) hashToTransportTicketId;
uint256 transportTicketIndex = 0;
```

### Ethereum

在开发完智能合约后，需要将智能合约部署到以太坊网络中，这样移动终端才能随时随地地通过访问以太坊网络来调用智能合约，从而对数据信息进行比对。这里需要使用到的工具主要用 Infura、MetaMask 等。

首先在 Infura 中创建项目，选择使用 Ropsten 网络。完成后复制下 EndPoints 的地址，并将其配置在`truffle-config.js`文件中。

![Infura](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F41f6198f-e982-4ea8-b36e-746886cdf0f5%2FUntitled.png?table=block&id=8fac8569-4d4f-47b9-941e-d70ae7556ac5&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=3280&userId=&cache=v2)

同时在 Chrome 浏览器中安装 MetaMask 插件，注册账号并获得 3 个测试以太币。在设置隐私界面中找到 12 个助记词并将其配置在`truffle-config.js`文件中。

![MetaMask](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fdcfadf3b-5236-4fc5-97ab-99d0b0090e52%2FUntitled.png?table=block&id=c572045e-04bf-406b-bf86-d96d51fbbca7&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=710&userId=&cache=v2)

最后，在控制台中，使用`truffle compile`命令编译智能合约，并使用以下命令将智能合约部署迁移到以太坊区块链测试网络中：

```shell
truffle migrate --reset --network ropsten # --reset optional
```

![Truffle 三件套](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F5928d8f3-1276-4d51-b640-4c051bc24a24%2FUntitled.png?table=block&id=e5f7c1be-4dba-46f6-950c-8ac7bfe58b1f&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=2430&userId=&cache=v2)


部署完毕之后，控制台中会出现智能合约的具体信息，包括被部署到的具体地址中，例如https://ropsten.etherscan.io/tx/address.

![Contract Address](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fc1a52b91-cd0a-48b5-9179-4b9989b85851%2FUntitled.png?table=block&id=e09979dd-93b5-4267-ba8b-544355fbb5a6&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=2160&userId=&cache=v2)

### web3j

需要将移动终端与智能合约连接起来的方式有很多，最传统的就是使用网络请求的方式。然后对于 Java 语言，有一个 web3j 的库能够很方便地帮助我们实现。

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fb0dd7b4e-822a-4801-aaec-cbed5559badc%2FUntitled.png?table=block&id=3d5c6753-fad1-4384-8a84-23932a3c9692&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=1910&userId=&cache=v2)

通过在本地安装好 web3j ，然后使用 web3j 的以下命令，可以将智能合约的代码逻辑自动以 Java 的方式实现。

```shell
cd /path/to/your/web3j/java/project

web3j truffle generate /path/to/<truffle-smart-contract-output>.json -o /path/to/src/main/java/ -p com.your.organization.name
```

然后就会发现在 Android 项目中出现了智能合约的代码，那么如果需要在 Android 中调用智能合约，只需要调用其中的方法即可。

### Android

Android 部分则是与用户交互的系统，主要需要实现两个部分，一个是 Google Map 地图中获得位置的标注来判断是否 Social Proof 成功，另一个是扫描二维码解析信息，将所得到的数据进行拼接再哈希操作后，访问以太坊网络判断信息是否真实有效。

#### Google Map

首先需要注册获得 Google Map SDK 的 API，然后在安卓应用中添加谷歌地图。在本项目中，自定义了两个概念：一个是兴趣点 Point of Interest，一个是社会证明点 Social Proof Point。

Point of Interest 是指公民或者项目管理者可以指定地图中的某个地点为兴趣点，公民只需要证明他们在某段特定的时间内到达过该地点即可，就可以在该地点回答问题或者制定决策等。

Social Proof Point 是指当公民无法直接证明他们在某个特定时间内到达过某个兴趣点时（可能是因为丢失了相关的证明文件或者该兴趣点是免费开放的，不提供相关凭证），他们就可以选择使用「**辅助法**」的方式，通过证明他们到达过周围一定范围内的地点，这些地点就被称为 Social Proof Point。

因此，需要在公民（用户）进入手机端的Google Map界面后，根据提示询问公民是将该地点添加为 Point of Interest 还是 Social Proof Point。选择完毕之后，就进入证明的过程，即下一部分（二维码）。

![Google Map User Interface](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F898b46dd-d9c5-4675-a5cf-0075ee5d4c6e%2FUntitled.png?table=block&id=dafb15db-5268-4495-9a47-29b9eb245930&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=6480&userId=&cache=v2)

#### QR Code

该项目设想的场景是处于一个智慧城市中。在该智慧城市中，所有的购买、交易等都是处于一个庞大的大数据网络中。因此，无论公民在线上还是线下进行了某笔交易时，所有的交易细节都会上传到网络中，同时会返回给公民一个包含所有交易细节的二维码作为凭证，那么公民就可以凭借二维码作为 Entity 去证明他们在某个特定的时间内到达过某个兴趣点。

因为这仍然是一个设想，所以目前只有测试数据而并没有真实的数据，因为目前完全智能的城市仍然是不存在的。所以需要提供储存一个测试数据的二维码作为测试使用。

具体解析二维码的方式可以使用 Google 提供的开源库 ZXing。通过扫描二维码，解析二维码的数据并与区块链中已保存的数据进行比对，判断是否真实并且有效。如果有效，则说明成功证明公民到达过 Point of Interest 或者 Social Proof Point。

![Scan QR Code User Interface](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Ff4a60b58-f4ce-487a-ba38-86bed4414cf0%2FUntitled.png?table=block&id=068953e9-95e7-43f6-99a4-178549626fb5&spaceId=77b9deb7-cc8a-4bc2-82c7-73fdf2893565&width=8820&userId=&cache=v2)

:::note 💡 Tips

> 这里注意并不仅仅是 QR Code 的二维码格式，Barcode 的条形码格式同样支持。

:::

## Dissertation

本文仅仅是该毕设项目的整体思路和实现逻辑的介绍，具体的细节已经在论文中全部列出。

The dissertation is available at: [HUANG2020-FPR.pdf](https://notes.withh.life/download/HUANG2020-FPR.pdf).

The source code of the project is available at: [ProofOfSituationAwareness](https://github.com/epournaras/ProofOfSituationAwareness) (currently maybe private). I will appreciate it if you can give some improvement opinions.

### Reference

该毕设项目的智能合约部分的实现，除了参考了导师的论文之外，很多还借鉴了国内研究生论文的思路，下面是我有参考到的国内研究生的毕业论文列表：

[1] 区块链智能合约在学位管理系统上的研究与实现_党京

[2] 基于区块链智能合约的高校学历认证系统的研究与实现_吴春龙

[3] 基于区块链技术的电子数据存证系统_冒小乐

[4] 基于安卓的智能合约平台的设计与实现_朱翀

[5] 基于区块链技术的可信数据通证化方法的研究与应用_周桐

[6] 区块链智能合约技术的研究_许雄

[7] 基于区块链智能合约的可信存证系统研究与实现_曹迪迪

[8] 基于区块链技术的去中心化管理系统的研究与应用_孙韵秋

[9] 基于区块链技术的学位信息验证系统设计与实现_高翔
