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

Figure 2. Payment request QR code (Hint: Try to scan this!)

The payment request QR code encodes the following URL, defined in BIP0021:
> bitcoin:1GdK9UzpHBzqzX2A9JFP3Di4weBwqgmoQA?  
> amount=0.015&  
> label=Bob%27s%20Cafe&  
> message=Purchase%20at%20Bob%27s%20Cafe  
>  
> Components of the URL  
>  
> A bitcoin address: "1GdK9UzpHBzqzX2A9JFP3Di4weBwqgmoQA"  
> The payment amount: "0.015"  
> A label for the recipient address: "Bob's Cafe"  
> A description for the payment: "Purchase at Bob's Cafe"

[Tip]
>Unlike a QR code that simply contains a destination bitcoin address, a payment request is a QR-encoded URL that contains a destination address, a payment amount, and a generic description such as "Bob’s Cafe." This allows a bitcoin wallet application to prefill the information used to send the payment while showing a human-readable description to the user. You can scan the QR code with a bitcoin wallet application to see what Alice would see.

Bob says, "That’s one-dollar-fifty, or fifteen millibits."

Alice uses her smartphone to scan the barcode on display. Her smartphone shows a payment of *0.0150 BTC* to *Bob’s Cafe* and she selects *Send* to authorize the payment. Within a few seconds (about the same amount of time as a credit card authorization), Bob would see the transaction on the register, completing the transaction.

In the following sections we will examine this transaction in more detail, see how Alice’s wallet constructed it, how it was propagated across the network, how it was verified, and finally, how Bob can spend that amount in subsequent transactions.

Note
>The bitcoin network can transact in fractional values, e.g., from milli-bitcoins (1/1000th of a bitcoin) down to 1/100,000,000th of a bitcoin, which is known as a satoshi. Throughout this book we’ll use the term “bitcoin” to refer to any quantity of bitcoin currency, from the smallest unit (1 satoshi) to the total number (21,000,000) of all bitcoins that will ever be mined.

##Bitcoin Transactions

In simple terms, a transaction tells the network that the owner of a number of bitcoins has authorized the transfer of some of those bitcoins to another owner. The new owner can now spend these bitcoins by creating another transaction that authorizes transfer to another owner, and so on, in a chain of ownership.

Transactions are like lines in a double-entry bookkeeping ledger. In simple terms, each transaction contains one or more "inputs," which are debits against a bitcoin account. On the other side of the transaction, there are one or more "outputs," which are credits added to a bitcoin account. The inputs and outputs (debits and credits) do not necessarily add up to the same amount. Instead, outputs add up to slightly less than inputs and the difference represents an implied "transaction fee," which is a small payment collected by the miner who includes the transaction in the ledger. A bitcoin transaction is shown as a bookkeeping ledger entry in [Transaction as double-entry bookkeeping](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-double-entry).

The transaction also contains proof of ownership for each amount of bitcoin (inputs) whose value is transferred, in the form of a digital signature from the owner, which can be independently validated by anyone. In bitcoin terms, "spending" is signing a transaction that transfers value from a previous transaction over to a new owner identified by a bitcoin address.

Tip
>_Transactions_ move value from _transaction inputs_ to _transaction outputs_. An input is where the coin value is coming from, usually a previous transaction’s output. A transaction output assigns a new owner to the value by associating it with a key. The destination key is called an _encumbrance_. It imposes a requirement for a signature for the funds to be redeemed in future transactions. Outputs from one transaction can be used as inputs in a new transaction, thus creating a chain of ownership as the value is moved from address to address (see [A chain of transactions, where the output of one transaction is the input of the next transaction](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#blockchain-mnemonic)).

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0203.png)
Figure 3. Transaction as double-entry bookkeeping

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0204.png)
Figure 4. A chain of transactions, where the output of one transaction is the input of the next transaction

Alice’s payment to Bob’s Cafe uses a previous transaction as its input. In the previous chapter Alice received bitcoin from her friend Joe in return for cash. That transaction has a number of bitcoins locked (encumbered) against Alice’s key. Her new transaction to Bob’s Cafe references the previous transaction as an input and creates new outputs to pay for the cup of coffee and receive change. The transactions form a chain, where the inputs from the latest transaction correspond to outputs from previous transactions. Alice’s key provides the signature that unlocks those previous transaction outputs, thereby proving to the bitcoin network that she owns the funds. She attaches the payment for coffee to Bob’s address, thereby "encumbering" that output with the requirement that Bob produces a signature in order to spend that amount. This represents a transfer of value between Alice and Bob. This chain of transactions, from Joe to Alice to Bob, is illustrated in [A chain of transactions, where the output of one transaction is the input of the next transaction](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#blockchain-mnemonic).

###Common Transaction Forms

The most common form of transaction is a simple payment from one address to another, which often includes some "change" returned to the original owner. This type of transaction has one input and two outputs and is shown in [Most common transaction](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-common).

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0205.png)
Figure 5. Most common transaction

Another common form of transaction is one that aggregates several inputs into a single output (see [Transaction aggregating funds](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-aggregating)). This represents the real-world equivalent of exchanging a pile of coins and currency notes for a single larger note. Transactions like these are sometimes generated by wallet applications to clean up lots of smaller amounts that were received as change for payments.

![](https://github.com/aantonop/bitcoinbook/blob/develop/images/msbt_0206.png)
Figure 6. Transaction aggregating funds
Finally, another transaction form that is seen often on the bitcoin ledger is a transaction that distributes one input to multiple outputs representing multiple recipients (see [Transaction distributing funds](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-distributing)). This type of transaction is sometimes used by commercial entities to distribute funds, such as when processing payroll payments to multiple employees.

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0207.png)
Figure 7. Transaction distributing funds

##Constructing a Transaction

Alice’s wallet application contains all the logic for selecting appropriate inputs and outputs to build a transaction to Alice’s specification. Alice only needs to specify a destination and an amount and the rest happens in the wallet application without her seeing the details. Importantly, a wallet application can construct transactions even if it is completely offline. Like writing a check at home and later sending it to the bank in an envelope, the transaction does not need to be constructed and signed while connected to the bitcoin network. It only has to be sent to the network eventually for it to be executed.

###Getting the Right Inputs

Alice’s wallet application will first have to find inputs that can pay for the amount she wants to send to Bob. Most wallet applications keep a small database of "unspent transaction outputs" that are locked (encumbered) with the wallet’s own keys. Therefore, Alice’s wallet would contain a copy of the transaction output from Joe’s transaction, which was created in exchange for cash (see [getting_first_bitcoin](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#getting_first_bitcoin)). A bitcoin wallet application that runs as a full-index client actually contains a copy of every unspent output from every transaction in the blockchain. This allows a wallet to construct transaction inputs as well as quickly verify incoming transactions as having correct inputs. However, because a full-index client takes up a lot of disk space, most user wallets run "lightweight" clients that track only the user’s own unspent outputs.

If the wallet application does not maintain a copy of unspent transaction outputs, it can query the bitcoin network to retrieve this information, using a variety of APIs available by different providers or by asking a full-index node using the bitcoin JSON RPC API. [Look up all the unspent outputs for Alice’s bitcoin address](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#example_2-1) shows a RESTful API request, constructed as an HTTP GET command to a specific URL. This URL will return all the unspent transaction outputs for an address, giving any application the information it needs to construct transaction inputs for spending. We use the simple command-line HTTP client cURL to retrieve the response.

Example 1. Look up all the unspent outputs for Alice’s bitcoin address


{

 $ curl https://blockchain.info/unspent?active=1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK

}

Example 2. Response to the lookup


{

	"unspent_outputs":[

		{
			"tx_hash":"186f9f998a5...2836dd734d2804fe65fa35779",
			"tx_index":104810202,
			"tx_output_n": 0,	
			"script":"76a9147f9b1a7fb68d60c536c2fd8aeaa53a8f3cc025a888ac",
			"value": 10000000,
			"value_hex": "00989680",
			"confirmations":0
		}
  
	]

}

The response in [Response to the lookup](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#example_2-2) shows one unspent output (one that has not been redeemed yet) under the ownership of Alice’s address **1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK**. The response includes the reference to the transaction in which this unspent output is contained (the payment from Joe) and its value in satoshis, at 10 million, equivalent to 0.10 bitcoin. With this information, Alice’s wallet application can construct a transaction to transfer that value to new owner addresses.

Tip
>View the [transaction from Joe to Alice](http://bit.ly/1tAeeGr).

As you can see, Alice’s wallet contains enough bitcoins in a single unspent output to pay for the cup of coffee. Had this not been the case, Alice’s wallet application might have to "rummage" through a pile of smaller unspent outputs, like picking coins from a purse until it could find enough to pay for coffee. In both cases, there might be a need to get some change back, which we will see in the next section, as the wallet application creates the transaction outputs (payments).

###Creating the Outputs

A transaction output is created in the form of a script that creates an encumbrance on the value and can only be redeemed by the introduction of a solution to the script. In simpler terms, Alice’s transaction output will contain a script that says something like, "This output is payable to whoever can present a signature from the key corresponding to Bob’s public address." Because only Bob has the wallet with the keys corresponding to that address, only Bob’s wallet can present such a signature to redeem this output. Alice will therefore "encumber" the output value with a demand for a signature from Bob.

This transaction will also include a second output, because Alice’s funds are in the form of a 0.10 BTC output, too much money for the 0.015 BTC cup of coffee. Alice will need 0.085 BTC in change. Alice’s change payment is created _by Alice’s wallet_ in the very same transaction as the payment to Bob. Essentially, Alice’s wallet breaks her funds into two payments: one to Bob, and one back to herself. She can then use the change output in a subsequent transaction, thus spending it later.

Finally, for the transaction to be processed by the network in a timely fashion, Alice’s wallet application will add a small fee. This is not explicit in the transaction; it is implied by the difference between inputs and outputs. If instead of taking 0.085 in change, Alice creates only 0.0845 as the second output, there will be 0.0005 BTC (half a millibitcoin) left over. The input’s 0.10 BTC is not fully spent with the two outputs, because they will add up to less than 0.10. The resulting difference is the _transaction fee_ that is collected by the miner as a fee for including the transaction in a block and putting it on the blockchain ledger.

The resulting transaction can be seen using a blockchain explorer web application, as shown in [Alice’s transaction to Bob’s Cafe](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-alice).

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0208.png)
Figure 8. Alice’s transaction to Bob’s Cafe
Tip
>View the [transaction from Alice to Bob’s Cafe](http://bit.ly/1u0FIGs).

###Adding the Transaction to the Ledger

The transaction created by Alice’s wallet application is 258 bytes long and contains everything necessary to confirm ownership of the funds and assign new owners. Now, the transaction must be transmitted to the bitcoin network where it will become part of the distributed ledger (the blockchain). In the next section we will see how a transaction becomes part of a new block and how the block is "mined." Finally, we will see how the new block, once added to the blockchain, is increasingly trusted by the network as more blocks are added.

####Transmitting the transaction

Because the transaction contains all the information necessary to process, it does not matter how or where it is transmitted to the bitcoin network. The bitcoin network is a peer-to-peer network, with each bitcoin client participating by connecting to several other bitcoin clients. The purpose of the bitcoin network is to propagate transactions and blocks to all participants.

####How it propagates

Alice’s wallet application can send the new transaction to any of the other bitcoin clients it is connected to over any Internet connection: wired, WiFi, or mobile. Her bitcoin wallet does not have to be connected to Bob’s bitcoin wallet directly and she does not have to use the Internet connection offered by the cafe, though both those options are possible, too. Any bitcoin network node (other client) that receives a valid transaction it has not seen before will immediately forward it to other nodes to which it is connected. Thus, the transaction rapidly propagates out across the peer-to-peer network, reaching a large percentage of the nodes within a few seconds.

####Bob’s view

If Bob’s bitcoin wallet application is directly connected to Alice’s wallet application, Bob’s wallet application might be the first node to receive the transaction. However, even if Alice’s wallet sends the transaction through other nodes, it will reach Bob’s wallet within a few seconds. Bob’s wallet will immediately identify Alice’s transaction as an incoming payment because it contains outputs redeemable by Bob’s keys. Bob’s wallet application can also independently verify that the transaction is well formed, uses previously unspent inputs, and contains sufficient transaction fees to be included in the next block. At this point Bob can assume, with little risk, that the transaction will shortly be included in a block and confirmed.

Tip
>A common misconception about bitcoin transactions is that they must be "confirmed" by waiting 10 minutes for a new block, or up to 60 minutes for a full six confirmations. Although confirmations ensure the transaction has been accepted by the whole network, such a delay is unnecessary for small-value items such as a cup of coffee. A merchant may accept a valid small-value transaction with no confirmations, with no more risk than a credit card payment made without an ID or a signature, as merchants routinely accept today.
