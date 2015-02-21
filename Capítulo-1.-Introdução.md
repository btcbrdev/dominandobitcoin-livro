#Introdução

##O que é Bitcoin?
Bitcoin é uma coleção de conceitos e tecnologias que formam a base de um ecossistema de dinheiro digital. Unidades de moeda chamadas bitcoins são usadas para armazenar e transmitir valor entre os participantes na rede Bitcoin. Usuários Bitcoin comunicam-se entre si usando o protocolo bitcoin (geralmente através da Internet), embora outras redes de transporte também possam ser usadas. A pilha de protocolo bitcoin, disponível como software de código aberto, pode ser executada em uma ampla variedade de dispositivos com capacidade de computação, incluindo laptops e smartphones, tornando a tecnologia facilmente acessível.

Os usuários podem transferir bitcoins através da rede para fazer praticamente qualquer coisa que pode ser feita com moedas convencionais, incluindo compra de venda de bens, envio de dinheiro a pessoas e organizações ou a extensão de crédito. Os bitcoins podem ser comprados, vendidos ou trocados por outras moedas em casas de câmbio especializadas. Bitcoin é, em suma, o dinheiro perfeitamente adequado para a Internet, pois é rápido, seguro e sem fronteiras.

Ao contrário das moedas tradicionais, os bitcoins são inteiramente virtuais. Não há moedas físicas ou mesmo moedas digitais por si só. As moedas de bitcoin se subentendem em transações que transferem valor de um remetente a um destinatário. Os usuários de bitcoin possuem chaves que lhes permitem provar a posse de transações na rede bitcoin, desbloqueando o valor a ser gasto e enviado para um novo destinatário. Essas chaves geralmente são armazeu em uma carteira digital no computador ou smartphone de cada usuário. A posse da chave que desbloqueia uma transação é o único pré-requisito para gastar os bitcoins, o que coloca o controle inteiramente nas mãos de cada usuário.

Bitcoin é um sistema distribuído, ponto-a-ponto (_peer-to-peer_ ou P2P). Como tal, não existe um servidor "central" ou ponto de controle. Os bitcoins são criados (gerados) através de um processo chamado de mineração, que consiste em competir para encontrar soluções para um problema matemático enquanto se processam transações de bitcoins. Qualquer participante na rede bitcoin (ou seja, qualquer um usando um dispositivo que execute a pilha completa de protocolo Bitcoin) pode operar como um mineiro, usando o poder de processamento de seu computador para verificar e registrar transações. A cada 10 minutos em média, alguém é capaz de validar as transações dos últimos 10 minutos, sendo recompensado com bitcoins novinhos em folha. Essencialmente, a mineração de bitcoin descentraliza as funções de emissão de moeda e de compensação tipicamente atribuídas a um banco central, substituindo a necessidade de qualquer banco central nesta competição global, que é a mineração.

O protocolo bitcoin contêm algoritmos embutidos que regulam a função de mineração através da rede. A dificuldade da tarefa de processamento que os mineiros devem realizar - registrar com sucesso um bloco de transações na rede bitcoin - ajusta-se dinamicamente de tal forma que alguém é bem-sucedido a cada 10 minutos, na média, independentemente de quantos mineiros (e CPUs) estejam trabalhando na tarefa a qualquer momento.

O protocolo também reduz à metade, a cada 4 anos, a taxa com que novos bitcoins são criados e limita o número total de bitcoins que serão criados a um máximo de 21 milhões de moedas. O resultado é que o número de bitcoins em circulação seguem uma curva previsível que alcança 21 milhões no ano de 2140. Devido à taxa decrescente de emissão, no longo prazo a moeda bitcoin é deflacionária. Ademais, bitcoin não pode ser inflacionada "imprimindo" novo dinheiro mais rápido que a taxa de emissão esperada.

Nos bastidores, bitcoin é também o nome do protocolo, de uma rede e de uma inovação digital distribuída. A moeda bitcoin é, na verdade, apenas a primeira aplicação desta invenção. Como um programador, eu vejo bitcoin parecido com a Internet do dinheiro, uma rede para propagar valor e proteger a posse de ativos digitais através da computação distribuída. Há muito mais em bitcoin do que se enxerga à primeira vista.

Neste capítulo inicial ensinaremos alguns dos principais conceitos e termos, além de como baixar o software necessário e como usar o bitcoin para transações simples. Nos capítulos seguintes iremos desembrulhar as capas da tecnologia que tornam bitcoin possível e examinar o funcionamento interno da rede e do protocolo bitcoin.

### Moedas Digitais Antes do Bitcoin

A aparição de um dinheiro digital viável está ligada de perto à evolução da criptografia. Não é uma surpresa quando alguém leva em conta que os desafios fundamentais envolvidos no uso de bits para representar valor que pode ser trocado por bens e serviços. Duas perguntas básicas feitas por qualquer um que aceite dinheiro digital são:

1. Posso confiar que o dinheiro é autêntico e não falsificado?
2. Posso estar seguro de que ninguém vai reclamar que esse dinheiro lhe pertence e não a mim? (também conhecido como o problema do "gasto duplicado")

Os emissores do dinheiro em papel estão o tempo todo batalhando o problema da falsificação com o uso de papéis e tecnologias de impressão cada vez mais sofisticados. O dinheiro físico resolve facilmente o problema do gasto duplicado, pois a mesma nota em papel não pode estar em dois lugares ao mesmo tempo. Mas é claro, o dinheiro convencional com frequência se armazena e se transmite de forma digital. Nestes casos, os problemas de falsicação e de gastos duplicados são tratados pela compensação de todas as transações eletrônicas através de autoridades centrais que detêm uma visão global da moeda em circulação. No caso do dinheiro digital, que não pode se beneficiar de tintas esotéricas ou marcas holográficas, a criptografia proporciona a base da confiança na legitimidade da exigência de um usuário pelo seu valor. Especificamente, as assinaturas digitais criptográficas permitem a um usuário assinar um ativo digital ou transação provando a posse do ativo. Com a arquitetura apropriada, as assinaturas digitais também podem ser usadas para resolver o problema do gasto duplicado. 

Quando a criptografia começou a se tornar mais comum e entendida no final dos anos 80, muitos pesquisadores começaram a tentar usá-la para construir moedas digitais. Estes projetos pioneiros emitiam dinheiro digital, normalmente embasado por uma moeda nacional ou um metal precioso como o ouro.

Apesar destas moedas digitais pioneiras funcionarem, elas eram centralizadas e, como resultado, eram fáceis de atacar tanto por governos como por _hackers_. As moedas digitais pioneiras usavam uma central de compensação para finalizar todas as transações em intervalos regulares, da mesma forma que um sistema bancário tradicional. Infelizmente, em muitos casos essas moedas digitais que surgiam se tornavam um alvo dos governos preocupados e eventualmente desapareciam. Algumas falharam em quebras espetaculares quando a companhia responsável era liquidada de repente. Para ser robusta contra a intervenção de opositores, sejam governos legítimos ou elementos criminais, uma moeda descentralizada digital se tornava necessária para evitar um único ponto de ataque. Este sistema é Bitcoin, completamente descentralizado por _design_, e livre de qualquer autoridade central ou ponto de controle que pode ser atacado ou corrompido.

Bitcoin representa o auge de décadas de pesquisa em criptografia e sistemas distribuídos e inclui 4 inovações chaves unidas em uma combinação única e poderosa. Bitcoin consiste em:

* Uma rede _peer-to-peer_ descentralizada (o protocolo bitcoin)
* Um registro público de transações (a blockchain ou cadeia de blocos)
* Uma emissão de moeda descentralizada, matemática e determinística (a mineração distribuída)
* Um sistema descentralizado de verificação de transações (o script de transação)

##A História do Bitcoin

O Bitcoin foi inventado em 2008 com a publicação de um paper entitulado com a publicação de um paper entitulado "Bitcoin: Um Sistema de Dinheiro em Espécie Eletrônico" (_"Bitcoin: A Peer-to-Peer Electronic Cash System"_ em inglês), escrito sob o pseudônimo de Satoshi Nakamoto. Nakamoto combinou várias das invenções anteriores tais como b-money e HashCash para criar um sistema de dinheiro vivo eletrônico completamente descentralizado que não depende de uma autoridade central para a emissão de moeda ou para a liquidação e validação de transações. A inovação chave foi usar um sistema de computação distribuído (chamado algoritmo de "prova de trabalho" ou _"proof of work"_) para conduzir uma "eleição" global a cada 10 minutos, permitindo à rede descentralizada chegar em um consenso sobre o estado das transações. Isto resolve de forma elegante o problema de gasto duplicado onde uma única unidade de moeda poderia ser gasta duas vezes. Antes o problema de gasto duplicado era uma fraqueza do dinheiro digital e se solucionava liquidando todas as transações através de uma entidade central.

A rede bitcoin começou em 2009, baseado em uma implementação de referência publicada por Nakamoto e desde então revisada por muitos outros programadores. A computação distribuída que proporciona segurança e robustez ao bitcoin cresceu exponencialmente, e agora excede a capacidade combinada de processamento dos principais supercomputadores do mundo. O valor de mercado do bitcoin se estima entre 5 e 10 bilhões de dólares americanos, dependendo da taxa de câmbio entre o bitcoin e o dólar. A maior transação processada até o momento pela rede foi de US$ 150 milhões, transmitidos instantaneamente e processados sem nenhuma taxa.

Satoshi Nakamoto se afastou do público em abril de 2011, deixando a responsabilidade pelo desenvolvimento do código e da rede nas mão de um animado grupo de voluntários. A identidade da pessoa ou pessoas por trás do bitcoin ainda é desconhecida. No entanto, nem Satoshi Nakamoto nem qualquer outra pessoa exerce controle sobre o sistema bitcoin, que opera baseado em princípios matemáticos totalmente transparentes. O próprio invento é revolucionário e já gerou nova ciência nos campos da computação distribuída, economia e econometria.

###Uma Solução para um Problema de Computação Distribuída
O invento de Satoshi Nakamoto é também uma solução prática para um problema que até então não estava resolvido em computação distribuída, conhecido como o "Problema dos Generais Bizantinos". Em resumo, o problema consiste em tentar tomar uma decisão através do intercâmbio de informações sobre uma rede pouco confiável e potencialmente comprometido. A solução de Satoshi Nakamoto, que utiliza o conceito de prova de trabalho para alcançar o consenso sem uma autoridade central confiável, representa um enorme avanço na ciência de computação distribuída e possui amplas aplicações além de moedas. Pode ser usado para alcançar consenso em redes descentralizadas para provar a honestidade de eleições, loterias, registros de bens, cartórios digitais e mais.

##Usos do Bitcoin, Seus Usuários e Suas Histórias

Bitcoin é uma tecnologia, mas ela expressa dinheiro que é fundamentalmente uma linguagem para a troca de valor entre pessoas. Vamos dar uma olhada nas pessoas que estão usando bitcoin e alguns dos usos mais comuns da moeda e do protocolo através de suas histórias. Iremos reutilizar essas histórias ao largo do livro para ilustrar os usos do dinheiro digital na vida real e como eles se tornaram possíveis por meio das várias tecnologias que formam parte do bitcoin.

_**Comércio de ítems de baixo valor nos Estados Unidos**_

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

##Como Começar

Para participar da rede bitcoin e começar a usar a moeda, tudo que um usuário tem de fazer é baixar uma aplicação ou usar uma aplicação _web_. Como o bitcoin é um padrão, há muitas implementações do software de cliente bitcoin. Também há uma implementação de referência, conhecida como o cliente Satoshi, que é administrado como um projeto de código aberto por uma equipe de programadores e provém da implementação original escrita por Satoshi Nakamoto.
The three main forms of bitcoin clients are:

_**Cliente completo**_

Um cliente completo, ou "nó completo", é um cliente que armazena todo o histórico de transações de bitcoins (cada uma das transações de todos os usuários, desde o começo), gerencia as carteiras dos usuários e pode iniciar transações diretamente na rede bitcoin. Isto é similar a um servidor de email independente, no sentido de que ele trata de todos os aspectos do protocolo sem depender de quaisquer outros servidores ou serviços de terceiros.


_**Cliente compacto**_

Um cliente compacto guarda a carteira do usuário mas depende de servidores mantidos por terceiros para ter acesso às transações e à rede Bitcoin. O cliente compacto não guarda uma cópia completa de todas as transações e portanto precisa confiar nos servidores de terceiros para validar transações. É similar a um cliente de email autônomo que se conecta a um servidor de email para acessar uma caixa de emails, no sentido de que depende de um terceiro para interagir com a rede.

_**Cliente web**_

Os clientes web se utilizam através de um navegador web e armazena a carteira do usuário em um servidor mantido por um terceiro. São similares ao webmail no sentido de que eles dependem completamente de um servidor de terceiro.

_**Clientes móveis**_

Os clientes móveis para smartphones, tais como aqueles baseados no sistema Android, pode operar tanto como clientes completos, clientes compactos ou clientes web. Alguns clientes móveis se sincronizam com um cliente web ou de PC, propocionando assim uma carteira multiplataforma entre múltiplos dispositivos mas com uma fonte comum de fundos.

A escolha do cliente bitcoin depende de quanto controle o usuário quer sobre os fundos. Um cliente completo irá oferecer o máximo nível de controle e independência do usuário mas, em compensação, deixa a responsabilidade pelos backups e pela segurança nas mãos do usuário. No outro extremo de opções, um cliente web é o mais fácil de configurar de de usar mas, em compensação, um cliente web introduz um risco de contraparte já que a segurança e o controle se compartilha com o usuário e o dono do serviço web. Se um serviço de carteira web é comprometido, como muitos já foram, os usuários podem perder todos os seus fundos. Por outro lado, se os usuários tiverem um cliente completo sem os backups adequados, eles podem perder todos os seus fundos por causa de um contratempo do computador.

Para os propósitos deste livro, demonstraremos o uso de uma variedade de clientes bitcoin que se podem baixar, desde a implementação de referência (o cliente Satoshi) às carteiras web. Alguns dos exemplos vão necessitar o uso do cliente de referência, que além de ser um cliente completo também expõe APIs de acesso à carteira, à rede e aos serviços de transações. Se você planeja explorar as interfaces programáticas de acesso ao sistema Bitcoin, você irá precisar do cliente de referência.

###Iniciação Rápida

Alice, a quem apresentamos na seção "Usos do Bitcoin, Seus Usuários e Suas Histórias" não é uma usuária técnica e só recentemente ouviu falar do bitcoin por um amigo. Ela começa sua jornada visitando o website oficial bitcoin.org, onde ela encontra uma ampla seleção de clientes bitcoin. Seguindo o conselho do site bitcoin.org, ela escolhe o cliente bitcoin compacto Multibit.

Alice segue um link do site bitcoin.org para baixar e instalar Multibit no PC dela. Multibit está disponível para computadores Windows, Mac OS e Linux.

[Atenção]
Uma carteira bitcoin deve ser protegida por uma senha ou frase. Há muitos agentes maliciosos tentando quebrar senhas fracas, então tenha o cuidado de selecionar uma que não possa ser facilmente adivinhada. Use uma combinação de caracteres maiúsculos e minúsculos, números e símbolos. Evite usar informação pessoal como datas de nascimento ou nomes de times de futebol. Evite quaiquer palavras facilmente encontradas em dicionários, em qualquer língua. Se puder, use um gerador de senhas para criar uma senha completamente aleatória que tenha no mínimo 12 caracteres de comprimento. Lembre-se: bitcoin é dinheiro e pode ser transferido instantaneamente para qualquer lugar do mundo. Se não for bem protegido, ele pode ser facilmente roubado.

Assim que a Alice terminar de baixar e instalar a aplicação Multibit, ela o executa e a tela de Boas-Vindas a saúda, como mostrado na tela de boas-vindas do cliente Multibit.

![](https://github.com/aantonop/bitcoinbook/blob/develop/images/msbt_0101.png)

Figura 1. A tela de boas-vindas do cliente bitcoin Multibit

Multibit automaticamente cria uma carteira e um novo endereço bitcoin para Alice, que Alice pode ver fazendo clique na aba _Solicitar_.



![](https://github.com/aantonop/bitcoinbook/blob/develop/images/msbt_0102.png)

Figura 2. O novo endereço bitcoin da Alice, na aba _Solicitar_ do cliente Multibit


A parte mais importante desta tela é o endereço bitcoin da Alice. Assim como um endereço de email, a Alice pode compartilhar este endereço e qualquer um pode usá-lo para mandar dinheiro diretamente à carteira dela. Na tela aparece uma longa sequência de letras e números: 1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK. Junto ao endereço bitcoin da carteira está um código QR, um forma de código de barras que contém a mesma informação mas em um formato que pode ser escaneado pela câmera de um smartphone. O código QR é o quadrado branco e negro no lado direito da janela. A Alice pode copiar o endereço bitcoin ou o código QR clicando no botão _copy_ junto de cada um deles. Ao clicar no próprio código QR ele será ampliado, podendo facilmente ser escaneado pela câmera de um smartphone.

A Alice pode também imprimir o código QR para entregar facilmente seu endereço a outras pessoas sem que eles tenham de se lembrar de digitar uma longa sequência de letras e números.

[Dica]
> Os endereços bitcoin começam sempre com o dígito 1 ou o dígito 3. Assim como endereços de email, eles podem ser compartilhados com outros usuários bitcoin que podem usá-los para mandar bitcoin diretamente a sua carteira. Ao contrário dos endereços de email, você pode criar tantos novos endereços como queira, e todos receberão fundos em sua carteira. Uma carteira é simplesmente uma coleção de endereços e as chaves que desbloqueiam os fundos que estão nela. Você pode aumentar a sua privacidade usando um endereço diferente para cada transação. Não há nenhuma limitação na quantidade de endereços que um usuário pode criar.

Agora a Alice está pronta para começar a usar a nova carteira bitcoin dela.

###Obtendo Os Seus Primeiros Bitcoins

Ainda não é possível comprar os bitcoins em um banco ou casa de câmbio de moedas estrangeiras. Em 2014, ainda é muito difícil adquirir bitcoins na maior parte dos países. Há algumas casas de câmbio especializadas onde você pode comprar e vender bitcoin pagando com a sua moeda local. Estas operam como os mercados de moedas online e delas fazem parte:

_**Bitstamp**_
Um mercado de moedas europeu que permite comprar várias moedas inclusive euros (EUR) e dólares americanos (USD) por transferência bancária.

_**Coinbase**_
Uma carteira e uma plataforma americanas de bitcoin onde comerciantes e consumidores podem fazer transações em bitcoin. Coinbase torna fácil comprar e vender bitcoin, permitindo aos usuários se conectarem às suas contas bancárias nos EUA através do sistema ACH (Automated Clearing House).

Casas de câmbio de criptomoedas como essas operam na interseção entre moedas nacionais e criptomoedas. Assim elas estão sujeitas às normas nacionais e internacionais e, com frequência, são específcas a um determinado país ou região econômica e se especializam nas moedas nacionais daquela região. Sua escolha de casas de câmcio será específica para moeda nacional que você usa e limitada às exchanges que operam dentro da jurisdição legal de seu país. De maneira similar a uma conta bancária, pode levar vários dias ou semanas para configurar as contas necessárias com estes serviços pois eles requerem várias formas de identificação para atender às exigências das regulações bancárias KYC (_know your customer_ ou conheça seu cliente) e AML (_anti-money laundering_ ou combate à lavagem de dinheiro). Assim que você tiver uma conta em um exchange bitcoin, você pode comprar e vender bitcoins rapidamente assim como você faria com uma moeda estrangeira em uma conta de corretagem.

Você pode encontrar uma lista mais completa em [Bitcoin Charts](http://bitcoincharts.com/markets/), que é um site que mostra as cotações e outros dados de mercado através de muitas dúzias de casas de câmbio.

Há outras 4 formas de conseguir bitcoins como um novo usuário:

* Encontre um amigo que tem bitcoins e compre alguns dele diretamente. Muitos usuários de bitcoin começam assim.

* Use um serviço de classificados como localbitcoins.com para encontrar um vendedor na sua área para comprar os bitcoins pagando em dinheiro em uma transação em pessoa.

* Venda um produto ou serviço por bitcoin. Se você for um programador, venda as suas habilidades de programação.

* Use um ATM bitcoin na sua cidade. Encontre um ATM bitcoin perto de você usando um mapa online da CoinDesk.

Alice foi apresentada ao bitcoin por um amigo e portanto ela tinha uma maneira fácil de conseguir os primeiros bitcoins dela enquanto ela espera que a conta dela em um mercado de moedas na Califórnia seja verificada e ativada.

###Mandando e Recebendo Bitcoins

Depois de criar a carteira bitcoin dela, a Alice agora está pronta para receber fundos. A aplicação de carteira gera aleatoriamente uma chave privada (descrita em mais detalhes em [private_keys]) junto com o endereço bitcoin correspondente. A partir deste ponto, o endereço bitcoin dela ainda não é conhecido na rede bitcoin nem "registrado" com qualquer parte do sistema bitcoin. Os endereços bitcoin dela é simplesmente um número que corresponde a uma chave que ela pode usar para controlar o acesso aos fundos. Não há uma conta ou associação entre aquele endereço e uma conta. Até o momento em que este endereço esteja referenciado como o destinatário de um valor em uma transação publicada no registro contábil de bitcoin (a cadeia de blocos), ele é simplesmente parte da vasta quantidade de possíveis endereços considerados "válidos" em bitcoin. A partir do momento em que esteja associado com uma transação, ele se torna parte dos endereços conhecidos na rede e a Alice poderá comprovar o saldo dela no registro público.

A Alice se encontrou com o amigo dela, o Joe, que a apresentou ao bitcoin, em um restaurante local para que eles possam trocar alguns dólares e colocar bitcoins na conta dela. Ela trouxe um papel com o endereço dela e o código QR impressos conforme aparecem na carteira bitcoin. Não há nenhuma informação que deva ser protegida, desde um ponto de vista de segurança, no endereço bitcoin. Ele pode ser publicado em qualquer lugar sem nenhum risco de segurança da conta dela.

A Alice quer trocar somente 10 dólares americanos por bitcoin, para que assim ela não arrisque muito dinheiro com essa nova tecnologia. Ela dá ao Joe uma nota de $10 e o papel impresso com seu endereço para que o Joe possa lhe mandar o montante equivalente em bitcoin.

A seguir, o Joe tem que descobrir a taxa de câmbio para que ele possa dar a quantia correta à Alice. Há centenas de aplicações e páginas web que podem proporcionar a taxa de mercado atual. Aqui há algumas das mais populares:

_**Bitcoin Charts**_
 Um serviço de listagem de dados do mercado que mostra a taxa de câmbio do bitcoin em várias casas de câmbio em todo o planeta, nas diferentes moedas locais

_**Bitcoin Average**_
 Um site que permite, de forma simples, ver a média ponderada dos volumes negociados em cada moeda. 

_**ZeroBlock**_
 Uma aplicação grátis para Android e iOS que mostra o preço do bitcoin em diferentes casas de câmbio (procure por "ZeroBlock, _a bitcoin market-rate application for Android and iOS_")

_**Bitcoin Wisdom**_
 Outro serviço de listagem de dados de mercado

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0103.png)

Figura 3. ZeroBlock, uma aplicação de preço de mercado do bitcoin para Android e iOS

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0104.png)

Figura 4. A tela de envio de bitcoin da carteira móvel Blockchain

Então o Joe digita o valor em bitcoins da transação, 0.10 bitcoin. Ele confere com cuidado para ter certeza de que digitou a quantia correta, pois ele está a ponto de transmitir dinheiro e qualquer erro pode sair muito caro. Finalmente ele aperta _Send_ para transmitir a transação. A carteira móvel do Joe constrói a transação que assigna 0.10 bitcoin ao endereço da Alice, gerando os fundos da carteira do Joe e assinando a transação com as chaves privadas dele. Isso informa a rede bitcoin que o Joe autorizou uma transferência de valor de one de seus endereços para o novo endereço da Alice. À medida que a transação se transmite conforme o protocolo _peer-to-peer_, ele rapidamente se propaga pela rede bitcoin. Em menos de 1 segundo, a maioria dos nós melhor conectados da rede recebem a transação e vêem o endereço da Alice pela primeira vez.

Se a Alice tivesse trazido um smartphone ou um laptop com ela, ela seria também capaz de ver a transação. O registro contábil do bitcoin, que é um arquivo que não pára de crescer e que guarda cada uma das transações em bitcoin que já ocorreram desde o início, é público e isso significa que tudo que ela tem de fazer é olhar seu próprio endereço e ver se quaisquer fundos foram mandados para ele. É muito fácil para ela fazer isto no site da blockchain.info, digitando o endereço dela no campo de busca. O website lhe vai mostrar uma página listando todas as transações de e para esse endereço. Se a Alice estiver olhando essa página, vai ver uma atualização que mostra uma nova transação transferindo 0.10 bitcoin para o saldo dela logo depois do Joe apertar _Send_.

### Confirmações

Ao princípio, o endereço da Alice vai mostrar a transação do Joe como "Transação não Confirmada." Isto significa que a transação já se propagou pela rede mas ainda não foi incluída no registro contábil de transações do bitcoin, conhecido como a cadeia de blocos. Para ser incluído, a transação deve ser This means that the transaction has been propagated to the network but has not yet been included in the bitcoin transaction ledger, known as the blockchain. To be included, the transaction must be "picked up" by a miner and included in a block of transactions. Once a new block is created, in approximately 10 minutes, the transactions within the block will be accepted as "confirmed" by the network and can be spent. The transaction is seen by all instantly, but it is only "trusted" by all when it is included in a newly mined block.

Alice is now the proud owner of 0.10 bitcoin that she can spend. In the next chapter we will look at her first purchase with bitcoin, and examine the underlying transaction and propagation technologies in more detail.