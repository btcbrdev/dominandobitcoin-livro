#How Bitcoin Works

##Transactions, Blocks, Mining, and the Blockchain

The bitcoin system, unlike traditional banking and payment systems, is based on de-centralized trust. Instead of a central trusted authority, in bitcoin, trust is achieved as an emergent property from the interactions of different participants in the bitcoin system. In this chapter, we will examine bitcoin from a high level by tracking a single transaction through the bitcoin system and watch as it becomes "trusted" and accepted by the bitcoin mechanism of distributed consensus and is finally recorded on the blockchain, the distributed ledger of all transactions.

Each example is based on an actual transaction made on the bitcoin network, simulating the interactions between the users (Joe, Alice, and Bob) by sending funds from one wallet to another. While tracking a transaction through the bitcoin network and blockchain, we will use a blockchain explorer site to visualize each step. A blockchain explorer is a web application that operates as a bitcoin search engine, in that it allows you to search for addresses, transactions, and blocks and see the relationships and flows between them.

Popular blockchain explorers include:  
* [Blockchain info](http://blockchain.info/)  
* Bitcoin Block Explorer  (http://blockexplorer.com/)  
* insight(http://insight.bitpay.com/)  
* blockr Block Reader(http://blockr.io/)  

Each of these has a search function that can take an address, transaction hash, or block number and find the equivalent data on the bitcoin network and blockchain. With each example, we will provide a URL that takes you directly to the relevant entry, so you can study it in detail.

###Bitcoin Overview

In the overview diagram shown in [Bitcoin overview](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#bitcoin-overview), we see that the bitcoin system consists of users with wallets containing keys, transactions that are propagated across the network, and miners who produce (through competitive computation) the consensus blockchain, which is the authoritative ledger of all transactions. In this chapter, we will trace a single transaction as it travels across the network and examine the interactions between each part of the bitcoin system, at a high level. Subsequent chapters will delve into the technology behind wallets, mining, and merchant systems.

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0201.png)

Figure 1. Bitcoin overview

###Buying a Cup of Coffee

Alice, introduced in the previous chapter, is a new user who has just acquired her first bitcoin. In [getting_first_bitcoin](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#getting_first_bitcoin), Alice met with her friend Joe to exchange some cash for bitcoin. The transaction created by Joe funded Alice’s wallet with 0.10 BTC. Now Alice will make her first retail transaction, buying a cup of coffee at Bob’s coffee shop in Palo Alto, California. Bob’s coffee shop recently started accepting bitcoin payments, by adding a bitcoin option to his point-of-sale system. The prices at Bob’s Cafe are listed in the local currency (US dollars), but at the register, customers have the option of paying in either dollars or bitcoin. Alice places her order for a cup of coffee and Bob enters the transaction at the register. The point-of-sale system will convert the total price from US dollars to bitcoins at the prevailing market rate and display the prices in both currencies, as well as show a QR code containing a payment request for this transaction (see [Payment request QR code (Hint: Try to scan this!)](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#payment-request-QR)):

> Total:
> $1.50 USD
> 0.015 BTC

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0202.png)