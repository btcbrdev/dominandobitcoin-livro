[Link ao capítulo original](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc)

##Assim Funciona o Bitcoin

###Transações, Blocos, Mineração e a Corrente de Blocos (blockchain)

O sistema bitcoin, à diferença dos sistemas financeiro e de pagamentos tradicionais, baseia-se na confiança descentralizada. Ao invés de depender de uma autoridade confiável central, com o bitcoin a confiança surge das interações entre os diferentes participantes no sistema bitcoin. Neste capítulo, iremos examinar o bitcoin a fundo, rastreando uma transação através do sistema bitcoin e observando como ela se torna "confiável", como é aceita pelo mecanismo de consenso distribuído e, finalmente, como é gravada na corrente de blocos (blockchain), o livro contábil que contém todas as transações já realizadas.

Cada exemplo baseia-se em uma transação real feita na rede bitcoin, simulando interações entre usuários (Joe, Alice e Bob)  enviando fundos de uma carteira a outra. Enquanto rastrearmos uma transação através da rede bitcoin e da corrente de blocos (blockchain), iremos usar um site explorador da corrente de blocos para visualizar cada passo. Um explorador da corrente de blocos é um site que funciona como um mecanismo de busca para o bitcoin, no sentido de que lhe permite procurar por endereços, transações e blocos e ver as relações e fluxos entre eles.

Leitores populares da corrente de blocos (blockchain) incluem:
* [Blockchain info](http://blockchain.info/)  
* Bitcoin Block Explorer  (http://blockexplorer.com/)  
* insight(http://insight.bitpay.com/)  
* blockr Block Reader(http://blockr.io/)  

Cada um destes possui uma função de busca na qual pode ser pesquisado um endereço, um hash de transação ou um número de bloco, sendo mostrado como resultado os dados equivalentes na rede bitcoin e blockchain. Em cada exemplo, nós iremos fornecer uma URL que leva você diretamente à "entry" relevante, para que você possa estudá-la em maiores detalhes.


####Visão Geral do Bitcoin

No diagrama de visão geral mostrado em [Bitcoin overview](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#bitcoin-overview), podemos observar que o sistema de bitcoin consiste de usuários com carteiras que contém chaves, transações que são propagadas através da rede e mineradores que produzem (através de computação competitiva) o consenso da blockchain, que é um "authoritative ledger" de todas as transações. Neste capítulo, nós iremos rastrear uma transação à medida que ela é transmitida pela rede e examinaremos as interações entre cada parte do sistema bitcoin. Os capítulos subsequentes irão se aprofundar na tecnologia contida nas carteiras, mineração e sistemas de comerciantes.

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0201.png)

Figura 1. Visão geral do Bitcoin

####Comprando uma Xícara de Café

A Alice, que foi apresentada no último capítulo, é uma nova usuária que acabou de adquirir seu primeiro bitcoin. Em [getting_first_bitcoin](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#getting_first_bitcoin), ela encontrou seu amigo Joe para trocar um pouco de dinheiro em papel por bitcoins. A transação que Joe criou adicionou 0,10 BTC na carteira da Alice. Agora a Alice irá fazer sua primeira compra com bitcoins, comprando uma xícara de café na cafeteria do Bob em Palo Alto, na Califórnia. A cafeteria do Bob, a Bob's Cafe, passou recentemente a aceitar pagamentos em bitcoins, ao adicionar uma opção de bitcoins em seu sistema de ponto de venda (PDV). Os preços da cafeteria estão listados na moeda local (dólares americanos), mas, no caixa, os clientes tem a opção de pagarem tanto em dólares quanto em bitcoins. A Alice faz seu pedido de uma xícara de café e o Bob insere a transação no caixa. O sistema de ponto de venda (PDV) irá converter o preço em dólares para bitcoins usando a cotação atual do mercado e irá mostrar os preços em ambas as moedas, além de exibir o código QR contendo uma solicitação de pagamento para a transação (ver [Código QR de solitação de pagamento (Dica: Tente escanear esse código!))](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#payment-request-QR):

> Total:  
> $1,50 USD  
> 0,015 BTC  

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0202.png)

Figura 2. Código QR de solitação de pagamento (Dica: Tente escanear esse código!)

O código QR de solicitação de pagamento codifica a seguinte URL, definida em  BIP0021:
> bitcoin:1GdK9UzpHBzqzX2A9JFP3Di4weBwqgmoQA?  
> amount=0.015&  
> label=Bob%27s%20Cafe&  
> message=Compra%20no%20Bob%27s%20Cafe  
>  
> Componentes da URL  
>  
> Um endereço bitcoin (bitcoin): "1GdK9UzpHBzqzX2A9JFP3Di4weBwqgmoQA"  
> Valor do pagamento (amount): "0.015"  
> Um rótulo para o endereço do destinatário (label): "Bob's Cafe"  
> Uma descrição para o pagamento (message): "Compra no Bob's Cafe"

[Dica]
> Ao contrário de um código QR que simplesmente contém um endereço de bitcoin como destinatário, um QR code com uma requisição de pagamento contém uma URL codificada a qual contém múltiplos parâmetros: um endereço de pagamento, um valor de pagamento e uma descrição genérica como "Bob's Cafe". Isso permite que um aplicativo de carteira bitcoin preencha as informações ussdas para enviar o pagamento enquanto mostra uma descrição intuitiva para o usuário. Você pode escanear o código QR acima com um aplicativo de carteira bitcoin para ver o que a Alice veria.

Bob diz: "A conta deu 1,50 dólares, ou 15 milibits."

A Alice então usa seu smartphone para escanear o código de barras mostrado na tela do Bob. Seu smartphone mostra um pagamento de  *0,0150 BTC* para o *Bob’s Cafe* e ela clica em *Enviar* para autorizar o pagamento. Dentro de alguns segundos (aproximadamente o mesmo tempo que leva uma autorização de cartão de crédito), o Bob visualiza a transação em seu caixa, completando a transação.

Nas próximas seções, examinaremos essa transação em maiores detalhes, veremos como a carteira da Alice a construiu, como ela foi propagada através da rede, como ela foi verificada e, finalmente, como o Bob pode gastar a quantia recebida em novas transações futuras.

Nota
>A rede bitcoin pode fazer transações em valores fracionários, por exemplo, desde mili-bitcoins (1/1.000 de um bitcoin) até um satoshi (1/100.000.000 de um bitcoin). Ao longo deste livro nós iremos usar o termo bitcoin para se referir a qualquer quantidade na moeda bitcoin, desde a menor unidade possível (1 satoshi) até o número máximo (21.000.000) de bitcoins que podem ser minerados.

###Transações Bitcoin

Em termos simples, uma transação informa para a rede que o dono de uma quantidade de bitcoins autorizou a transferência de alguns destes bitcoins para outro dono. O novo dono agora pode gastar esses bitcoins ao criar uma nova transação que autoriza a transferência para um outro dono, e assim por diante, em uma cadeia de posse de bitcoins.

As transações são como linhas em um "bookkeeping ledger" de dupla entrada. Em termos simples, cada transação contém um ou mais "inputs" (entradas), que são débitos em uma conta bitcoin. No outro lado da transação, existem um ou mais "outputs" (saídas) que são créditos adicionados em uma conta bitcoin. Os inputs e outputs (entradas e saídas ou débitos e créditos) somados não necessariamente resultam na mesma quantia. Ao invés disso, os outputs são um pouco maiores do que os inputs, e essa diferença se dá devido à "taxa de transação", que é um pequeno pagamento coletado pelo minerador que inclui a transação no blockchain (ledger). Uma transação bitcoin é mostrada como uma entrada no bookkeeping ledger em [Transaction as double-entry bookkeeping](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-double-entry).

A transação também contém uma prova de posse para cada quantia de bitcoins (inputs) que é transferida, na forma de uma assinatura digital assinada pelo dono, que pode ser validade por qualquer pessoa, de maneira independentemente. Usando os termos de bitcoin, "gastar" é assinar uma transação que transfere um valor (de uma transação prévia) para um novo dono, o qual é identificado através de um endereço bitcoin.

Dica
>_Transações_ movimentam valores a partir de _inputs de transação_ para _outputs de transação_. 

Um input é o lugar de onde vem o valor da moeda, geralmente um output de transação prévio. Um output de transação designa um novo dono para o valor ao associá-lo com uma nova chave. A chave de destino é chamada de _encumbrance_. Ela exige uma assinatura para a retirada dos fundos em transações futuras. Outputs de uma transação podem ser usados como inputs em uma nova transação, dessa maneira criando uma cadeia de posses à medida que o valor é movido de um endereço para outro (ver [Uma cadeia de transações, onde o output de uma transação é o input da próxima transação](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#blockchain-mnemonic).

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0203.png)
Figura 3. Transação como double-entry bookkeeping

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0204.png)
Figura 4. Uma cadeia de transações, onde o output de uma transação é o input da próxima transação

O pagamento de Alice para o Bob's Cafe usa uma transação prévia como seu input. No capítulo anterior, Alice recebeu bitcoins de seu amigo em troca de dinheiro. Aquela transação continha um número de bitcoins "trancados" com a chave de Alice (necessitam que um desafio seja solucionado para libertá-los). Sua nova transação para o Bob's Cafe utiliza a transação prévia como um input e cria novos outputs para pagar pela xícara de café e receber o troco. As transações formam uma cadeia, onde os inputs da última transação correspondem aos outputs das transações anteriores. A chave da Alice fornece a assinatura que desbloqueia estes outputs de transações prévios, desta maneira provando à rede bitcoin que ela é dona dos fundos. Ela vincula seu pagamento pelo café ao endereço do Bob, desta maneira criando um desafio neste output, que para ser solucionado exige que Bob produza uma assinatura, liberando essa quantidade de bitcoins para serem gastas. Isso representa a transferência de valor entre Alice e Bob. Essa cadeia de transações, de Joe para Alice, e de Alice para Bob, é ilustrada em [Uma cadeia de transações, onde o output de uma transação é o input da próxima transação](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#blockchain-mnemonic).

####Formas Comuns de Transação

A forma mais comum de transação é um pagamento simples de um endereço para outro, que frequentemente inclui algum "troco" que é devolvido para o dono original. Esse tipo de transação possui um input e dois outputs, e é mostrada em  [Transação mais comum](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-common).

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0205.png)
Figura 5. A forma mais comum de transação

Outra forma comum de transação é uma que agrega múltiplos inputs em um único output (ver [Transaction aggregating funds](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-aggregating). 

Isso representa o equivalente no mundo real à uma troca de uma pilha de moedas e notas por uma nota de valor maior. As transações deste tipo são às vezes geradas pelos aplicativos de carteira para limpar vários valores pequenos que foram recebidos como troco pelos pagamentos efetuados.

![](https://github.com/aantonop/bitcoinbook/blob/develop/images/msbt_0206.png)
Figura 6. Transação agregando fundos

Finalmente, outra forma de transação frequentemente vista no ledger do bitcoin é uma transação que distribui um input para múltiplos outputs, que representam múltiplos destinatários (ver [Transaction distributing funds](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-distributing). Este tipo de transação é às vezes usadas por entidades comerciais para distribuir fundos, como, por exemplo, ao processar folhas de pagamento para múltiplos empregados.

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0207.png)
Figura 7. Transação distribuindo fundos

###Construindo uma Transação

O aplicativo de carteira contém toda a lógica para selecionar os inputs e outputs apropriados para construir uma transação com os dados especificados pela Alice. Ela só precisa fornecer os dados de um destinatário e de uma quantia: o seu aplicativo de carteira faz todo o resto, sem que ela sequer veja os detalhes. Outro aspecto importante, é que o aplicativo de carteira também pode construir transações mesmo estando completamente offline. Da mesma maneira que você pode preencher um cheque em casa para depois depositá-lo em um envelope no banco, uma conexão com a rede bitcoin não é necessária para que uma transação seja construída e assinada. A transação só precisa ser enviada para a rede quando a pessoa quiser efetuá-la.

####Recebendo os Inputs Certos

O aplicativo carteira de Alice terá primeiro que achar os inputs que podem pagar pela quantia que ela quer enviar para o Bob. A maioria dos aplicativos carteira mantém um pequeno banco de dados de "outputs de transações não gastos" que são trancados (protegidos por um desafio) com as próprias chaves da carteira. Logo, a carteira de Alice iria conter uma cópia do output de transação da transação do Joe, que foi criada na troca pelo dinheiro (ver [getting_first_bitcoin](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#getting_first_bitcoin). Um apilcativo carteira de bitcoin que roda como um cliente de índice completo na verdade contém uma cópia de cada output não gasto de todas as transações presentes na blockchain. Isso permite que a carteira construa inputs de transação, além de verificar rapidamente se as transações que chegam tem inputs corretos. No entanto, como um cliente de índice completo ocupa muito espaço de armazenamento em disco, a maioria das carteiras roda clientes "leves" que mantém somente o registro dos outputs não gastos do usuário.

Se o aplicativo carteira não mantém uma cópia dos outputs de transação não-gastos, ele pode fazer uma requisição à rede bitcoin para solicitar essa informação, usando APIs disponíveis de diferentes fornecedores, ou fazer uma requisição a um nodo de índice completo usando um API de bitcoin JSON RPC. [Veja que todos os outputs não-gastos para o endereço de bitcoin de Alice](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#example_2-1) mostram uma requisição API RESTful, construído como um comando HTTP GET para uma URL específica. Essa URL irá retornar todas os outputs de transação não-gastos para um endereço, fornecendo para qualquer aplicação a informação necessária para construir inputs de transação para que os bitcoins sejam gastos. Nós usamos um simples cliente HTTP de linha de comando cURL para solicitarmos a resposta.

Exemplo 1. Observe todos os outputs não gastos para o endereço de bitcoin da Alice


{

 $ curl https://blockchain.info/unspent?active=1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK

}

Exemplo 2. Resposta para o lookup


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

A resposta em [Respota ao lookup](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#example_2-2) mostra um output não-gasto (um que ainda não foi resgatado) sob a posse do endereço de Alice **1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK**. A resposta inclui uma referência à transação na qual esse valor não-gasto está contido (o pagamento do Joe) e seu valor em satoshis, 10 milhões, equivalente a 0,10 bitcoin. Com essa informação, o aplicativo carteira de Alice pode construir uma transação para transferir o valor para o endereço do novo dono.

Dica
>Veja a [transação de Joe para Alice](http://bit.ly/1tAeeGr).

Como você pode ver, a carteira de Alice contém bitcoins suficientes em um output não-gasto isolado para pagar pela xícara de café. Caso não contivesse, o aplicativo carteira de Alice teria que "vasculhar" uma pilha de pequenos outputs não-gastos, como se estivesse pegando as moedas em uma bolsa, até encontrar o suficiente para poder pagar o café. Em ambos os casos, pode haver uma necessidade de receber algum troco de volta, que é o assunto que iremos ver na próxima seção, quando o aplicativo carteira cria os outputs da transação (pagamentos).

####Criando os Outputs

Um output de transação é criado na forma de um script que cria um "desafio" no valor a ser transferido, de maneira que o valor só pode ser regastado se uma solução for apresentada ao script. De maneira simplificada, o output da transação de Alice irá conter um script que diz algo como "Esse output é pagável para aquela pessoa que conseguir apresentar uma assinatura para a chave correspondente ao endereço público de Bob". Como somente o Bob possui a carteira com as chaves correspondentes àquele endereço, somente a carteira de bob pode apresentar a assinatura para resgatar esse output. A Alice ao fazer uma exigência de assinatura do Bob, ela está fazendo um "desafio" no valor de output.

Essa transação também incluirá um segundo output, porque os fundos de Alice estão na forma de um output de 0,10 BTC, que é dinheiro demais para a transação de 0,015 BTC pela xícara de café. A Alice precisará de 0,085 BTC de troco. O pagamento do troco da Alice é criado _pela carteira de Alice_ na mesma transação que o pagamento do Bob. Essencialmente, a carteira de Alice divide seus fundos em dois pagamentos: um para o Bob, e outro de volta para si mesmo. Ela pode então usar o output do troco em uma transação no futuro, gastando-o mais tarde.

Finalmente, para que a transação seja processada pela rede em tempo hábil, o aplicativo de carteira da Alice irá adicionar uma pequena taxa. Isso não está explícito na transação: isso está implícito na diferença entre os inputs e os outputs. Se ao invés de receber 0,085 de troco, Alice cria somente 0,0845 como um segundo output, haverá 0,0005 (metade de um milibitcoin) restantes. O input de 0,10 BTC não é totalmente gasto com os dois outputs, porque ele irá se somar até menos do que 0,10.  A diferença resultante é a _taxa de transação_ que é coletada pelo minerador como um pagamento por ter incluído a transação em um bloco e adicionar esse bloco no ledger da blockchain.

A transação resultante pode ser vista usando um aplicativo web explorador de blockchain, como visto em [Transação da Alice para o Bob’s Cafe](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-alice).

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0208.png)
Figura 8. Transação de Alice para o Bob’s Cafe

Dica
>Veja a [transação de Alice para o Bob’s Cafe](http://bit.ly/1u0FIGs).

####Adicionando uma Transação ao Ledger

A transação criada pelo aplicativo de carteira da Alice tem 258 bytes de comprimento e contém todas as informações necessárias para confirmar a sua posse dos fundos e para designar novos donos. Agora, a transação deve ser transmitida para rede bitcoin, onde ela tornará-se parte do ledger distribuído (da blockchain). Na próxima seção, iremos ver como a transação torna-se parte de um novo bloco e como o bloco é "minerado". Por fim, iremos ver como o novo bloco, após ser adicionado à blockchain, torna-se cada vez mais confiável conforme novos blocos são adicionados posteriormente à ele.

#####Transmitindo a transação

Como a transação contém toda a informação necessária para que seja processada, não importa como ou onde ela é transmitida para a rede bitcoin. A rede bitcoin é uma rede ponto-a-ponto (P2P0, com cada cliente bitcoin participando ao se conectar a múltiplos outros clientes bitcoins. A proposta da rede bitconi é propagar as transações e os blocos para todos os participantes.

#####Como ela se propaga

O aplicativo carteira da Alice pode enviar a nova transação para qualquer um dos outros clientes bitcoins se ele estiver conectado através de uma conexão de Internet: por cabo, WiFi ou móvel. A sua carteira não tem que obrigatoriamente estar conectada diretamente à carteira do Bob ou usar a conexão de internet oferecida pela cafeteria, embora essas opções também sejam possíveis. Qualquer nodo (outro cliente) na rede bitcoin que recber uma transação válida que não tenha sido vista anteriormente irá imediatamente propagá-la para outros nodos com os quais está ligado. Logo, a transação rapidamente é propagada através da rede ponto-a-ponto (P2P), atingindo uma grande percentagem dos nodos dentro de poucos segundos.

#####Visão do Bob

Se o aplicativo carteira do bob estiver diretamente conectado ao aplicativo carteira da Alice, o aplicativo pode ser o primeiro nodo a receber a transação. Entretanto, mesmo que a carteira de Alice envia a tranação através de outros nodos, a transação chegará à carteira do Bob dentro de pouco segundos. A carteira de Bob irá identificar imediatamente a transação de Alice como um pagamento porque ela contém outputs que são resgatáveis pelas chaves do Bob. O aplicativo carteira de Bob também pode verificar independentemente que a transação é bem formada, utiliza inputs previamente não-gastos e contém taxas de transação suficientes para ser incluída no próximo bloco. Neste momento o Bob pode esperar, com um alto grau de probabilidade, que a transação será em breve incluída em um bloco e será confirmada.

Dica
>Uma ideia erroneamente difundida é a de que as transações bitcoin, para serem "comprovadas", exigem uma espera de 10 minutos por um novo bloco, ou de até 60 minutos por seis confirmações. Embora essas confirmações sejam uma garantia de que a transação foi aceita por toda a rede, a espera por elas é desnecessária para ítens de pequeno valor, como uma xícara de café. Ao aceitar uma transação de pequeno valor como comprovadamente válida, o comerciante estará correndo um risco menor do que quando recebe um pagamento de cartão de crédito feito sem assinatura ou carteira de identidade.

###Mineração de Bitcoin

A transação foi propagada na rede bitcoin. Ela só vai tornar-se parte de ledger compartilhado (a _blockchain_) quando for verificada e incluída em um bloco, através de um processo chamado _mineração_. Veja [[ch8]](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#ch8) para uma explicação mais detalhada.

O sistema de confiança do bitcoin é baseado em computação. As transações são agrupadas em blocos, o que requer uma enorme quantidade de processamento para prová-las, mas apenas uma pequena quantidade de processamento para verificá-las como previamente provadas. O processo de mineração do bitcoin tem duas propostas:

Criar novos bitcoins em cada bloco, quase como um banco central imprimindo novas moedas e notas. A quantidade de bitcoin criada por bloco é fixa e diminui com o tempo.

Criar confiança, ao garantir que as transações sejam confirmadas somente se poder de processamento suficiente for dedicado ao bloco que as contém. Mais blocos requerem mais processamento, o que significa maior confiança.

Uma boa maneira de descrever a mineração é como um jogo de sudoku, gigantesco e competitivo, que reinicia cada vez que alguém encontra uma solução e cuja dificuldade se ajusta automaticamente, de maneira que leve cerca de 10 minutos para que uma solução seja encontrada. Imagine um sudoku gigantesco, com milhares de colunas e linhas de tamanho. Se eu mostrar para você um sudoku completo, você pode verificar rapidamente que ele está corretamente preenchido. No entando, se o sudoku tiver apenas alguns quadrados preenchidos e o resto estiver vazio, levará muito trabalho para resolvê-lo! A dificuldade do sudoku pode ser ajustada ao mudar o seu tamanho (mais ou menos linhas ou colunos), mas o sudoku ainda pode ser verificado de maneira rápida, mesmo que ele seja muito grande. O "sodoku" usado no bitcoin é baseado em um hash criptográfico, que exibe características semelhantes: ele é assimetricamente difícil de resolver, mas fácil de verificar, e sua dificuldade pode ser ajustada.

Nas [histórias dos usuários](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#user-stories), nós apresentamos o Jing, um estudante de engenharia da computação de Shangai. Ele está participando da rede bitcoin como um minerados. A cada 10 minutos em média, Joing se une a milhares de outros mineradores para uma corrida global para achar uma solução para um bloco de transações. Encontrar uma solução, também chamada de prova de trabalho, requer quadrilhões de operações de hashing por segundo ao longo de toda a rede bitcoin. O algoritmo para a prova de tarbalho envolve fazer hashing com o cabeçalho do bloco e um número aleatório com um algoritmo criptográfico SHA256 até que a solução correspondente a um determinado padrão surja. O primeiro minerador a encontrar uma solução ganha a rodada da competição e publica o bloco na blockchain.

Jing começou a minerar em 2010 usando um computador destktop muito rápido para achar provas de trabalho adequadas para novos blocos. Conforme mais mineradores começaram a se juntas à rede bitcoin, a dificuldade do problema cresceu rapidamente. Logo em seguida, Jing e outros mineradores fizeram upgrade para um hardware mais especializado, como placas com unidades de processamento gráfico (GPUs) dedicadas de alta performance, como as placas de vídeo utilizadas para jogos de desktop ou videogames. Nesse momento, a dificuldade está tão alta que só é rentável minerar com circuitos integrados específicos para a aplicação (ASIC), que é essencialmente centenas de algoritmos de mineração impresso em hardware, rodando em paralelo em um único chip de silício. Jing também se uniu ao "mining pool", que é como um pool loteria que permite que vários participantes compartilhem seus esforços e recompensas. Jing agora roda duas máquinas ASIC ligadas a USB para minerar bitcoins 24 horas por dia. Ele paga seus custos de eletricidade com a venda dos seus bitcoins minerados, obtendo algum lucro dos seus bitcoins. Seu computador roda uma cópia do bitcoind, um cliente bitcoin de referência, como um backend para seu software de mineração especializado.

###Mining Transactions in Blocks

A transaction transmitted across the network is not verified until it becomes part of the global distributed ledger, the blockchain. Every 10 minutes on average, miners generate a new block that contains all the transactions since the last block. New transactions are constantly flowing into the network from user wallets and other applications. As these are seen by the bitcoin network nodes, they get added to a temporary pool of unverified transactions maintained by each node. As miners build a new block, they add unverified transactions from this pool to a new block and then attempt to solve a very hard problem (a.k.a., proof of work) to prove the validity of that new block. The process of mining is explained in detail in [mining](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#mining).

Transactions are added to the new block, prioritized by the highest-fee transactions first and a few other criteria. Each miner starts the process of mining a new block of transactions as soon as he receives the previous block from the network, knowing he has lost that previous round of competition. He immediately creates a new block, fills it with transactions and the fingerprint of the previous block, and starts calculating the proof of work for the new block. Each miner includes a special transaction in his block, one that pays his own bitcoin address a reward of newly created bitcoins (currently 25 BTC per block). If he finds a solution that makes that block valid, he "wins" this reward because his successful block is added to the global blockchain and the reward transaction he included becomes spendable. Jing, who participates in a mining pool, has set up his software to create new blocks that assign the reward to a pool address. From there, a share of the reward is distributed to Jing and other miners in proportion to the amount of work they contributed in the last round.

Alice’s transaction was picked up by the network and included in the pool of unverified transactions. Because it had sufficient fees, it was included in a new block generated by Jing’s mining pool. Approximately five minutes after the transaction was first transmitted by Alice’s wallet, Jing’s ASIC miner found a solution for the block and published it as block #277316, containing 419 other transactions. Jing’s ASIC miner published the new block on the bitcoin network, where other miners validated it and started the race to generate the next block.

You can see the block that includes [Alice’s transaction](https://blockchain.info/block-height/277316).

A few minutes later, a new block, #277317, is mined by another miner. Because this new block is based on the previous block (#277316) that contained Alice’s transaction, it added even more computation on top of that block, thereby strengthening the trust in those transactions. The block containing Alice’s transaction is counted as one "confirmation" of that transaction. Each block mined on top of the one containing the transaction is an additional confirmation. As the blocks pile on top of each other, it becomes exponentially harder to reverse the transaction, thereby making it more and more trusted by the network.

In the diagram in [Alice’s transaction included in block #277316](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#block-alice1) we can see block #277316, which contains Alice’s transaction. Below it are 277,316 blocks (including block #0), linked to each other in a chain of blocks (blockchain) all the way back to block #0, known as the _genesis block_. Over time, as the "height" in blocks increases, so does the computation difficulty for each block and the chain as a whole. The blocks mined after the one that contains Alice’s transaction act as further assurance, as they pile on more computation in a longer and longer chain. By convention, any block with more than six confirmations is considered irrevocable, because it would require an immense amount of computation to invalidate and recalculate six blocks. We will examine the process of mining and the way it builds trust in more detail in [ch8](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#ch8).

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0209.png)
Figure 9. Alice’s transaction included in block #277316

###Gastando a transação

Agora que a transação da Alice foi incorporada à blockchain como parte de um bloco, ela faz parte do ledger distribuído do bitcoin e está visível para todos as aplicações bitcoin. Cada cliente bitcoin pode verificar independentemente que a transação é válida e que seus fundos podem ser gastos. Clientes de índice completo (full-index) podem rastrear a origem dos fundos desde o início, ou seja, o momento em que os bitcoins foram gerados em um bloco, e, progredindo de transação a transação, até chegarem ao endereço do Bob. Clientes leves (lightweight) podem fazer uma verificação simplificada de pagamento (ver [spv_nodes](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#spv_nodes)) ao confirmar que a transação está presente na blockchain e que vários blocos foram minerados após ela, garantindo que ela foi aceita pela rede como válida.

O Bob agora pode gastar o output desta e de outras transações, ao criar suas próprias transações que usam esses outputs como inputs e os designam para um novo dono. Por exemplo, Bob pode pagar um fornecedor ao transferir, para este novo dono, o valor do pagamento da xícara de café da Alice. Mais provavelmente, o software de bitcoin do Bob irá agregar vários pequenos pagamentos em um pagamento maior, talvez concentrando em uma única transação todo o lucro em bitcoins obtidos na loja em um dia. Isso moveria todos os pagamentos para um endereço único, usado como uma conta de "checking" geral da loja. Para ver um diagrama de uma transação agregadora, leia [Transaction aggregating funds](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#transaction-aggregating).

À medida que o Bob gasta os pagamentos que recebeu de Alice e outros clientes, ele estende a cadeia de transações, que por sua vez são adicionadas ao ledger global do blockchain para que todos possam ver e confiar. Vamos assumir que o Bob paga seu web designer Gopesh em Bangalore para desenvolver um novo site. Agora a cadeia de transações irá ficar parecida como na figura [Transação da Alice fazendo parte de uma cadeia de transação do Joe para o Gopesh](https://github.com/aantonop/bitcoinbook/blob/develop/ch02.asciidoc#block-alice2).

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0210.png)
Figura 10. Transação da Alice fazendo parte de uma cadeia de transação do Joep ara o Gopesh
