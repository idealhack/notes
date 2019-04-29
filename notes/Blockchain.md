# Blockchain

## Overview

- [区块链 - 维基百科](https://zh.wikipedia.org/wiki/%E5%8C%BA%E5%9D%97%E9%93%BE)

### How blockchain born

- 近 30 年，人类在数字货币系统方向不断尝试，积累了不少经验
- 2008 年 10 月 31 日，Satoshi Nakamoto（中本聪）发布比特币白皮书，提出了区块链
- 2009 年，区块链在比特币中被实现和开源，第一个比特币于 2009 年 1 月 3 日生成

### What is blockchain

> A blockchain, originally block chain, is a continuously growing list of records, called blocks, which are linked and secured using cryptography.

> 区块链（英语：blockchain 或 block chain）是用分布式数据库识别、传播和记载信息的智能化对等网络, 也称为价值互联网。

一句话：分布式账本

- 交易（Transaction）：一次操作，导致账本状态的一次改变，如添加一条记录；
- 区块（Block）：记录一段时间内发生的交易和状态结果，是对当前账本状态的一次共识；
- 链（Chain）：由一个个区块按照发生顺序串联而成，是整个状态变化的日志记录。

区块链通过去中心化，解决了信任问题，但是带来了性能问题。

对于一致性（共识），由于存在拜占庭问题，区块链并不能使用传统分布式系统常用的 Paxos 或 Raft 算法，而是使用 PoW（Proof-of-Work 工作量证明）、PoS（Proof-of-Stake 权益证明）或 DPOS（Delegated Proof-of-Stake-of权益证明）等共识算法。

### How can it be used

You don’t need a block chain, if

- you don’t need a database
- not many people need to write to it
- those people trust each other
- they have on person in common they trust

## Applications

- [[Cryptocurrency]]
- [[Ethereum]]
- Hyperledger
- Ripple
- [Stellar](https://www.stellar.org/)
- [IPFS is the Distributed Web](https://ipfs.io/)

## Resources

- [chaozh/awesome-blockchain: 收集所有区块链(BlockChain)技术开发相关资料，包括Fabric和Ethereum开发资料](https://github.com/chaozh/awesome-blockchain-cn)
- [Xel/Blockchain-stuff: Blockchain and Crytocurrency Resources](https://github.com/Xel/Blockchain-stuff)
- [machinomy/awesome-non-financial-blockchain: Curated list of projects that build non-financial applications of blockchain](https://github.com/machinomy/awesome-non-financial-blockchain)
- [openblockchains/awesome-blockchains: A collection about awesome blockchains - open distributed public databases w/ crypto hashes incl. git ;-). Blockchains are the new tulips . Distributed is the new centralized.](https://github.com/openblockchains/awesome-blockchains)
- [区块链世界来龙去脉，峰瑞资本内部分享 – 代码家](https://daimajia.com/2018/02/10/blockchain-share-in-freesfund)
- [纠正你对区块链的认知偏见](https://mp.weixin.qq.com/s/Q9ZRHbRI5lkqAn1NLkDzXg)
- [教程 | 如何成为区块链开发者：速成课！ » 论坛 » EthFans | 以太坊爱好者](https://ethfans.org/posts/blockchain-developer-crash-course)
- [加密货币和区块链（二）：分布式共识与去中心化 | 1 Byte](https://1byte.io/cryptocurrencies-and-blockchains-consensus-and-decentralization/)
- [SegmentFault 技术周刊 Vol.41 - 深入学习区块链 - SegmentFault 社区周刊 - SegmentFault 思否](https://segmentfault.com/a/1190000012894266)

### Books

- [bitcoinbook/bitcoinbook: Mastering Bitcoin 2nd Edition - Programming the Open Blockchain](https://github.com/bitcoinbook/bitcoinbook)

### Samples

- [Jeiwan/blockchain_go: A simplified blockchain implementation in Golang](https://github.com/Jeiwan/blockchain_go)
- [GitHub - dvf/blockchain: A simple Blockchain in Python](https://github.com/dvf/blockchain)
- [lhartikk/naivechain: A blockchain implementation in 200 lines of code](https://github.com/lhartikk/naivechain)
- [Coral Health blockchain in Go … on K8s ;-) – Daz Wilkin – Medium](https://medium.com/@DazWilkin/coral-health-blockchain-in-go-on-k8s-c7700e1670b7)

### Videos

- [How Bitcoin Works in 5 Minutes (Technical) - YouTube](https://www.youtube.com/watch?v=l9jOJk30eQs)
- [Ever wonder how Bitcoin (and other cryptocurrencies) actually work? - YouTube](https://www.youtube.com/watch?v=bBC-nXj3Ng4)
- [liyuechun/blockchain_go_videos: Golang公链开发系统视频教程](https://github.com/liyuechun/blockchain_go_videos)
