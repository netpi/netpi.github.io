---
title: "第2天，搭建开发环境，用 Node.js 转账 ETH  | 5天掌握以太坊 dApp 开发"
date: 2020-06-01T15:00:00+08:00
categories:
- 5天掌握以太坊 dApp 开发
tags: 
- Ethereum
- dApp 
- blockchain
keywords: 以太坊教程 以太坊 Ethereum dApp Ganache mainnet Ropsten Rinkeby Kovan
description: 本章我们主要学习以太坊开发环境的搭建，并运行一个 Deme --- 通代码来转账 ETH。
---

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/74m7h.png)
## 0 前言

本章我们主要学习 **以太坊开发环境的搭建**，并运行一个 [Demo](https://github.com/netpi/ethereum-demo) ---  **通代码来转账 ETH**。

## 1 开发环境介绍

以太坊的开发环境分成三大类

* 本地测试环境： Local Test Network
* 线上测试环境包括：
  * Ropsten Test Network
  * Rinkeby Test Network
  * Kovan Test Network
  * Goerli Test Network
* 线上生产环境：Mainnet Network（ 以太坊主网 ）

一般情况下，我们的项目开发流程是

`本地测试环境` --> `线上测试环境` --> `生产环境`

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/b3xgz.png)

但是，本文得讲解过程推荐**先快速跑通 Ropsten 环境，然后跑通本地开发环境。** 

原因是按照我提供的 [ethereum-demo](https://github.com/netpi/ethereum-demo) 来跑通 Ropsten 环境会相对容易，整个过程接近我们平时的转账，因此更容易了解以太坊的运作流程。

## 2 Ropsten 环境快速开始

### 2.1 生成随机账户 

访问 [助记词生成页面](https://eurychen.me/tools/mnemonic.html)，生成助12个助记词，作为测试开发使用。

**保存好随机生成的助记词**
![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/ha8ox.png)

记下第一个地址 `Account[0]`，下面要给 `Account[0]` 领取测试 ETH
![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/uqj4g.png)

### 2.2 领取测试 ETH

在 Ropsten 网络中获得测试 ETH 是非常的方便，只要到 [Ropsten Ethereum Faucet](https://faucet.ropsten.be/) 上填入你的以太坊地址，测试环境就会为你提供 `1ETH`。

填入 `Account[0]` 地址，申请 `1ETH`

![领取1eth](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/0cvtt.png)

### 2.3 注册 Infura

我们平时用的以太坊钱包，[TrustWallet](https://trustwallet.com/)、[Metamask](http://metamask.io/)、[MyEtherWallet](https://www.myetherwallet.com/) 等，都要通过发送 JSON-RPC 才能够接入到以太坊的网络中。
因此我们需要一个可以提供 RPCURL 的平台 -- Infura。

* 访问 https://infura.io/， 注册一个帐号
* 记住 `wss://ropsten.infura.io/v3/xxxxx` 这串，后面要使用。（ ENDPOINTS 选择 ROPSTEN）
![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/iyq52.png)

### 2.4 运行代码

我准备了一个 [ethereum-demo](https://github.com/netpi/ethereum-demo) ，来帮助大家快速 Setup;

Repo 地址：[https://github.com/netpi/ethereum-demo](https://github.com/netpi/ethereum-demo);

```shell

#1
git clone https://github.com/netpi/ethereum-demo.git

#2
cd ethereum-demo

#3 
npm install

# nodejs v8.17.0 （web3.js@1.x 目前支持 NODE_MODULE_VERSION 57 ）
```

修改 **ropsten.config.js** 文件，把第一步中生成的**助记词**和 infura.io 中申请的 **RPC-URL** 地址填入。

```js
// ropsten.config.js

module.exports = {
  mnemonic: "你的助记词",
  rpcurl: "RPC 地址" // 格式如：wss://ropsten.infura.io/ws ， 可访问 infura.io 注册申请
}

```

**执行 transforEth.js** 

上一步中，我们领取的 Ropsten 环境 1ETH 应该已经到账了。

transforEth.js 做的事情是：`Account[0]` 转账 0.01ETH 到 `Account[1]`

```shell
node transferEth.js
```

如果看到控制台打印出以下内容，说明转账成功
```json
{ blockHash: '0x47a243a7d3cf9e1a82d2dfb16bb4db65c248ebd8b5188510ae39be3ddfb80633',
  blockNumber: 8008669,
  contractAddress: null,
  cumulativeGasUsed: 412061,
  from: '0x15e35634f38f416830aaf09e35b323b516af6d36',
  gasUsed: 21000,
  logs: [],
  logsBloom: '0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000',
  status: true,
  to: '0x75d60374fd1740d1bcdc033084deaaa57a7d8321',
  transactionHash: '0x2bf9563c4b094d09ad252bce7ffca5f93438ee0797b3c94be5513e9cc77422d8',
  transactionIndex: 8 }

```

最后可以访问 https://ropsten.etherscan.io/ 搜索 transactionHash 来查看转账详情

例如：我在演示中转账成功的 transactionHash 查询地址: [点击查看](https://ropsten.etherscan.io/tx/0x2bf9563c4b094d09ad252bce7ffca5f93438ee0797b3c94be5513e9cc77422d8)

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/jw8zj.png)


至此 Ropsten Test Network 就跑通了，我们成功的在以太坊网络中通过代码完成了一次 0.01ETH 的价值转移。

## 3 配置本地环境

按照上述步骤 Ropsten 环境已经配置成功，那么接下来配置本地开发就非常容易了。

### 3.1 使用 Ganache
本地环境中，提供 JSON-RPC 服务的是，[ganache-cli](https://github.com/trufflesuite/ganache-cli)。

访问 [https://www.trufflesuite.com/ganache](https://www.trufflesuite.com/ganache) 下载 Ganache 客户端;

运行 Ganache，在 `设置` --> `ACCOUNTS & KEYS` 中 配置好你的助记词，点击右上角的 `SAVE AND RESTART`
![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/s4occ.png)

这样你就 Setup 好了一个本地的 JSON-RPC 环境了。

### 3.2 本地环境运行代码
我们来配置一下本地环境，拷贝 RPC SERVER (我默认的地址是：http://127.0.0.1:7545)

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/kd9cn.png)

修改 `local.config.js` 文件

```js
// local.config.js
module.exports = {
  mnemonic: "你的助记词",
  rpcurl: "http://127.0.0.1:7545" 
}

```

切换 `transferEth.js ` 引用的 `local.config.js` 文件

```js
const Web3 = require('web3');
// const config = require('./ropsten.config.js'); // ropsten test network
const config = require('./local.config.js'); // local test network
const HDWalletProvider = require("@truffle/hdwallet-provider");
const mnemonic = config.mnemonic; 
...
```

执行 `tranferEth.js`

```shell
node tranferEth.js
```

同样的，看到如下输出说明成功

```json
{ transactionHash: '0xdd6c68c8ac4071fa1cc5f39d0954d8240b8fcf272dd2dca2765c09cfb93180b1',
  transactionIndex: 0,
  blockHash: '0x9fadfcf19571d574e03cb410e10c0c817fe76a1e4a1339ff89c2f03afcd5c14e',
  blockNumber: 1,
  from: '0x15e35634f38f416830aaf09e35b323b516af6d36',
  to: '0x75d60374fd1740d1bcdc033084deaaa57a7d8321',
  gasUsed: 21000,
  cumulativeGasUsed: 21000,
  contractAddress: null,
  logs: [],
  status: true,
  logsBloom: '0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000' }
```

### 3.3 通过 Ganache 查看本地链上信息

这时再看 Ganache，Account[0] 账户余额变成了 99.99ETH，Account[1]的余额变成了 100.01ETH，说明转账成功。

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/4zdce.png)

我们还可以在 Ganache TRANSACTION 中查看 TX 的细节

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/bptri.png)

至此我们在本地环境中完成了一次价值转移，本地环境搭建成功。

## 总结

通过本章的实践，我们成功跑通了 `Ropsten Test Network` 和 `Local Test Network`，并用通过运行代码完成了 ETH 交易。


下一章节中，我们将主要学习本章中 `transferEth.js` 里所涉及的知识点 --- `Web3.js 工作原理`，`助记词原理详解`。 以及`智能合约的编写、调试与发布`等。

