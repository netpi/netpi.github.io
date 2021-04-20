---
title: "如何用一台 MacBook 创造高额年化收益 | ETH2.0 Staking 教程"
date: 2020-06-05T14:32:35+08:00
categories: 
- ETH2.0
tags:
- Ethereum2.0
- ETH2.0
- blockchain
keywords: Ethereum2.0 ETH2.0 Staking blockchain
description: 根据 ETH2.0（以太坊2.0）的 PoS（权益证明）共识机制，只要持有一定数量的以太坊就可以成为 Validator（验证者），而 Validator 参与 Vote（投票）之后，会获得报酬。
cover_p: https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/zdf1h.png
---

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/pln5g.png)


## **1，ETH2.0 Staking 介绍**

**简单说，根据 ETH2.0（以太坊2.0）的 PoS（权益证明）共识机制，只要持有一定数量的以太坊就可以成为 Validator（验证者），而 Validator 参与 Vote（投票）之后，会获得报酬。**

我个人亲自实践，发现获得收益的门槛并不是很高，有 **一台持续运行的 MacBook** 和 **一定数量的以太坊** 就可以参与。目前我已经成功成为测试网络中的 Validator，只要笔记本开着每天都可以获得 ETH 收益 。
可以到访问 [这个网站](https://beacon.etherscan.io/validator/0x9001858bc999658b984c117fa6e17381c9422725b126902aa01e336d169c3254d84690df59ccedc8ba6771eca994fc28) 来查看我的收益情况。

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/lmbma.png)


目前 ETH2.0 还处在测试阶段，我所获得的收益目前也在测试网络中。

然而 ETH2.0 Phase 0 的上线脚步临近了，官方要求的上线条件是：测试网络下多个节点文档运行两个月以上。
根据 https://beacon.etherscan.io/ 的数据显示：beacon 网络中的活跃的 validators 数量已经达到 39653 个。

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/x6guf.png)


虽然 ETH2.0 正式环境还没上线，但我们要做到未雨绸缪。要想在 ETH2.0 Phase 0 正式上线的时快速接入，**第一时间获得收益**。那么提前在测试环境中跑通流程就是非常必要了。

***

## **2，成为 Validator 的收益如何**


根据 beacon 网络提供的 [收益计算器](https://beacon.etherscan.io/staking-calculator) 来看：

**`ETH2.0 的年化收益可以达到 > 8%。`** 

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/5qyko.png)

注意，这里的 8%是 ETH 数量的收益：

比如质押 32ETH 成为 Validator，一年之后的总资产大约是 `32*1.08=34.56ETH`。

初期如果考虑技术门槛风险系数等，**我个人认为收益会高于8%；（目前已达到 10.44%）**

如果再考虑 ETH 本身的价值波动，那么收益可自己想象。我个人是 ETH2.0 的技术参与者，非常看好其后期的表现（产品上的表现，不发表币价观点）；

***

## **3，参与 ETH2.0 Staking 都需要什么**

### **3.1，需要 32ETH 锁仓**

ETH2.0 Staking，就是一个质押系统，参与者要将 32ETH 按规定质押锁仓之后才能成为 Validator。这是因为 ETH2.0 有 Slashed 机制，如果一名 Validator 有恶意行为（参与双花攻击等）或者经常偷懒（经常离线），那么 Validator 就会受到一定的经济惩罚，情节严重者不但不能获得收益，而且本身抵押的 32ETH 也会受到一定损失。

还有一点要注意，这个锁仓要很久，要等到 ETH2.0 Phase 2 上线，估计要 2 年左右的时间。这期间 32ETH 的锁仓是 `one-way` 的，一旦锁仓中途无法返还。



### **3.2，硬件要求**
* 最小可运行的配置要求：
  * 64-bit Linux, Mac OS X 10.14+ (Mojave+), Windows
  * Processor: Intel Core i5–760 or AMD FX-8100 or better
  * Memory: 4GB RAM
  * Storage: 20GB available space SSD
  * Internet: Broadband connection

* 推荐的配置要求
  * Processor: Intel Core i7–4770 or AMD FX-8310 or better
  * Memory: 8GB RAM
  * Storage: 100GB available space SSD
  * Internet: Broadband connection

我个人目前使用一台闲置的 2016年的 Macbook Pro 来做 Staking。现在看起来，支撑一个 Validator 性能错错有余。

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/xq8ve.png)


***

## **4，开始 ETH2.0 Staking**


### **4.1，Beacon-Chain （ 信标链 ）和 Validator（ 验证者）**

要想顺利参与 Staking 获得收益，就要先搞清楚 `Beacon-Chain` 和 `Validator` 是什么。

* **Beacon-Chain** ： Beacon-Chain 就像一个总调度系统、可以让 Validator 参质押系统、代替矿工成为链的构建者、还会为 Validator 分配任务等。

* **Validator** ： 在 PoS 共识机制下，每个区块都是由 Validator 选择出来的，Validator 通过投票验证区块，获得收益。


**因此我们需要在电脑上同时运行两个进程：`Beacon-Chain` 和 `Validator`**
![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/halmc.png)


**运行 Beacon-Chain 和 Validator 就要使用 ETH2.0 的客户端。**

以太坊官方孵化的 ETH2.0 测试客户端还是挺多的，但是我推荐用 GO 语言写的 [Prysm](https://github.com/prysmaticlabs/prysm)。

Prysm 是 Prysmatic Labs 开发并且以太坊基金会投入扶持基金最多的的 ETH2.0 客户端，现在产品仍在不断更新完善，社区答疑也的非常积极。如果遇到疑问也随时可以到 [Prysm discord 讨论组](https://discord.com/invite/YMVYzv6) 提问。


### **4.2，安装Prysm 客户端 & 运行 Beacon-Chain**


1.创建一个文件夹，用来存放 prysm 脚本

```sh
mkdir prysm && cd prysm
```

2.把 `prysm.sh` 拉倒本地，并且增加一个可执行权限
```sh
curl https://raw.githubusercontent.com/prysmaticlabs/prysm/master/prysm.sh --output prysm.sh && chmod +x prysm.sh
```

3.运行 `Beacon-Chain`

```sh
./prysm.sh beacon-chain --datadir=$HOME/.eth2

```

看到如下信息就说明开始同步区块数据了，我当时同步完成用了大概3个小时，目前我同步到最新（ 2020.6.6 ）数据大小 5.23G。

```sh
./prysm.sh beacon-chain --datadir=$HOME/.eth2
Latest Prysm version is v0.3.3.
Downloading beacon-chain@v0.3.3 to /home/{USER}/prysm/dist/beacon-chain-v0.3.3-linux-amd64 (automatically selected latest available version)
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   622  100   622    0     0   2320      0 --:--:-- --:--:-- --:--:--  2312
100 39.6M  100 39.6M    0     0  13.6M      0  0:00:02  0:00:02 --:--:-- 20.4M
Downloading validator@v0.3.3 to /home/{USER}/prysm/dist/validator-v0.3.3-linux-amd64 (automatically selected latest available version)
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   619  100   619    0     0   1484      0 --:--:-- --:--:-- --:--:--  1484
100 32.5M  100 32.5M    0     0  12.6M      0  0:00:02  0:00:02 --:--:-- 21.7M
Starting Prysm beacon-chain
...
```

### **4.3，获得测试网络 32ETH**

成为 Validator 需要我们把 32ETH 存入指定 ETH1.0 的锁仓合约。

Prysm 把锁仓合约部署在了 Göerli Testnet 中。
Göerli Testnet 是 Proof-of-Authority（PoA权威证明） 的区块链网络。

为什么选择 Göerli Testnet？

Prysm 的技术负责人（Preston Van Loon）的说法是为了拿到足够的测试代币：

> 使用 Görli 进行测试，是因为它们还没有正式上线，所以我们可以在它们的网络中要到大量的代币。我向他们要了 1000 万枚，这是我们实际需要启动以太坊 2.0 的数量
>
> --- Preston Van Loon


#### **那么如何获得 Göerli Testnet 的 32ETH？**

到这里：[https://faucet.goerli.mudit.blog/](https://faucet.goerli.mudit.blog/)

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/2l6fi.png)

这是我测试下来最快获得 32ETH 的方式，用 Twitter 或 Facebook 发一条带有你 ETH 地址的推文。然后把那条推文的链接贴进输入框，选择 `37.5 ETH/9 days`，确定。

我个人使用的时候发现贴 Twitter 的推文会提示找不到以太坊地址，**后来用 Facebook 的推文成功获得 37.5 ETH**。


###  **4.4，生成 Validator 密钥对**

得到了 37.5ETH 之后，我们要开始生成 Validator 的密钥对了

```
./prysm.sh validator accounts create --keystore-path=$HOME/.eth2validator

```
这条指令会在 $HOME/.eth2validator 文件夹下面生成密钥对，命令输出一段 Raw Transaction Data ：

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/mgxhf.png)

把 `===Deposit Data===` 保存好，后面质押 32ETH 的时候要一起提交到合约。

### **4.5，启动 Validator 客户端**
**用 `prysm.sh` 启动 Validator 客户端**

```
./prysm.sh validator --keystore-path=$HOME/.eth2validator
```
这时会提示 beacon-chain 正在等待收到你的 32ETH 的质押记录。
```sh
INFO validator: Waiting for beacon chain start log from the ETH 1.0 deposit contract
```

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/choss.png)

接下来就将 32ETH 按规定转入质押合约，完成 Validator 注册。

### **4.5，提交 32ETH 至锁仓合约**

注意，这一步并不是把 32ETH 直接转入锁仓合约就可以了。我们还需要把之前生成的 Raw Transaction Data 一起提交。

我们用这个网站 https://prylabs.net/participate 来帮助我们完成提交

把 4.4 中生成的 Raw Transaction Data 填入

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/1fezo.png)

在第5步中点击 `Make deposit` (确保 matemask 切换至 Goerli Network，并且有 >32ETH)

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/oom7j.png)


### **4.6，等待 Validator 激活，获得持续收益**

完成以上步骤之后，我们要保持 Terminal 同时运行 `Beacon-chain` 和 `Validator` 两个进程，然后等待 Validator 激活，持续获得收益。

这个等待的过程加起来大概要 7.5小时左右（1024 个 ETH 1.0 的 Block 确认 和 1024 ETH2.0 Slot 确认）。

我们可以到 https://beacon.ethereum.io 来查看 Validator 激活的状态。

这是 Beacon-chain 同步完成的这状态

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/kmkf4.png)

这是 Validator 已激活工作中的状态

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/psko1.png)

***

## 补充事项

* 一个 Validator 的收益与责任是并存的，持续保持在线可以获得收益，但是如果离线也会受到惩罚。惩罚会根据离线时间扣除收入，如果在线时间低于 75% 就会开始亏钱了。
* 32ETH 是要锁仓很久的，ETH2.0 Phase 2 上线预计要两年左右。这期间 32ETH 是无法移动的。
* 同一个客户端可以运行多个 `Validators`，需要的电脑配置也会增加
* 查看自己的公钥私钥可以用 `/prysm.sh validator accounts keys --keystore-path=$HOME/.eth2validator/ --password=password` 
* 使用树莓派作为挖矿节点已经变成可能，树莓派4就可以。Prysm 的预编译代码 [点击查看](https://github.com/prysmaticlabs/prysm/releases)




