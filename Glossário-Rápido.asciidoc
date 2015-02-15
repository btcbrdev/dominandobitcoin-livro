# Glossário Rápido

Esse glossário rápido contém muitos dos termos usados em relação ao bitcoin. Esses termos são usados em todo o livro, então favorite isso para uma referência rápida

endereço (address)::
    Um endereço (address) bitcoin parece com +1DSrfJdB2AnWaFNgSbv3MZC2m74996JafV+. Consiste de uma string de letras e números começando com um "1" (número um). Assim como você pede aos outros para enviar um e-mail para o seu endereço de e-mail, você irá pedir aos outros para lhe enviar bitcoin para o seu endereço bitcoin.((("bitcoin address")))((("address", see="bitcoin address")))((("public key", see="bitcoin address")))

bip::
    Proposta de melhoria do Bitcoin (Bitcoin Improvement Proposals). Um conjunto de proposta que membros da comunidade de bitcoin submete para melhorar o bitcoin. Por exemplo, BIP0021 e uma proposta para melhorar o esquema do identificador de endereços na internet (URI) do bitcoin.((("bip")))

bitcoin::
    O nome da unidade monetária (A moeda), a rede e o software.((("bitcoin")))

block::
    Um agrupamento das transações, marcado com um timestamp, e uma impressão digital do bloco anterior. O cabeçalho do bloco é um hash para produzir uma prova de trabalho, assim validando as transações. Blocos válidos são adicionados ao blockchain principal por consenso da rede.((("block")))

blockchain::
  Uma lista de blocos validados, cada um ligando ao seu antecessor até o bloco gênese.((("blockchain")))

confirmações (confirmations)::
  Uma vez que uma transação é incluída em um bloco, ela tem uma confirmação. Assim que _outro_ bloco é minerado no mesmo blockchain, a operação tem duas confirmações, e assim por diante. Seis ou mais confirmações é considerado prova suficiente de que a transação não pode ser revertida.((("confirmations")))

difficulty::
	A network-wide setting that controls how much computation is required to produce a proof of work.((("difficulty")))

difficulty target::
 	A difficulty at which all the computation in the network will find blocks approximately every 10 minutes.((("target difficulty")))

difficulty retargeting::
	A network-wide recalculation of the difficulty that occurs once every 2,106 blocks and considers the hashing power of the previous 2,106 blocks.((("difficulty retargeting")))

fees::
	The sender of a transaction often includes a fee to the network for processing the requested transaction.  Most transactions require a minimum fee of 0.5 mBTC.((("fees")))

hash::
	A digital fingerprint of some binary input.((("hash")))

genesis block::
	The first block in the blockchain, used to initialize the cryptocurrency.((("genesis block")))

miner::
A network node that finds valid proof of work for new blocks, by repeated hashing.((("miner")))

network::
A peer-to-peer network that propagates transactions and blocks to every bitcoin node on the network.((("network")))

Proof-Of-Work::
	A piece of data that requires significant computation to find. In bitcoin, miners must find a numeric solution to the SHA256 algorithm that meets a network-wide target, the difficulty target. ((("proof-of-work")))

reward::
An amount included in each new block as a reward by the network to the miner who found the Proof-Of-Work solution. It is currently 25BTC per block.((("reward")))

secret key (aka private key)::
	The secret number that unlocks bitcoins sent to the corresponding address.  A secret key looks like +5J76sF8L5jTtzE96r66Sf8cka9y44wdpJjMwCxR3tzLh3ibVPxh+.((("secret key")))((("private key", see="secret key")))

transaction::
In simple terms, a transfer of bitcoins from one address to another. More precisely, a transaction is a signed data structure expressing a transfer of value. Transactions are transmitted over the bitcoin network, collected by miners, and included into blocks, made permanent on the blockchain.((("transaction")))

wallet::
Software that holds all your bitcoin addresses and secret keys. Use it to send, receive, and store your bitcoin.((("wallet")))
