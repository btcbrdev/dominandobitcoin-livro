#O que é Bitcoin?
Bitcoin é uma coleção de conceitos e tecnologias que formam a base de um ecossistema de dinheiro digital. Unidades de moeda chamadas bitcoins são usadas para armazenar e transmitir valor entre os participantes na rede Bitcoin. Usuários Bitcoin se comunicam entre si usando o protocolo bitcoin principalmente através da Internet, apesar de que outras redes de transporte também possam ser usadas. A pilha de protocolo bitcoin, disponível como software de código aberto, pode ser executada em uma ampla variedade de dispositivos com capacidade de computação, incluindo laptops e smartphones, tornando a tecnologia facilmente acessível.

Os usuários podem transferir bitcoins através da rede para fazer praticamente qualquer coisa que pode ser feita com moedas convencionais, incluindo a compra de venda de bens, o envio de dinheiro a pessoas ou organizações, ou a extensão de crédito. Os bitcoins podem ser comprados, vendidos ou trocados por outras moedas em casas de câmbio especializadas. Bitcoin é, em um sentido, uma forma perfeita de dinheiro para a Internet pois é rápido, seguro e sem fronteiras.

Ao contrário das moedas tradicionais, os bitcoins são inteiramente virtuais. Não há moedas físicas ou mesmo moedas digitais por si só. As moedas de bitcoin se subentendem em transações que transferem valor de um remetente a um destinatário. Os usuários de bitcoin possuem chaves que lhes permitem provar a posse de transações na rede bitcoin, desbloqueando o valor a ser gasto e enviado para um novo destinatário. Essas chaves com freqüência se armazenam em uma carteira digital no computador de cada usuário. A posse da chave que desbloqueia uma transação é o único pré-requisito para gastar os bitcoins, o que coloca o controle inteiramente nas mãos de cada usuário.

Bitcoin é um sistema distribuído, peer-to-peer. Como tal, não existe um servidor "central" ou ponto de controle. Os bitcoins se criam através de um processo chamado de "mineração", que consiste em competir para encontrar soluções para um problema matemático enquanto se processam transações de bitcoins. Qualquer participante na rede bitcoin (ou seja, qualquer um usando um dispositivo que execute a pilha completa de protocolo Bitcoin) pode operar como um mineiro, usando o poder de processamento do computador dele para verificar e registrar transações. A cada 10 minutos em média, alguém é capaz de validar as transações dos últimos 10 minutos e é recompensado com bitcoins novinhos em folha. Essencialmente, a mineração de bitcoin descentraliza as funções de emissão de moeda e de compensação típicas de um banco central e substitui a necessidade de qualquer banco central nesta competição global [que é a mineração].

O protocolo bitcoin contêm algoritmos embutidos que regulam a função de mineração através da rede. A dificuldade da tarefa de processamento que os mineiros devem realizar - para registrar com sucesso um bloco de transações para a rede bitcoin - se ajusta dinamicamente de tal forma que alguém é bem-sucedido a cada 10 minutos, na média, independentemente de quantos mineiros (e CPUs) estejam trabalhando na tarefa a qualquer momento. O protocolo também reduz à metade, a cada 4 anos, a taxa com que novos bitcoins são criados e limita o número total de bitcoins que serão criados a um total fixo de 21 milhões de moedas. O resultado é que o número de bitcoins em circulação acompanham de perto uma curva previsível que alcança 21 milhões no ano de 2140. Devido à taxa decrescente de emissão, no longo prazo a moeda bitcoin é deflacionária. Ademais, bitcoin não pode ser inflacionada "imprimindo" novo dinheiro mais rápido que a taxa de emissão esperada.

Nos bastidores, bitcoin é também o nome do protocolo, de uma rede e de uma inovação informática distribuída. A moeda bitcoin é na verdade tão somente a primeira aplicação desta invenção. Como um programador, eu vejo bitcoin parecido com a Internet do dinheiro, uma rede para propagar valor e proteger a posse de ativos digitais através da computação distribuída. Há muito mais em bitcoin do que se enxerga à primeira vista.

Neste capítulo começaremos explicando alguns dos principais conceitos e termos, obtendo o software necessário e usando bitcoin para transações simples. Nos próximos capítulos iremos desembrulhar as capas da tecnologia que tornam bitcoin possível e examinar o funcionamento interno da rede e do protocolo bitcoin.

##Moedas Digitais Antes do Bitcoin

A aparição de um dinheiro digital viável está ligada de perto a desenvolvimentos em criptografia. Não é uma surpresa quando alguém leva em conta que os desafios fundamentais envolvidos no uso de bits para representar valor que pode ser trocado por bens e serviços. Duas perguntas básicas para qualquer um aceite dinheiro digital são:

1. Posso confiar que o dinheiro é autêntico e não falsificado?
2. Posso estar seguro de que ninguém vai reclamar que esse dinheiro lhe pertence e não a mim? (também conhecido como o problema do "gasto duplicado")

Os emissores do dinheiro em papel estão o tempo todo batalhando o problema da falsificação com o uso de papéis e tecnologias de impressão cada vez mais sofisticados. O dinheiro físico resolve facilmente o problema do gasto duplicado pois a mesma nota em papel não pode estar em 2 lugares ao mesmo tempo. Mas é claro, o dinheiro convencional com frequência se armazena e se transmite de forma digital. Nestes casos, os problemas de falsicação e de gastos duplicados são tratados pela compensação de todas as transações eletrônicas através de autoridades centrais que detêm uma visão global da moeda em circulação. No caso do dinheiro digital, que não pode se beneficiar de tintas esotéricas ou marcas holográficas, a criptografia proporciona a base da confiança na legitimidade da exigência de um usuario pelo seu valor. Especificamente, as assinaturas digitais criptográficas permitem a um usuário assinar um ativo digital ou transação provando a posse do ativo. Com a arquitetura apropriada, as assinaturas digitais também podem ser usadas para resolver o problema do gasto duplicado. 

Quando a criptografia começou a se tornar mais comum e entendida no final dos anos 80, muitos pesquisadores começaram a tentar usá-la para construir moedas digitais. Estes projetos pioneiros emitiam dinheiro digital, normalmente embasado por uma moeda nacional ou um metal precioso como o ouro.

Apesar destas moedas digitais pioneiras funcionarem, elas eram centralizadas e, como resultado, eram fáceis de atacar tanto por governos como por _hackers_. As moedas digitais pioneiras usavam uma central de compensação para finalizar todas as transações em intervalos regulares, da mesma forma que um sistema bancário tradicional. Infelizmente, em muitos casos essas moedas digitais que surgiam se tornavam um alvo dos governos preocupados e eventualmente desapareciam. Algumas falharam em quebras espetaculares quando a companhia responsável era liquidada de repente. Para ser robusta contra a intervenção de opositores, sejam governos legítimos ou elementos criminais, uma moeda descentralizada digital se tornava necessária para evitar um único ponto de ataque. Este sistema é Bitcoin, completamente descentralizado por _design_, e livre de qualquer autoridade central ou ponto de controle que pode ser atacado ou corrompido.

Bitcoin representa o auge de décadas de pesquisa em criptografia e sistemas distribuídos e inclui 4 inovações chaves unidas em uma combinação única e poderosa. Bitcoin consiste em:

* Uma rede _peer-to-peer_ descentralizada (o protocolo bitcoin)
* Um registro público de transações (a blockchain ou cadeia de blocos)
* Uma emissão de moeda descentralizada, matemática e determinística (a mineração distribuída)
* Um sistema descentralizado de verificação de transações (o script de transação)

#A História do Bitcoin

O Bitcoin foi inventado em 2008 com a publicação de um paper entitulado com a publicação de um paper entitulado "Bitcoin: Um Sistema de Dinheiro em Espécie Eletrônico" (_"Bitcoin: A Peer-to-Peer Electronic Cash System"_ em inglês), escrito sob o pseudônimo de Satoshi Nakamoto. Nakamoto combinou várias das invenções anteriores tais como b-money e HashCash para criar um sistema de dinheiro vivo eletrônico completamente descentralizado que não depende de uma autoridade central para a emissão de moeda ou para a liquidação e validação de transações. A inovação chave foi usar um sistema de computação distribuído (chamado algoritmo de "prova de trabalho" ou _"proof of work"_) para conduzir uma "eleição" global a cada 10 minutos, permitindo à rede descentralizada chegar em um consenso sobre o estado das transações. Isto resolve de forma elegante o problema de gasto duplicado onde uma única unidade de moeda poderia ser gasta duas vezes. Antes o problema de gasto duplicado era uma fraqueza do dinheiro digital e se solucionava liquidando todas as transações através de uma entidade central.

A rede bitcoin começou em 2009, baseado em uma implementação de referência publicada por Nakamoto e desde então revisada por muitos outros programadores. A computação distribuída que proporciona segurança e robustez ao bitcoin cresceu exponencialmente, e agora excede a capacidade combinada de processamento dos principais supercomputadores do mundo. O valor de mercado do bitcoin se estima entre 5 e 10 bilhões de dólares americanos, dependendo da taxa de câmbio entre o bitcoin e o dólar. A maior transação processada até o momento pela rede foi de US$ 150 milhões, transmitidos instantaneamente e processados sem nenhuma taxa.

Satoshi Nakamoto se afastou do público em abril de 2011, deixando a responsabilidade pelo desenvolvimento do código e da rede nas mão de um animado grupo de voluntários. A identidade da pessoa ou pessoas por trás do bitcoin ainda é desconhecida. No entanto, nem Satoshi Nakamoto nem qualquer outra pessoa exerce controle sobre o sistema bitcoin, que opera baseado em princípios matemáticos totalmente transparentes. O próprio invento é revolucionário e já gerou nova ciência nos campos da computação distribuída, economia e econometria.

###Uma Solução para um Problema de Computação Distribuída
O invento de Satoshi Nakamoto é também uma solução prática para um problema que até então não estava resolvido em computação distribuída, conhecido como o "Problema dos Generais Bizantinos". Em resumo, o problema consiste em tentar tomar uma decisão através do intercâmbio de informações sobre uma rede pouco confiável e potencialmente comprometido. A solução de Satoshi Nakamoto, que utiliza o conceito de prova de trabalho para alcançar o consenso sem uma autoridade central confiável, representa um enorme avanço na ciência de computação distribuída e possui amplas aplicações além de moedas. Pode ser usado para alcançar consenso em redes descentralizadas para provar a honestidade de eleições, loterias, registros de bens, cartórios digitais e mais.

#Usos do Bitcoin, Seus Usuários e Suas Histórias

Bitcoin é uma tecnologia, mas ela expressa dinheiro que é fundamentalmente uma linguagem para a troca de valor entre pessoas. Vamos dar uma olhada nas pessoas que estão usando bitcoin e alguns dos usos mais comuns da moeda e do protocolo através de suas histórias. Iremos reutilizar essas histórias ao largo do livro para ilustrar os usos do dinheiro digital na vida real e como eles se tornaram possíveis por meio das várias tecnologias que formam parte do bitcoin.

_**Comércio de ítems de baixo valor na América do Norte**_

Alícia mora na área da baía da Califórnia do Norte. Ela ouviu falar sobre o bitcoin através dos seus amigos tecnólogos e quer começar a usá-lo. Iremos acompanhar sua história de como ela aprende a respeito do bitcoin, adquire alguns e então gasta alguns dos bitcoins dela para comprar uma xícara de café no Bob's Cafe em Palo Alto. Esta história nos vai apresentar ao _software_, às casas de câmbio e às transações básicas desde a perspectiva de um consumidor do varejo.

_**Comércio de ítems de alto valor nos Estados Unidos**_

Carol é dona de uma galeria de arte em San Francisco. Ela vende pinturas caras por bitcoin. Esta história nos vai apresentar os riscos de um ataque de consenso "51%" contra varejistas de items de alto valor.

_**Serviços de contratos internacionais**_

Bob, o dono da cafeteria de Palo Alto, está montando um novo website. Ele contratou um programador web indiano, Gopesh, que mora em Bangalore, Índia. Gopesh aceitou ser pago em bitcoin. Esta história vai examinar o uso do bitcoin para a terceirização, contratos de serviços e transferências bancárias internacionais. 

_**Doações beneficentes**_

Eugênia é a diretora de uma instituição de caridade para crianças nas Filipinas. Recentemente ela discobriu o bitcoin e quer usá-lo para alcançar um grupo completamente diferente de estrangeiros e doadores domésticos para financiar sua instituição de caridade. Ela também tem investigado formas de usa o bitcoin para distribuir os fundos rapidamente nas áreas necessitadas. Esta história irá mostrar o uso do bitcoin para a angariação de fundos através de fronteiras e moedas e o uso de um registro contábil aberto para a transparência de organizações de caridade.

_**Importação e exportação**_

Mohammed é um importador de eletrônicos em Dubai. Ele vem tentando usar o bitcoin para comprar eletrônicos dos Estados Unidos e da China para importação aos Emirados Árabes Unidos e assim acelerar o processo de pagamentos para as importações. Esta história irá mostrar como o bitcoin pode ser usado para grandes pagamentos internacionais _B2B_ entre negócios de grande porte atados a mercadorias físicas.

_**Minerando por bitcoins**_

Jing é um estudante de engenharia de computação em Shanghai. Ele possui uma aparelhagem de "mineração" para minerar bitcoins, usando suas habilidades de engenharia para complementar sua renda. Esta história irá examinar a base "industrial" do bitcoin: o equipamento especializado usado para proteger a rede bitcoin e emitir nova moeda.

Cada uma dessas histórias se baseia em pessoas reais e indústrias reais que atualmente usam bitcoin para criar novos mercados, novas indústrias e soluções inovadoras para os problemas econômicos globais.



=== Getting Started

((("bitcoin","forms of")))To join the bitcoin network and start using the currency, all a user has to do is download an application or use a web application. Because bitcoin is a standard, there are many implementations of the bitcoin client software. There is also a reference implementation, also known as the Satoshi client, which is managed as an open source project by a team of developers and is derived from the original implementation written by Satoshi Nakamoto. 

The three main forms of bitcoin clients are:

Full client:: ((("full nodes")))A full client, or "full node," is a client that stores the entire history of bitcoin transactions (every transaction by every user, ever), manages the users' wallets, and can initiate transactions directly on the bitcoin network. This is similar to a standalone email server, in that it handles all aspects of the protocol without relying on any other servers or third-party services.

Lightweight client:: ((("lightweight client")))A lightweight client stores the user's wallet but relies on third-party–owned servers for access to the bitcoin transactions and network. The light client does not store a full copy of all transactions and therefore must trust the third-party servers for transaction validation. This is similar to a standalone email client that connects to a mail server for access to a mailbox, in that it relies on a third party for interactions with the network. 

Web client:: ((("web clients")))Web clients are accessed through a web browser and store the user's wallet on a server owned by a third party. This is similar to webmail in that it relies entirely on a third-party server. 

.Mobile Bitcoin
****
((("mobile clients")))((("smartphones, bitcoin clients for")))Mobile clients for smartphones, such as those based on the Android system, can either operate as full clients, lightweight clients, or web clients. Some mobile clients are synchronized with a web or desktop client, providing a multiplatform wallet across multiple devices but with a common source of funds.
****

The choice of bitcoin client depends on how much control the user wants over funds. A full client will offer the highest level of control and independence for the user, but in turn puts the burden of backups and security on the user. On the other end of the range of choices, a web client is the easiest to set up and use, but the trade-off with a web client is that counterparty risk is introduced because security and control is shared with the user and the owner of the web service. If a web-wallet service is compromised, as many have been, the users can lose all their funds. Conversely, if users have a full client without adequate backups, they might lose their funds through a computer mishap. 

For the purposes of this book, we will be demonstrating the use of a variety of downloadable bitcoin clients, from the reference implementation (the Satoshi client) to web wallets. Some of the examples will require the use of the reference client, which, in addition to being a full client, also exposes APIs to the wallet, network, and transaction services. If you are planning to explore the programmatic interfaces into the bitcoin system, you will need the reference client.

==== Quick Start

((("bitcoin","wallet setup")))((("wallets","setting up")))Alice, who we introduced in <<user-stories>>, is not a technical user and only recently heard about bitcoin from a friend. She starts her journey by visiting the((("bitcoin.org"))) official website http://www.bitcoin.org[bitcoin.org], where she finds a broad selection of bitcoin clients. Following the advice on the bitcoin.org site, she chooses the lightweight bitcoin client((("Multibit client"))) Multibit. 

Alice follows a link from the bitcoin.org site to download and install Multibit on her desktop. Multibit is available for Windows, Mac OS, and Linux desktops.

[WARNING]
====
((("wallets","security of")))A bitcoin wallet must be protected by a password or passphrase. There are many bad actors attempting to break weak passwords, so take care to select one that cannot be easily broken. Use a combination of upper and lowercase characters, numbers, and symbols. Avoid personal information such as birth dates or names of sports teams. Avoid any words commonly found in dictionaries, in any language. If you can, use a password generator to create a completely random password that is at least 12 characters in length. Remember: bitcoin is money and can be instantly moved anywhere in the world. If it is not well protected, it can be easily stolen.
====

Once Alice has downloaded and installed the Multibit application, she runs it and is greeted by a Welcome screen, as shown in <<multibit-welcome>>.

[[multibit-welcome]]
.The Multibit bitcoin client Welcome screen
image::images/msbt_0101.png["MultibitWelcome"]

((("addresses, bitcoin","created by Multibit")))Multibit automatically creates a wallet and a new bitcoin address for Alice, which Alice can see by clicking the Request tab shown in <<multibit-request>>.
[[multibit-request]]
.Alice's new bitcoin address, in the Request tab of the Multibit client
image::images/msbt_0102.png["MultibitReceive"]

The most important part of this screen is Alice's _bitcoin address_. Like an email address, Alice can share this address and anyone can use it to send money directly to her new wallet. On the screen it appears as a long string of letters and numbers: +1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK+. Next to the wallet's bitcoin address is a QR code, a form of barcode that contains the same information in a format that can be scanned by a smartphone camera. The QR code is the black-and-white square on the right side of the window. Alice can copy the bitcoin address or the QR code onto her clipboard by clicking the copy button adjacent to each of them. Clicking the QR code itself will magnify it, so that it can be easily scanned by a smartphone camera. 

Alice can also print the QR code as a way to easily give her address to others without them having to type the long string of letters and numbers. 

[TIP]
====
((("addresses, bitcoin","sharing")))Bitcoin addresses start with the digit 1 or 3. Like email addresses, they can be shared with other bitcoin users who can use them to send bitcoin directly to your wallet. Unlike email addresses, you can create new addresses as often as you like, all of which will direct funds to your wallet. A wallet is simply a collection of addresses and the keys that unlock the funds within. You can increase your privacy by using a different address for every transaction. There is practically no limit to the number of addresses a user can create.
====

Alice is now ready to start using her new bitcoin wallet. 

[[getting_first_bitcoin]]
==== Getting Your First Bitcoins

((("bitcoin","acquiring")))((("currency markets")))It is not possible to buy bitcoins at a bank or foreign exchange kiosks at this time. As of 2014, it is still quite difficult to acquire bitcoins in most countries. There are a number of specialized currency exchanges where you can buy and sell bitcoin in exchange for a local currency. These operate as web-based currency markets and include:

http://bitstamp.net[Bitstamp]:: A European currency market that supports several currencies including euros (EUR) and US dollars (USD) via wire transfer.((("Bitstamp currency market")))
http://www.coinbase.com[Coinbase]:: A US-based bitcoin wallet and platform where merchants and consumers can transact in bitcoin. Coinbase makes it easy to buy and sell bitcoin, allowing users to connect to US checking accounts via the ACH system.((("Coinbase.com")))

Cryptocurrency exchanges such as these operate at the intersection of national currencies and cryptocurrencies. As such, they are subject to national and international regulations, and are often specific to a single country or economic area and specialize in the national currencies of that area. Your choice of currency exchange will be specific to the national currency you use and limited to the exchanges that operate within the legal jurisdiction of your country.  Similar to opening a bank account, it takes several days or weeks to set up the necessary accounts with these services because they require various forms of identification to comply with((("AML (Anti-Money Laundering) banking regulations")))((("banking regulations and bitcoin")))((("KYC (Know Your Customer) banking regulations"))) KYC (know your customer) and AML (anti-money laundering) banking regulations. Once you have an account on a bitcoin exchange, you can then buy or sell bitcoins quickly just as you could with foreign currency with a brokerage account.

You can find a more complete list at http://bitcoincharts.com/markets[bitcoin charts], a site that offers price quotes and other market data across many dozens of currency exchanges. 

There are four other methods for getting bitcoins as a new user:

* Find((("bitcoins, buying for cash"))) a friend who has bitcoins and buy some from him directly. Many bitcoin users start this way. 
* Use a classified service such as localbitcoins.com to find a seller in your area to buy bitcoins for cash in an in-person transaction. 
* Sell a product or service for bitcoin. If you're a programmer, sell your programming skills. 
* Use((("ATMs, bitcoin")))((("bitcoin ATMs"))) a bitcoin ATM in your city.  Find a bitcoin ATM close to you using an online map from http://www.coindesk.com/bitcoin-atm-map/[CoinDesk].

Alice was introduced to bitcoin by a friend and so she has an easy way of getting her first bitcoins while she waits for her account on a California currency market to be verified and activated. 

[[sending_receiving]]
==== Sending and Receiving Bitcoins

((("bitcoin","sending/receiving", id="ix_ch01-asciidoc1", range="startofrange")))Alice has created her bitcoin wallet and she is now ready to receive funds. Her wallet application randomly generated a private key (described in more detail in <<private_keys>>) together with its corresponding bitcoin address. At this point, her bitcoin address is not known to the bitcoin network or "registered" with any part of the bitcoin system. Her bitcoin address is simply a number that corresponds to a key that she can use to control access to the funds. There is no account or association between that address and an account. Until the moment this address is referenced as the recipient of value in a transaction posted on the bitcoin ledger (the blockchain), it is simply part of the vast number of possible addresses that are "valid" in bitcoin. Once it has been associated with a transaction, it becomes part of the known addresses in the network and Alice can check its balance on the public ledger. 

Alice meets her friend Joe, who introduced her to bitcoin, at a local restaurant so they can exchange some US dollars and put some bitcoins into her account. She has brought a printout of her address and the QR code as displayed in her bitcoin wallet. There is nothing sensitive, from a security perspective, about the bitcoin address. It can be posted anywhere without risking the security of her account. 

Alice wants to convert just 10 US dollars into bitcoin, so as not to risk too much money on this new technology. She gives Joe a $10 bill and the printout of her address so that Joe can send her the equivalent amount of bitcoin. 

((("exchange rate, finding")))Next, Joe has to figure out the exchange rate so that he can give the correct amount of bitcoin to Alice. There are hundreds of applications and websites that can provide the current market rate. Here are some of the most popular:
	
http://bitcoincharts.com[Bitcoin Charts]:: ((("bitcoincharts.com")))A market data listing service that shows the market rate of bitcoin across many exchanges around the globe, denominated in different local currencies
http://bitcoinaverage.com/[Bitcoin Average]:: ((("bitcoinaverage.com")))A site that provides a simple view of the volume-weighted-average for each currency 
http://www.zeroblock.com/[ZeroBlock]:: ((("ZeroBlock")))A free Android and iOS application that can display a bitcoin price from different exchanges (see <<zeroblock-android>>)
http://www.bitcoinwisdom.com/[Bitcoin Wisdom]:: ((("bitcoinwisdom.com")))Another market data listing service
	
[[zeroblock-android]]
.ZeroBlock, a bitcoin market-rate application for Android and iOS
image::images/msbt_0103.png["zeroblock screenshot"]
	
Using one of the applications or websites just listed, Joe determines the price of bitcoin to be approximately 100 US dollars per bitcoin. At that rate he should give Alice 0.10 bitcoin, also known as 100 millibits, in return for the 10 US dollars she gave him. 

Once Joe has established a fair exchange price, he opens his mobile wallet application and selects to "send" bitcoin. For example, if using the Blockchain mobile wallet on an Android phone, he would see a screen requesting two inputs, as shown in <<blockchain-mobile-send>>.

* The destination bitcoin address for the transaction
* The amount of bitcoin to send


In the input field for the bitcoin address, there is a small icon that looks like a QR code. This allows Joe to scan the barcode with his smartphone camera so that he doesn't have to type in Alice's bitcoin address (+1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK+), which is quite long and difficult to type. Joe taps the QR code icon and activates the smartphone camera, scanning the QR code from Alice's printed wallet that she brought with her. The mobile wallet application fills in the bitcoin address and Joe can check that it scanned correctly by comparing a few digits from the address with the address printed by Alice. 

[[blockchain-mobile-send]]
.Blockchain mobile wallet's bitcoin send screen
image::images/msbt_0104.png["blockchain mobile send screen"]

Joe then enters the bitcoin value for the transaction, 0.10 bitcoin. He carefully checks to make sure he has entered the correct amount, because he is about to transmit money and any mistake could be costly. Finally, he presses Send to transmit the transaction. Joe's mobile bitcoin wallet constructs a transaction that assigns 0.10 bitcoin to the address provided by Alice, sourcing the funds from Joe's wallet and signing the transaction with Joe's private keys. This tells the bitcoin network that Joe has authorized a transfer of value from one of his addresses to Alice's new address. As the transaction is transmitted via the peer-to-peer protocol, it quickly propagates across the bitcoin network. In less than a second, most of the well-connected nodes in the network receive the transaction and see Alice's address for the first time. 

If Alice has a smartphone or laptop with her, she will also be able to see the transaction. The bitcoin ledger—a constantly growing file that records every bitcoin transaction that has ever occurred—is public, meaning that all she has to do is look up her own address and see if any funds have been sent to it. She can do this quite easily at the((("blockchain.info website"))) blockchain.info website by entering her address in the search box. The website will show her a http://bit.ly/1u0FFKL[page] listing all the transactions to and from that address. If Alice is watching that page, it will update to show a new transaction transferring 0.10 bitcoin to her balance soon after Joe hits Send. 

++++
<?hard-pagebreak?>
++++

.Confirmations
****
((("confirmation of transactions")))At first, Alice's address will show the transaction from Joe as "Unconfirmed." This means that the transaction has been propagated to the network but has not yet been included in the bitcoin transaction ledger, known as the blockchain. To be included, the transaction must be "picked up" by a miner and included in a block of transactions. Once a new block is created, in approximately 10 minutes, the transactions within the block will be accepted as "confirmed" by the network and can be spent. The transaction is seen by all instantly, but it is only "trusted" by all when it is included in a newly mined block.
****

Alice is now the proud owner of 0.10 bitcoin that she can spend. In the next chapter we will look at her first purchase with bitcoin, and examine the underlying transaction and propagation technologies in more detail.(((range="endofrange", startref="ix_ch01-asciidoc1")))(((range="endofrange", startref="ix_ch01-asciidoc0")))

