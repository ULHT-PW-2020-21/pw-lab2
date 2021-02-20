**UNIVERSIDADE LUSÓFONA DE HUMANIDADES E TECNOLOGIAS**

# Programação Web - Laboratório 2: Explorando o HTML com o meu primeiro website  

**OBJECTIVO**: Nesta ficha criará um primeiro website que ficará disponível na nuvem. Irá aplicar todos os conceitos aprendidos na aula sobre HTML desta semana.

**PRÉ-REQUISITOS**: 
* Instale o VS Code para editar o código HTML de forma fácil. Senão, pode sempre usar o Notepad++. 
* Deverá ter feito o [lab1](https://github.com/ULHT-PW-2020-21/pw-lab1).

# 1. Estruturação

1. Crie uma pasta `projeto` 
1. Crie a pasta `lab1` que deverá conter o seu `lab1` criado na semana passada.
   1. crie um ficheiro `lab1.html` que:
       * tenha como título "lab1" (usando a etiqueta `<title>` no `<<head>`)
       * tenha um cabeçalho `<h1>` a dizer "Lab1: Conhecer a Internet com a minha primeira página Web" 
       * tenha, numa lista, links para as duas páginas desse laboratório: `progweb.html` e  `report.html`.

1. Crie a pasta `lab2`
   1. crie um ficheiro `lab2.html` que:
       * tenha como título "lab2" (etiqueta `<title>`)
       * tenha um cabeçalho `<h1>` a dizer "Lab2: Explorando o HTML com o meu primeiro website" 
       * deverá ter, numa lista, links para cada uma das páginas que irá criar neste laboratório.

1. crie dentro da pasta `projeto`o ficheiro `index.html` que:
   * tenha como título "Laboratórios Programação Web" (etiqueta `<title>`)
   * tenha um cabeçalho `<h1>` a dizer "Laboratórios Programação Web" 
   * deverá ter, numa lista, links para os ficheiros `lab1.html` e `lab2.html` (que estão nos seus respectivas pastas, pelo que deverá incluir no caminho o nome da pasta), usando o título de cada laboratório.

1. Os ficheiros `lab1.html` e `lab2.html` deverão ter um link para voltar para a landingpage do seu projeto, `index.html`.

A estrutura final deverá ser como em baixo (com mais imagens na pasta img):
```
projeto
+-- index.html
+-- lab1
|   +-- lab1.html
|   +-- index.html
|   +-- report.html
|   +-- img
    |   +-- wordcloud.png
+-- lab2
|   +-- lab2.html
|   +-- ... (ficheiros a criar ao longo deste laboratório)
```


## Landing page


## Lab 2
Crie uma pasta `lab2` com o ficheiro `index.html` que deverá satisfazer os seguintes requisitos:
1. deverá ter como título laboratório 2. 
1. Deverá especificar esse título no `body`, numa etiqueta `h1`.
2. deverá listar os exercícios realizados, com links para os respetivas páginas HTML.
3. deverá ter um link para voltar para a landingpage da sua aplicação no Heroku.

![](wordcloud.png)

Uma vez editado, abra o ficheiro `index.html` com um Browser para ver se visualiza corretamente a imagem em baixo.
![](index-renderizado.png)

## Criação de repositório GitHub
Crie um repositório no GitHub `pw-lab1`, e faça push da pasta `lab1`.

## Alojamento no Heroku
Crie uma conta no Heroku. Sincronize o GitHub com o Heroku, de forma a colocar disponível na cloud a pasta `lab1` com seus conteúdos. 
De forma a conseguirem o alojamento na cloud com sucesso devem seguir os seguintes passos:
* Adicionar dois ficheiros na diretoria `root` da pasta
* * index.php
* * * Com o seguinte conteúdo: `<?php include_once("index.html")  ?>`
* * composer.json
* * * Com o seguinte conteúdo: `{}`
* Criar conta no Heroku - https://signup.heroku.com/login 
* Criar uma aplicação, atribuindo-lhe um nome
* Entrar nas definições da aplicação criada, e clicar na tab `Deploy`
* Na secção de `Deploy Method` devem conectar a aplicação com o Github
* Navegando até ao fim da página, até à secção `Manual deploy`, devem escolher o branch indicado do repositório e clicar em `Deploy branch`
* Um vez realizado com sucesso, devem clicar no botão `Open app` no topo da página, e visualizar a página HTML 




# 2. Conhecer a Internet

Vamos explorar alguns aspectos da Internet, a rede de routers e cabos que suporta Web. 

## Endereços IP
1. Obtenha informação sobre o IP do seu PC e seu telemóvel.
    * obtenha e anote o endereço IP do seu computador. Pode obter isso de várias formas. A mais simples é perguntar no Google "what is my ip". Anote onde está localizado, usando por exemplo a ferramenta https://whatismyipaddress.com/ip-lookup. guarde uma imagem do mapa que localiza.
    * Obtenha e anote a mesma informação do seu telemóvel, se tiver dados móveis.
1. Obtenha informação sobre o IP do servidor Heroku onde está a sua app.
    * Obtenha e anote o endereço IP do servidor Web onde está alojada a sua página no Heroku
    * anote onde este está localizado, usando a ferramenta https://whatismyipaddress.com/ip-lookup.  Guarde uma imagem do mapa que a localiza.

## Percurso
Traceroute (comando tracert) é uma ferramenta de diagnóstico que rastreia a rota que os pacotes IP fazem, desde o seu computador até um endereço IP destino/ou URL que especifique. Este identifica os routers pelos quais os pacotes passam até o seu destino, indicando o tempo que demoram por "salto" entre router. 

1. A forma mais clássica é através da linha de comando e escreva tracert e especifique o endereço IP obtido anteriormente:
``> traceroute <endereço IP ou URL sua app>``
1. Use a ferramenta GeoTraceroute, Em https://geotraceroute.com/, para visualizar graficamente por onde passam os pacotes IP, até chegar ao seu servidor Heroku. Escolha como origem (source) Portugal, e como destino o URL do seu site. Registe os saltos, indicando o país, e distância de cada salto. Quando fizer a página, pode procurar na Internet e inserir uma pequena image da bandeira do país. Com a ferramenta de Snip (Tecla Windows + Shift + S) copie a imagem do globo que cubra os saltos dados, e guarde-a como um ficheiro jpg ou png, para inserir também na página report.html.

# 3. Acesso via HTTP à minha página Web

## HTTP

O protocolo de troca de mensagens entre um cliente e um servidor Web é o HTTP. Um Web browser (Chrome, Safari, Firefox, etc) é uma aplicação que corre numa máquina "cliente" (o seu portátil por exemplo) e é capaz de enviar um pedido usando o protocolo HTTP a um servidor Web:
* O cliente pode pedir uma determinada página Web através de uma mensagem HTTP GET. O servidor Web irá responder-lhe a esse pedido, enviando os conteúdos correspondentes. Tipicamente é recebido um ficheiro HTML juntamente com algumas imagens e outros ficheiros auxiliares, sendo o browser capaz de representar visualmente o conteúdo. 
* O cliente pode também enviar ao servidor Web dados que preencheu por exemplo num formulário, através de uma mensagem HTTP POST. 
Esta é a arquitetura cliente-servidor. 

No seu browser, insira o URL da sua página Heroku. Nesse instante será feito enviado ao servidor Web um pedido (a mensagem chama-se mensagem HTTP GET) do conteúdo correspondente a esse URL, que lhe será enviado pelo servidor em modo de resposta. Visualise o código recebido, clicando com o botão direito do rato e selecionando "ver código fonte" (view page source) ou simplesmente premindo Ctrl + U. Verifique o que aparece: é o que escreveu!

## Inspect

Todos os browsers têm uma ferramenta (*browser developer tool*) que permite inspeccionar ficheiros descarregados pelo browser, permitindo analisar uma grande variedade de informação.
USe por exemplo o Chrome para abrir a sua página, e clicando no botão direito do rato, selecione *Inspect*, ou selecione Ctrl+Shift+i.

Selecione a barra network. Clique na janela  do seu browser onde está o URL do seu site e faça novamente Enter: 
* Explique o que aparece. Com a ferramenta de Snip (Tecla Windows + Shift + S) copie a imagem com info dos ficheiros descarregados. 
* Anote quantos ficheiros são descarregados na sequencia de um clique num hiperlink.
* Anote o tipo de ficheiros, timings de espera e de descarga.
* Selecione cada um dos ficheiros descarregados. Anote o que observa, quando seleciona:
   * preview
   * Headers
   * Timing

Faça o mesmo agora para o site da lusófona, mas aqui observando apenas (sem necessidade de anotar, pois a quantidade de informação é muito maior :-)).

# 4. Página Web Report.html

Com base em todas estas observações crie uma nova página HTML, report.html, onde reporte tudo o que observou.
* Utilize etiquetas para estruturar o seu conteúdo, etiquetas de heading (h1, h2, h3, ....), assim como para listar (ul) e enumerar (ol) (pesquise na internet, nna W3Schools, por exemplo https://www.w3schools.com/tags/tag_ul.asp).
* Inclua as imagens recolhidas da mesma forma que fez no index.html. 
* Faça upload para o seu repositório no GitHub, e sincronize com o Heroku. 
* Verifique que ambas as páginas estão operacionais.

A estrutura das pastas deverá ser como em baixo (com mais imagens na pasta img):
```
projeto
+-- lab1
|   +-- index.html
|   +-- report.html
|   +-- img
    |   +-- wordcloud.png
```

# 5. Submissão do Laboratório
No Moodle, submeta o link da sua aplicação antes da sua próxima aula prática, onde este será avaliado. 

Esperamos que tenha gostado de conhecer um pouco do funcionamento da Internet e de ter feito a sua primeira página Web &#127760;!
