# Escrevendo o livro Bitcoin

A primeira vez que ouvi falar em bitcoin foi em meados de 2011. Minha reação imediata foi mais ou menos essa "Pfft! Dinheiro de nerd!" e eu ignorei-o por mais seis meses, sem compreender a sua importância. Esta é uma reação que eu tenho observado com frequência entre muitas das pessoas mais inteligentes que conheço, o que me dá algum consolo. A segunda vez que me deparei com bitcoin, em uma lista de discussão, eu decidi ler o seu "manual de instruções" oficial, a _white page_, escrito pelo seu criador, Satoshi Nakamoto, para ver do que se tratava. Ainda me lembro do momento em que eu terminei de ler essas nove páginas, quando eu percebi que bitcoin não era simplesmente uma moeda digital, mas uma rede de confiança que também poderia servir de base para aplicações muito mais avançadas do que apenas moedas. Após constatar que o bitcoin não é dinheiro, mas sim uma rede de confiança descentralizada, comecei uma viagem de quatro meses para devorar cada pedaço de informação que eu poderia encontrar sobre o assunto. Eu me tornei obcecado e encantado, gastando 12 ou mais horas por dia colado ao monitor, lendo, escrevendo, codificando e aprendendo o máximo que pude. Após pular muitas refeições, saí desse período de obsessão 20 quilos mais leve e determinado a dedicar-me a trabalhar com bitcoin.

Dois anos depois, depois de criar várias pequenas startups para explorar serviços e produtos relacionas ao bitcoin, eu decidi que estava na hora de escrever meu primeiro livro. O bitcoin foi um tópico que me levou a um frenesi de criatividade e consumiu meus pensamentos; ele esa a tecnologia mais empolgante que eu já havia encontrado desde que conheci a Internet. Estava na hora de compartilhar com uma audiência mais ampla minha paixão sobre essa incrível tecnologia.

## Público Alvo

Esse livro foi escrito principalmente para programadores. Se você sabe alguma linguagem de programação, esse livro irá ensiná-lo como as moedas criptográficas funcionam, como utilizá-las e como desenvolver softwares que trabalhem com elas. Os primeiros capítulos também são adequados como uma introdução aprofundada ao bitcoin para não-programadores, que queiram entender o funcionamento interno do bitcoin e das criptomoedas.

## Por Que a Capa do Livro Tem Insetos?

A formiga cortadeira é uma espécie que possui um comportamente altamente complexo em um super-organismo de colônia, mas cada formiga individualmente opera sob um conjunto de regras simples dirigidas por interação social e pela troca de aromas químicos (feromônios). De acordo com a Wikipedia: "Depois dos humanos, as formigas cortadeiras formam as maiores e maix complexas sociedades animais do planeta Terra". Na verdade, as formigas cortadeiras não comem as folhas, mas as utilizam para cultivar um fungo, que é a fonte central de comida da colônia. Você compreendeu isso? Essas formigas estão fazendo agricultura!

Embora as formigas formem uma sociedade baseada em castas e possuam uma rainha para produzir a prole, não há uma autoridade central ou um líder na colônia de formigas. O comportamento altamente inteligente e sofisticado exibido pela colônia composta por milhões de membros é uma propriedade que surge a partir da interação dos indivíduos em uma rede social.

A natureza demonstra que sistemas descentralizados podem ser versáteis e podem uma complexidade que evolui, além de uma sofisticação incrível, tudo isso sem a necessidade de uma autordade central, hierarquia ou partes complexas.

O Bitcoin é uma rede de confiança descentralizada altamente sofisticada que pode suportar uma grande diversidade de processos financeiros, No entanto, cada nodo na rede bitcoin segue algums poucas regras matemáticas simples. A interação entre os múltiplos nodos, e não uma complexidade inerente ou confiança em um nodo único, é o que leva à emergência de um comportamento sofisticado. Como uma colônia de formigas, a rede bitcoin é uma rede versátil de nodos simples, seguindo regras simples, que juntos podem fazer coisas incríveis, sem depender de uma coordenação central.

## Convenções Usadas Neste Livro

As seguintes convenções tipográficas são usadas neste livro:

<dl>
<dt>
<em>Itálico</em>
</dt>
<dd>
Indica novos termos, URLs, endereços de e-mail, nomes e extensões de arquivos.
</dd>
<dt>
Constant width
</dt>
<dd>
Usada para listagem de programas, assim como dentro de parágrafos para se referir a elementos de programas como variáveis e nomes de funções, banco de dados, tipos de dados, variáveis de ambiente, declarações e palavras-chave.
</dd>
<dt>
Constant width em negrito
</dt>
<dd>
Mostra comandos ou outro texto que deveria ser digitado literalmente pelo usuário.
</dd>
<dt>Constant width em itálico</dt>
<dd>
Mostra texto que deveria ser substituído por valores fornecidos pelo usuário, ou valores determinados pelo contexto.
</dd>
</dl>

> Esse ícone é usado em dicas, sugestões ou notas em geral.

> Esse ícone indica uma mensagem de aviso ou cuidado.

## Exemplos de códigos

Os exemplos são ilustrados em Python, C++ e usando uma linha de comando de um sistema operacional do tipo Unix, como Linux, ou Mac OS X. Todos os snippets de códigos estão disponíveis no repositório GitHub no subdiretório code do repositório principal. Você pode fazer um fork do código do livro, testar exemplos de códigos ou enviar correções via GitHub.

Todos os snippets de códigos podem ser replicados na maioria dos sistemas operacionais com uma instalação mínima dos compiladores e interpretadores das linguagens correspondentes. Quando necessário, nós providenciaremos as instruções básicas da instalação e exemplos passo-a-passo do output dessas instruções.

Alguns dos snippets de códigos e do output do código foram reformatados para a impressão. Em todos esses casos, as linhas foram divididas por uma barra invertida ( \ ), seguida por um caractere de nova linha. Ao transcrever os exemplos, remova estes dois caracteres e una as linhas novamente, obtendo resultados idênticos aos mostrados no exemplo.

Todos os snippets de códigos usam valores e cálculos reais quando possível, de maneira que você possa construir de exemplo a exemplo e observar os mesmo resultados em qualquer código que você escrever para calcular os mesmos valores. Por exemplo, as chaves privadas e seus endereços e chaves públicas correspondentes são reais. As amostras de transação, blocos e referências à blockchain foram realmente introduzidas na  blockchain do bitcoin e fazem parte do ledger público, para que você possa revisá-las em qualquer sistema bitcoin.

## Usando Exemplos de Códigos

Esse livro foi feito para ajudá-lo a fazer seu trabalho. Em geral, se um exemplo de código é oferecido com esse livro, você pode utilizá-lo em seus programas e documentação. Você não precisa entrar em contato conosco para pedir permissão, a menor que você esteja reproduzindo uma porção significativa do código. Por exemplo, você não precisa pedir permissão para escrever um programa que utiliza vários pedaços de código deste livro. No entanto, você precisa de permissão para vender ou distribuir um CD-ROM de exemplos dos livros O’Reilly. Para responder uma questão citando esse livro e citando um exemplo de código, você não precisa de permissão. Para incorporar uma porção significativa de exemplos de códigos deste livro na documentação do seu produto, você precisa de permissão.

Nós apreciamos, mas não exigimos, atribuição de créditos.  Uma atribuição geralmente inclui o título, autor, editor e ISBN. Por exemplo: “Mastering Bitcoin por Andreas M. Antonopoulos (O’Reilly). Copyright 2015 Andreas M. Antonopoulos, 978-1-449-37404-4.”


Algumas edições deste livro são oferecidas sob uma licença open source, como CC-BY-NC (creativecommons.org), neste caso, sendo aplicados os termos deste licença específica.

Se você acredita que o seu uso dos exemplos de código não se encaixam na categoria de fair use ou nas permissões citadas acima, sinta-se livre para entrar em contato conosco em  <permissions@oreilly.com>.

## Safari® Books Online

> Safari Books Online é uma biblioteca digital sob demanda que fornece conteúdo especializado tanto em livro quando em vídeo dos principais autores em tecnologia e negócios.

Profissionais de tecnologia, desenvolvedores de software, web designers e profissionais de negócios e áreas de criação usam o Safari Books Online como sua fonte primária de pesquisa, solução de problemas, aprendizado e treinamento certificado.

A Safari Books Online oferece uma variedade de produtos e condições de pagamento para organizações, agências do governo e pessoas físicas. Os assinantes tem acesso a milhares de livros, vídeos de treinamento e manuscritos liberados antes da publicação em um banco de dados pesquisável, que inclui editoras como O’Reilly Media, Prentice Hall Professional, Addison-Wesley Professional, Microsoft Press, Sams, Que, Peachpit Press, Focal Press, Cisco Press, John Wiley & Sons, Syngress, Morgan Kaufmann, IBM Redbooks, Packt, Adobe Press, FT Press, Apress, Manning, New Riders, McGraw-Hill, Jones & Bartlett, Course Technology e muitas outras. Para maiores informações sobre a Safari Books Online, visite-nos online.
