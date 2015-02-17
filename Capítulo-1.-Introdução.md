#Introdução

##O que é Bitcoin?
Bitcoin é uma coleção de conceitos e tecnologias que formam a base de um ecossistema de dinheiro digital. Unidades de moeda chamadas bitcoins são usadas para armazenar e transmitir valor entre os participantes na rede Bitcoin. Usuários Bitcoin se comunicam entre si usando o protocolo bitcoin principalmente através da Internet, apesar de que outras redes de transporte também possam ser usadas. A pilha de protocolo bitcoin, disponível como software de código aberto, pode ser executada em uma ampla variedade de dispositivos com capacidade de computação, incluindo laptops e smartphones, tornando a tecnologia facilmente acessível.

Os usuários podem transferir bitcoins através da rede para fazer praticamente qualquer coisa que pode ser feita com moedas convencionais, incluindo a compra de venda de bens, o envio de dinheiro a pessoas ou organizações, ou a extensão de crédito. Os bitcoins podem ser comprados, vendidos ou trocados por outras moedas em casas de câmbio especializadas. Bitcoin é, em um sentido, uma forma perfeita de dinheiro para a Internet pois é rápido, seguro e sem fronteiras.

Ao contrário das moedas tradicionais, os bitcoins são inteiramente virtuais. Não há moedas físicas ou mesmo moedas digitais por si só. As moedas de bitcoin se subentendem em transações que transferem valor de um remetente a um destinatário. Os usuários de bitcoin possuem chaves que lhes permitem provar a posse de transações na rede bitcoin, desbloqueando o valor a ser gasto e enviado para um novo destinatário. Essas chaves com freqüência se armazenam em uma carteira digital no computador de cada usuário. A posse da chave que desbloqueia uma transação é o único pré-requisito para gastar os bitcoins, o que coloca o controle inteiramente nas mãos de cada usuário.

Bitcoin é um sistema distribuído, peer-to-peer. Como tal, não existe um servidor "central" ou ponto de controle. Os bitcoins se criam através de um processo chamado de "mineração", que consiste em competir para encontrar soluções para um problema matemático enquanto se processam transações de bitcoins. Qualquer participante na rede bitcoin (ou seja, qualquer um usando um dispositivo que execute a pilha completa de protocolo Bitcoin) pode operar como um mineiro, usando o poder de processamento do computador dele para verificar e registrar transações. A cada 10 minutos em média, alguém é capaz de validar as transações dos últimos 10 minutos e é recompensado com bitcoins novinhos em folha. Essencialmente, a mineração de bitcoin descentraliza as funções de emissão de moeda e de compensação típicas de um banco central e substitui a necessidade de qualquer banco central nesta competição global [que é a mineração].

O protocolo bitcoin contêm algoritmos embutidos que regulam a função de mineração através da rede. A dificuldade da tarefa de processamento que os mineiros devem realizar - para registrar com sucesso um bloco de transações para a rede bitcoin - se ajusta dinamicamente de tal forma que alguém é bem-sucedido a cada 10 minutos, na média, independentemente de quantos mineiros (e CPUs) estejam trabalhando na tarefa a qualquer momento. O protocolo também reduz à metade, a cada 4 anos, a taxa com que novos bitcoins são criados e limita o número total de bitcoins que serão criados a um total fixo de 21 milhões de moedas. O resultado é que o número de bitcoins em circulação acompanham de perto uma curva previsível que alcança 21 milhões no ano de 2140. Devido à taxa decrescente de emissão, no longo prazo a moeda bitcoin é deflacionária. Ademais, bitcoin não pode ser inflacionada "imprimindo" novo dinheiro mais rápido que a taxa de emissão esperada.

Nos bastidores, bitcoin é também o nome do protocolo, de uma rede e de uma inovação informática distribuída. A moeda bitcoin é na verdade tão somente a primeira aplicação desta invenção. Como um programador, eu vejo bitcoin parecido com a Internet do dinheiro, uma rede para propagar valor e proteger a posse de ativos digitais através da computação distribuída. Há muito mais em bitcoin do que se enxerga à primeira vista.

Neste capítulo começaremos explicando alguns dos principais conceitos e termos, obtendo o software necessário e usando bitcoin para transações simples. Nos próximos capítulos iremos desembrulhar as capas da tecnologia que tornam bitcoin possível e examinar o funcionamento interno da rede e do protocolo bitcoin.

###Moedas Digitais Antes do Bitcoin

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

Assim que a Alice terminar de baixar e instalar a aplicação Multibit, ela o executa e a tela de Boas-Vindas lhe sauda, como mostrado na tela de boas-vindas do cliente Multibit. *** inserir link à imagem abaixo

![](https://github.com/aantonop/bitcoinbook/blob/develop/images/msbt_0101.png)

Figura 1. A tela de boas-vindas do cliente bitcoin Multibit



![](https://github.com/aantonop/bitcoinbook/blob/develop/images/msbt_0102.png)

Figura 2. O novo endereço bitcoin da Alice, na aba _Request_ do cliente Multibit

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0103.png)

Figura 3. ZeroBlock, uma aplicação de preço de mercado do bitcoin para Android e iOS

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0104.png)

Figura 4. A tela de envio de bitcoin da carteira móvel Blockchain