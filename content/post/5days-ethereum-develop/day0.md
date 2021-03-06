---
title: "〇，介绍 | 5天掌握以太坊 dApp 开发"
date: 2020-05-19T14:18:04+08:00
categories:
- 5天掌握以太坊 dApp 开发
tags:
tags: 
- Ethereum
- dApp 
- blockchain
keywords: 以太坊 Ethereum dApp blockchain 以太坊教程
description: 回顾互联网的历史，我们懵然记起来尝试、自由、去中心化、技术能力、创造才是一名黑客的初心，而不是每日朝九晚五的满足产品经历的需求。而区块链技术正是黑客精神的体现。

---
![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/tz8ig.jpg)
## 为什么要掌握区块链技术
**我们要明确，区块链是一项技术**，作为技术，它和厨师、挖掘机、花卉种植、数据分析、深度学习、5G通信是平等的。虽然链圈的世界包罗万象有浮躁、丑恶、贪图、背叛，但技术本身是无罪的。我们不能因为郁金香泡沫而否定种植技术，也不能因为对核武器的恐惧而否定相对论，同样我们也不能因为数字货币的泡沫而否定区块链技术本身。

好在国家也早已意识到这一问题，在2019年10月24日, 第18次中共中央领导集体学习区块链，提到我们要把区块链作为核心技术自主创新的重要突破口。但我认为，没有人可以在不敲一行代码的前提下掌握一门互联网技术。最后真正掌握区块链技术的人，一定还是如你我一般的程序员。而是否掌握区块链技术正是未来人才竞争的重要参考。

**区块链技术正是黑客的精神体现，** 1984年，《新闻周刊》的记者史蒂文·利维出版了历史上第一本介绍黑客的著作——《黑客：计算机革命的英雄》。在该书中，他进一步将黑客的价值观总结为六条“黑客伦理”。
1. 使用计算机以及所有有助于了解这个世界本质的事物都不应受到任何限制。任何事情都应该亲手`尝试`。
2. 所有信息应该都是`自由`的
3. 不信任权威，提倡`去中心化`
4. 判断一名黑客的水平应该看他的`技术能力`，而不是看他的学历、年龄或地位等其他标准
5. 你可以用计算机`创造`美和艺术
6. 计算机使生活更美好


回顾互联网的历史，我们懵然记起来`尝试`、`自由`、`去中心化`、`技术能力`、`创造`才是一名黑客的初心，而不是每日朝九晚五的满足产品经历的需求。
而区块链技术正是黑客精神的体现。

## 运行在区块链上的应用程序-dApp
dApp（Decentralized Application）就是运行在区块链网络上的应用程序。区块链网络中对于dApp的开发，就好像我们开发移动平台上的App。iOS端我们可以用`Swift`、`Objective C`，Android平台可以用`Kotlin`、`Java`。而[`Solidity`](http://solidity.readthedocs.io/en/v0.6.8/)最早是[以太坊（Ethereum）](https://github.com/ethereum/)社区使用的dApp开发语言，用于编写智能合约，写法有点像`C++`：
```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.16 <0.7.0;

contract SimpleStorage {
    uint storedData;

    function set(uint x) public {
        storedData = x;
    }

    function get() public view returns (uint) {
        return storedData;
    }
}
```
如今，Solidity 已经被各大公链采用作为其智能合约的开发语言，如EOS、TRON等。因此，掌握dApp开发势必要清楚 Solidity 的用法。

## 我的区块链技术背景

2018年，我创办了区块链游戏 [LORDLESS (无主之城)](https://lordless.io)，当时我的职位是 CEO，每天要处理公司大量的日常运行的琐事，还要兼顾智能合约的编写工作。截止到今天2020年5月19日，我独自完成的智能合约合计承载了`40,000+ transactions`，涉及到`近千个ETH`，合约包括`空投合约`、`锁仓合约`、`交易市场合约`、`Luckblock合约`、`ERC721酒馆合约`、`种植啤酒花合约`、`Bounty合约`等。这些数字虽然不大，却让我们这个平凡小团队经历了创业的一波三折，去中心化的日活用户数多次占领Ethereum dApp排行榜首位。我也在自己编写的合约黑客被攻击、被盗ETH、被诈骗的过程中不断成长。甚至有的成长需要付出超越金钱的代价，这些经历虽已经变成回忆，但是区块链早已把这些故事记录在了一个个transactions中。现在想起那段腥风血雨般的区块链的创业经历来，依旧恍如隔日。

下图是[可扩展的 Airdrop 智能合约](https://etherscan.io/address/0x35223bc965dbd91b41ddf1f540e8c7e475853551)：

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/dv38e.jpg)

后续的文章中，我会重点介绍智能合约编写时容易忽略的安全问题。

## 写作本系列的目的
### 1.自我完善个人技术
写作的过程，也是不断学习的过程。在写作的同时我便会实现技术的自我完善。

### 2.分享技术
斯塔夫里阿诺斯在《全球通史》中多次强调的：“文明是在交流和碰撞中产生的。” 分享的过程也是与大家交流的过程，也是我们共同进步的过程。
当然，分享也更符合黑客理论的特质，把我的知识装进你们的大脑，这本身就是符合去中心化的理论。

### 3.结交朋友
在 LORDLESS 担任 CEO 的时，我也把自己的定位成程序员，这样做的目的便是不断提醒自己勿忘技术本身，保持与时俱进。
能够踏踏实实做技术的人都是值得交朋友的人，经历链圈的江湖的虚与委蛇与市恩贾义，才真正理解多年前在教室的黑板上看到那句话：`code is law`。

承诺万千，不如运行一行智能合约。

学习过程中可以在下方的评论区留言，评论技术采用 [Gitalk](https://github.com/gitalk/gitalk) 基于 Github issues 的评论系统，方便技术讨论。那么欢迎留言！