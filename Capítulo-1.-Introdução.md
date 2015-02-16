#O que é Bitcoin?
Bitcoin é uma coleção de conceitos e tecnologias que formam a base de um ecossistema de dinheiro digital. Unidades de moeda (do original currency e não coin) chamadas bitcoins são usadas para armazenar e transmitir valor entre os participantes na rede bitcoin. Usuários Bitcoin se comunicam entre si usando o protocolo bitcoin principalmente através da Internet, apesar de que outras redes de transporte também possam ser usadas. A pilha de protocolo bitcoin, disponível como software de código aberto, pode ser executada em uma ampla variedade de dispositivos com capacidade de computação, incluindo laptops e smartphones, tornando a tecnologia facilmente acessível.

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

#História do Bitcoin

O Bitcoin foi inventado em 2008 com a publicação de um paper entitulado com a publicação de um paper entitulado "Bitcoin: Um Sistema de Dinheiro em Espécie Eletrônico" (_"Bitcoin: A Peer-to-Peer Electronic Cash System"_ em inglês), escrito sob o pseudônimo de Satoshi Nakamoto. Nakamoto combinou várias das invenções anteriores tais como b-money e HashCash para criar um sistema de dinheiro vivo eletrônico completamente descentralizado que não depende de uma autoridade central para a emissão de moeda ou para a liquidação e validação de transações. A inovação chave foi usar um sistema de computação distribuído (chamado algoritmo de "prova de trabalho" ou _"proof of work"_) para conduzir uma "eleição" global a cada 10 minutos, permitindo à rede descentralizada chegar em um consenso sobre o estado das transações. Isto resolve de forma elegante o problema de gasto duplicado onde uma única unidade de moeda poderia ser gasta duas vezes. Antes o problema de gasto duplicado era uma fraqueza do dinheiro digital e se solucionava liquidando todas as transações através de uma entidade central.

A rede bitcoin começou em 2009, baseado em uma implementação de referência publicada por Nakamoto e desde então revisada por muitos outros programadores. A computação distribuída que proporciona segurança e robustez ao bitcoin cresceu exponencialmente, e agora excede a capacidade combinada de processamento dos principais supercomputadores do mundo. O valor de mercado do bitcoin se estima entre 5 e 10 bilhões de dólares americanos, dependendo da taxa de câmbio entre o bitcoin e o dólar. A maior transação processada até o momento pela rede foi de US$ 150 milhões, transmitidos instantaneamente e processados sem nenhuma taxa.

Satoshi Nakamoto se afastou do público em abril de 2011, deixando a responsabilidade pelo desenvolvimento do código e da rede nas mão de um animado grupo de voluntários. A identidade da pessoa ou pessoas por trás do bitcoin ainda é desconhecida. No entanto, nem Satoshi Nakamoto nem qualquer outra pessoa exerce controle sobre o sistema bitcoin, que opera baseado em princípios matemáticos totalmente transparentes. O próprio invento é revolucionário e já gerou nova ciência nos campos da computação distribuída, economia e econometria.

###Uma Solução para um Problema de Computação Distribuída
O invento de Satoshi Nakamoto é também uma solução prática para um problema que até então não estava resolvido em computação distribuída, conhecido como o "Problema dos Generais Bizantinos". Em resumo, o problema consiste em tentar tomar uma decisão através do intercâmbio de informações sobre uma rede pouco confiável e potencialmente comprometido. A solução de Satoshi Nakamoto, que utiliza o conceito de prova de trabalho para alcançar o consenso sem uma autoridade central confiável, representa um enorme avanço na ciência de computação distribuída e possui amplas aplicações além de moedas. Pode ser usado para alcançar consenso em redes descentralizadas para provar a honestidade de eleições, loterias, registros de bens, cartórios digitais e mais.


![](https://github.com/aantonop/bitcoinbook/blob/develop/images/msbt_0101.png)
Figure 1. The Multibit bitcoin client Welcome screen

![](https://github.com/aantonop/bitcoinbook/blob/develop/images/msbt_0102.png)
Figure 2. Alice’s new bitcoin address, in the Request tab of the Multibit client

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0103.png)
Figure 3. ZeroBlock, a bitcoin market-rate application for Android and iOS

![](https://github.com/aantonop/bitcoinbook/raw/develop/images/msbt_0104.png)
Figure 4. Blockchain mobile wallet’s bitcoin send screen

