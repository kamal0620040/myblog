---
title: Understanding Blockchain Terminology - Part 1
date: "2022-07-24T12:40:32.169Z"
template: "post"
draft: false
slug: "blockchain-terms"
category: "Blockchain"
tags:
  - "Web3"
# description: "A blog about restful api."
socialImage: "/media/blockchain.png"
---

# Cryptocurrencies
When people hear about the word blockchain they automatically associate it with cryptocurrencies but these are actually two different things and it’s important to understand the difference.


Blockchain is a technology it’s neutral depending on what kind of data you store in the blockchain it can be used for very different purposes the most popular use of blockchain technology has been cryptocurrencies. There are many cryptocurrencies. Bitcoin adds a special place amount the cryptocurrencies because it’s the first cryptocurrency that introduces blockchain technology in 2009. 

So, if you want to have a good understanding of how blockchain works it’s a good thing to study bitcoin. Bitcoin allows the transfer of virtual currencies that we called bitcoin between different addresses. Bitcoin addresses are identifiers composed of alphanumeric characters.

![address](/media/addresses.jpg)

Each of these addressees is associated with a bitcoin balance. The owner of an address is able to spend his or her bitcoin and send them to another address. The blockchain of Bitcoin records bitcoin transfers in what we called transactions. These transactions are put inside blocks and these blocks are linked to each other. If you want to compute the balance of a specific address you have to go through all the blocks of the blockchain and take into consideration all the relevant actions. In bitcoin like in other cryptocurrencies, addresses are managed by external software that we called wallets. The blockchain itself doesn’t have any centralized management of addresses. Everybody is free to create as many addresses as they want with their wallets.

New bitcoin are regularly created by the blockchain we want the miner who successfully adds new blocks. This creation is not infinite and it will stop at some points which will limit the inflation of bitcoin. Most people think bitcoin can only do financial transactions but this is not actually technically true. Bitcoin can process slightly more complex financial transactions using what we called bitcoin scripting.

But that’s not very powerful, very few people use that, and generally speaking it’s not easy to build a blockchain application on top of bitcoin.


# Ethereum

Bitcoin was the first blockchain. It was really revolutionary however it was quite limited. That’s why Ethereum was created in 2013. Ethereum is a blockchain of the second generation capable of not only processing simple financial transactions but also any arbitrary computation. This allows the building of much more sophisticated applications on top of the blockchain. 

At the very core of Ethereum, we have the same technology that we have in the blockchain. In the Ethereum blockchain, we have a series of blocks. In each block we have transactions and we also have miners who add a new block to the Ethereum blockchain using the proof of work algorithm. We also have addresses. Each Ethereum address is associated with the cryptocurrency called ether. And if you own an address we can transfer ether to another address. However, at the top of this basic blockchain technology, there is another part called Ethereum Virtual Machine(EVM). The EVM is able to run a small program called a smart contract. A smart contract can run code and manipulate ether (the cryptocurrency of Ethereum). For example, with Ethereum, you can code multi-signature wallets where you need the approval of several people before spending any ether. The beauty of smart contracts is that their code is executed on the blockchain. So you don’t need any third party to execute them. Once the code of the smart contract is deployed on the blockchain nobody is able to change the code or stop the smart contract from running it's just on the blockchain forever. Another benefit of a smart contract is it’s very hard to hack them.

# Cryptographic Hashes

Cryptographic hashes are used a lot in the blockchain. For example, transactions are identified by a hash. So it’s actually important to understand what is hash. A cryptographic hash is a fingerprint. It uniquely identifies a piece of data. It usually looks like a gibberish piece of characters. This gibberish in itself has no meaning. All we care about is uniquely identifying a piece of data. If we change just one character of data, the hash will be completely different. So how do we produce this hash? For that, we use a cryptographic hash function like sha2, sha3. A cryptographic hash function will take any data as input and transfer it into a fixed-size cryptographic hash as output.

The size of the input data doesn’t matter. But the cryptographic hash always has the same size. Another important thing about hashes is cryptographic hash function is a one way operation. You can go from an input to a cryptographic hash but you cannot go from a cryptographic hash to input. That’s important for privacy because if you want to represent some data on the blockchain but you don’t want to reveal what the data is.

On Ethereum the hashing function that we use is Keccak256.

# Ethereum addresses

Ethereum the rule of addresses is to send and receive ether. 

### What is a private key?
That’s a very long number generated randomly. It must be kept secret like the password. So we have the secret private key.

![private-key](/media/private-key.jpg)

Then by using what we called Elliptic cryptography we generate another long number called a public key. With elliptic cryptography, you can go from a private key to a public key very easily but not the other way around. This public key is 128 char long.

We compute the hash of this public key using the k26 hash function. So in another word we compute the fingerprint of this public key. This fingerprint is the string that is 64 characters long we take the last 40 characters. Finally, we prefix 0x. So in the end you have 42 characters that are your address. 

![workflow](/media/workflow.jpg)

Now we have our address what can we do about it? First of all, we can give it to anyone if we want to receive some ether. Second, we can use the private key that we used to generate the address if you want to send ether to another address. Technically that is called a sign a transaction.

### Where are these addresses created?

It doesn’t happen on the Ethereum blockchain. instead, these addresses are created using the external software like called wallets