---
title: Blockchain
date: "2022-02-10T12:40:32.169Z"
template: "post"
draft: false
slug: "blockchain"
category: "web3"
tags:
  - "Web3"
  - "Blockchain"
description: "A blog about blockchain that essentially familiarizes the reader about what blockchain is."
socialImage: "/media/blockchain.png"
---

- [Introduction](#introduction)
- [What does each block contains?](#what-does-each-block-contains)
- [What makes it different than traditional database?](#what-makes-it-different-than-traditional-database)
- [Pros compared to traditional database](#pros-compared-to-traditional-database)
- [Cons compared to traditional database](#cons-compared-to-traditional-database)

![blockchain.png](/media/blockchain.png)

## Introduction
Blockchain is a special kind of database and its main function is to store data. Like it’s name implies a blockchain is a series of block of data like block 1, block 2, etc. These blocks are linked to each other with cryptography. Block 3 references block 2 which references block 1 etc. That’s why we call it a blockchain.
![block-reference.jpg](/media/block-reference.jpg)

## What does each block contains?
In each block there are two-part first you have the metadata. In metadata, you can find information such as the timestamp at which the block is created, the reference to the previous block, and the cryptographic signature of all the transactions. 

![block-entity.jpg](/media/block-entity.jpg)

And the other part of the block is transactions. Transactions describe how data changes. For example, for bitcoin, a transaction describes how bitcoin is transferred from one account to another one. The term transaction is a bit misleading here. The example above is in terms of the financial transaction but actually, a blockchain transaction describes a change of any kind of data not only a financial transaction. 

### What makes it different than traditional database?
> So, now you might with this blockchain thing we have blocks and transactions but this is just about the structure of data on blockchain but nothing is really revolutionary here. So what’s the big deal about blockchain? 

Actually, there are quite a few very important differences with the traditional database. So let’s start with **immutability**. With blockchain, you can only add data to the blockchain with a new block but you can never modify data that are already in the blockchain. So the blocks that are already in the blockchain you absolutely can’t touch them. That’s very different from the traditional database where you can change any data at any time.

Now, let’s talk about the blockchain network and the decentralized nature of blockchain. Blockchain does not run on a single computer but instead, it runs on a network of computers that are connected to each other. Each computer is called a node and together they form a blockchain network.

![decentralized.jpg](/media/decentralize.jpg)

Anybody can run a blockchain node and be a part of the blockchain in the network. That’s why we say that blockchain runs on a public network. They are ready databases that can run on several nodes. We call this distributed database. However, none of them run on a public network they all run on a public network.

> So if anybody can run a node on a blockchain network how can these network be secured? 

So, for that, there is the mining process. If you want to add data to the blockchain you need to add a new block to the blockchain with transactions that describes all the changes to the data that you want to bring to the blockchain. If you want to do this you need to engage in a process called mining. Any node on a blockchain network can be a miner. When you are a miner, you compete with the other miners to solve a mathematical equations. The first miner that solves the mathematical equations has a right to add the next block to the blockchain. This mining process is describes in a form of an algorithm called Proof-Of-Work (POW). Without getting about the details whats great about POW is that it is it’s very difficult to hack and it does not rely on any centralized company. 

## Pros compared to traditional database
- First, it’s immutable which means you cannot change any data once it has been added to the network.
- Then it’s decentralized and censorship-resistant. So a single actor cannot control the network. 
- Finally, it’s secure, especially thanks to the POW algorithm that is almost impossible to hack. 

## Cons compared to traditional database
- First, blockchain is much much slower than the traditional database because you have to synchronous data across the whole network that’s usually distributed globally.
- Another disadvantage is that it’s less scalable. Because you have to sync data across this whole network the capacity for this network to absorb more incoming transactions is much much more limited than a centralized database. This problem is so important that actually the whole blockchain industry is focused on solving this problem.
- It’s much more expensive because you have to pay miners for their service of adding data to the blockchain. For this reason, we avoid putting too much data on the blockchain.
- Because blockchains are the public network there is no privacy. Any data you put on the blockchain can be seen by anybody