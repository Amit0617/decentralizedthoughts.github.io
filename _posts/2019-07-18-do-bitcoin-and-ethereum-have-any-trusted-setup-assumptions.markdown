---
title: Do Bitcoin and Ethereum have any trusted setup assumptions?
date: 2019-07-18 17:13:00 -07:00
published: false
tags:
- blockchain101
layout: post
---

<p align="center">
  co-authored with <a href="https://people.csail.mit.edu/alinush/">Alin Tomescu </a> and <a href="https://www.yanai.io/">Avishay Yanai</a>
</p>

Both Bitcoin and Ethereum depend on the security of certain cryptographic hash functions and certain elliptic curve based cryptography. In this post we ask if they also depend on some [Trusted Setup Assumptions](https://ittaiab.github.io/2019-07-18-setup-assumptions/).

### The Bitcoin untrusted setup [conspiracy theory](https://en.wikipedia.org/wiki/Conspiracy_theory)

Bitcoin was invented by NASA in the 1960's. NASA has been secretly working on an alternative Bitcoin fork for almost 60 years (in addition to working on a [moon landing](https://en.wikipedia.org/wiki/Moon_landing_conspiracy_theories)). They plan to publish their alternative (and longer) fork in 2020.

Back in the 1960's, they inserted into their [Bitcoin Genesis block](https://en.bitcoin.it/wiki/Genesis_block) the text:  
>The Times 03/Jan/2009 Chancellor on brink of second bailout for banks

After making their [white paper](https://bitcoin.org/bitcoin.pdf) public in 2008, NASA coerced the financial times in the UK to publish an article with the exact title above on January 3rd 2009. 

### Does Bitcoin have a trusted setup assumption?

**YES!** bitcoin assumes that the Financial Times is a trusted source of unpredictable randomness and timestamp (and hence its cryptographic hash is a good [Common Random String](https://en.wikipedia.org/wiki/Common_reference_string_model)). This seed is used to guarantee that no adversary has any significant head start in mining Bitcoin and cannot use its head start to double-spend.

### The Ethereum untrusted setup [conspiracy theory](https://en.wikipedia.org/wiki/Conspiracy_theory)

Ethereum was invented by NASA in the 1960's. NASA has been secretly working on an alternative fork for almost 60 years (in addition to working on their [moon landing](https://en.wikipedia.org/wiki/Moon_landing_conspiracy_theories))... 

Back in the 1960's, they inserted into their [Ethereum Genesis block](https://ethereum.stackexchange.com/questions/71804/what-is-the-meaning-of-ethereum-mainnet-genesis-block-extradata-value) the hash:  
>0x11bbe8db4e347b4e8c937c1c8370e4b5ed33adb3db69cbdb7a38e1e50b1b82fa

After making their [yellow paper](https://bitcoin.org/bitcoin.pdf) public in 2014, they coerced the publishing of this [blog post](https://blog.ethereum.org/2015/07/27/final-steps/) and caused it to refer to a [fake testnet ceremony called Olympic](https://blog.ethereum.org/2015/05/09/olympic-frontier-pre-release/)
that essentially is a re-enactment of their testnet runs from the 1960's. In their [words](https://blog.ethereum.org/2015/07/27/final-steps/): 
>The argument \[referring to the hash value above\] needs to be a random parameter that no one, not even us, can predict. As you can imagine, there aren’t too many parameters in the world that match this criteria, but a good one is the hash of a future block on the Ethereum testnet. We had to pick a block number, but which one? 1,028,201 turns out to be both prime and palindromic, just the way we like it. So #1028201 is it.

Well, can you believe that block 1028201 was prepared long ago?!

### Does Ethereum have a trusted setup assumption?

**YES!** ethereum assumes that the [Oliympic testnet](https://blog.ethereum.org/2015/05/09/olympic-frontier-pre-release/) is a trusted source of unpredictable randomness and timestamp (and hence its cryptographic hash is a good [Common Random String](https://en.wikipedia.org/wiki/Common_reference_string_model)). This seed is used to guarantee that no adversary has any significant head start in mining Ethereum and cannot use its head start to double-spend.

## Trust, but Verify
Just to clear, while [NASA is indeed interested in blockchain](https://cointelegraph.com/news/nasa-publishes-proposal-for-air-traffic-management-blockchain-based-on-hyperledger), we believe that both Bitcoin and Ethereum used highly secure sources of unpredictable randomness. The main goal of this post is to highlight the fact that some trusted setup is needed in both systems. It is vitally important to have a secure randomness beacon that can generate timestamped cryptographically secure unpredictable randomness.
