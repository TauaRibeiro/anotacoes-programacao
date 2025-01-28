# HTML

## O que é HTML

* Hyper Text Markup Languange, ou linguagem de marcação de hiper texto é uma linguagem amplamente usada em sites para definir a posição de textos, imagens e ou vídeos.
* A linguagem faz isso através da utilização de tags que demarcam onde inicia e onde termina determinado trecho.
* A extensão utilizada para indicar arquivos desse tipo é a `.html`.

  ### OBS

  * A extensão `.htm` também é usada para indicar um arquivo HTML, mas a mais utilizada é a `.html`.

## Estrutura geral das tags do HTML

* As tags do HTML são escritas a partir de um nome que fica entre os caracteres `<` e `>`, quando é formado somente por esses elementos geralmente significa que o início de um trecho.
* Para indicar um fechamento de uma tag é colocado o caractere `/` no início do nome para indicar que é um fechameno.

  ### Exemplo

    ~~~~HTML
    <html>

    </html>
    ~~~~

* Neste exemplo a tag `<html>` indica o início do campo enquanto a versão com a `/` (`</html>`) indica o fechamento.

## Tags do HTML
  
* ### NOTA IMPORTANTE

  * As tags que serão mostardas não são todas as que existem no HTML, as tags 

* ### `<h1>`...`<h6>`, `</h1>` ... `</h6>`
  * Essas tags representam o cabeçalho da página, os números seguidos pela letra h indica a prioridade da tag.
  
  * Ou seja, a tag `<h1>` tem a maior prioridade dentre elas, enquanto a tag `<h6>` tem a menor prioridade
  
  * Outra coisa é que essas tags, sem formatação, tem tamanhos de fontes diferentes, tendo a tag `<h1>` a maior formatação dentre as 6, enquanto a `<h6>` tem a menor

  #### EXEMPLO  `<h1>`...`<h6>`, `</h1>` ... `</h6>`
  
    ~~~~HTML
    <h1>TESTE</h1>
    <h2>TESTE</h2>
    <h3>TESTE</h3>
    <h4>TESTE</h4>
    <h5>TESTE</h5>
    <h6>TESTE</h6>
    ~~~~

  #### RESULTADO  `<h1>`...`<h6>`, `</h1>` ... `</h6>`

    <h1>TESTE</h1>
    <h2>TESTE</h2>
    <h3>TESTE</h3>
    <h4>TESTE</h4>
    <h5>TESTE</h5>
    <h6>TESTE</h6>

* ### `<p>`, `</p>`

  * Indica um parágrafo
  
  #### EXEMPLO `<p>`, `</p>`
  
  ~~~~HTML
  <p>
    Exemplo de parágrafo
  </p>
  ~~~~

* ### `<i>`, `</i>`

  * Aplica a formatação *itálico* no texto

  #### EXEMPLO `<i>`, `</i>`

  ~~~~HTML
  <i>Texto em itálico</i>
  ~~~~

  #### RESULTADO `<i>`, `</i>`
  <i>Texto em itálico</i>

* ### `<b>`, `</b>`

  * Aplica a formatação **negrito** no texto

  #### EXEMPLO `<b>`, `</b>`

  ~~~~HTML
  <b>Texto em negrito</b>
  ~~~~

  #### RESULTADO `<b>`, `</b>`

  <b>Texto em negrito</b>  
  

* ### `<a>`, `</a>`

  * Indica que o texto é um hyperlink

  * A tag possuí o parâmetro `href`, que indica o link referecidado pelo texto

  #### EXEMPLO `<a>`, `</a>`

  ~~~~HTML
  Link para vídeo explicando sobre o funcionamento desse parâmetro: <a href= "https://www.youtube.com/watch?v=dQw4w9WgXcQ">Esse texto é um link</a>
  ~~~~

  #### RESULTADO `<a>`, `</a>`
  
  Link para vídeo explicando sobre o funcionamento desse parâmetro: <a href= "https://www.youtube.com/watch?v=dQw4w9WgXcQ">Esse texto é um link</a>

* ### `<img>`
  
  * Essa tag indica uma imagem no documento

  #### ATRIBUTOS DA TAG `<img>`
  
  PARÂMETRO|DESCRIÇÃO
  :---------:|:---------:
  src| Indica a fonte da imagem
  alt| Indica um texto que será exibido quando a imagem não carregar
  width| Indica quantos pixels de comprimento a imagem terá
  height| Indica quantos pixels de altura a imagem terá

  #### EXEMPLO `<img>`
  
  ~~~~HTML
  <img src="https://stickers.pw/wp-content/uploads/2024/09/whats_stickers_featured_memes_brazil-min.png" alt= "Um texto que será exibido quando a imagem não carregar" width= 200 height= 160>

  ~~~~

  #### RESULTADO `<img>`
   <img src="https://stickers.pw/wp-content/uploads/2024/09/whats_stickers_featured_memes_brazil-min.png" alt= "Um texto que será exibido quando a imagem não carregar" width= 200 height= 160>

* ### `<!DOCTYPE>`

  * Indica o tipo de documento que o neavegador irá ler.


* ### `<html>`, `</html>`

  * Indica a região do código HTML.

  * Possui um parâmetro chamado `lang=` que indica a linguagem do documento (por exemplo,"en" será para textos em inglês e "pt-br" será para textos em português brasileiro).

  #### EXEMPLO `<html>`, `</html>`
  ~~~~HTML
  <html lang= "pt-br">
  </html>
  ~~~~

* ### `<head>`, `</head>`

  * Parte do documento HTML que contém as configurações de um site.

  * Essas configurações não são visíveis para o usuário.

* ### `<body>`, `</body>`

  * Parte do documento HTML que indica onde vai ficar o conteúdo do site.

* ### `<meta>`
  
  * Tag usada para definir as configurações de metadados de um site.
  
  * #### atributos DA TAG `<meta>`
  
    ##### `charset`

    * Indica a codificação/tipo de caracteres que serão usados no documento.

    * O atributo que normalmente utilizado é o "UTF-8"

    ##### `name`, `content`

    * O parâmetro `name` indica o nome de um metadado, enquanto `content` indica o seu conteúdo.

    valores `name`|DESCRIÇÃO
    :----------:|:-------:
    `viewport`| Configura a visualização da página
    `keywords`|Configura as palavras chaves que serão utilizadas pelo neavegador
    `author`|Configura nome o autor do documento
    `descripition`|Configura a descrição da pagina

* ### `<title>`, `</title>`
  
  * Indica o título da página

* ### `<hr>`
  
  * Cria uma linha horizontal
  
  #### EXEMPLO `<hr>`:
  ~~~~HTML
  <hr>
  ~~~~

  #### RESULTADO `<hr>`
  <hr>

* ### `<br>`
  
  *  Realiza uma quebra de linha

* ### `<!-- -->`

  * Indica um comentário e portanto não será lido pelo programa

* ### TABLES

  * No HTML é possível criar tabelas com seus devidos cabeçalhos e conteúdos dentro das tags `<table>` e `</table>`.

  * Para definir o a seção do cabeçalho é utilizado as `<thead>` e `</thead>`, enquanto o cabeçalho em si é definido pelas tags `<th>` e `</th>`

  * Já pra a seção do conteúdo é utilizado as tags `<tbody>` e `</tbody>`, e dentro é utilizado as tags `<tr>` e `</tr>` para definir as linhas dessas tabelas, e por fim é utilizado as tags `<td>` e `</td>` para definir os conteúdos em si.

  #### EXEMPLO TABLE

  ~~~~HTML
  <table>
      <thead>
          <th>Nome</th>
          <th>Cidade</th>
          <th>idade</th>
      </thead>
      <tbody>
          <!-- Linha 1 -->
          <tr>
              <td>Tauã</td>
              <td>cidade 1</td>
              <td>19</td>
          </tr>
          <!-- Linha 2 -->
          <tr>
              <td>Teste</td>
              <td>cidade teste</td>
              <td>20</td>
          </tr>
      </tbody>
  </table>
  ~~~~

  #### RESULTADO TABLE

    <table>
      <thead>
          <th>Nome</th>
          <th>Cidade</th>
          <th>idade</th>
      </thead>
      <tbody>
          <tr>
              <td>Tauã</td>
              <td>cidade 1</td>
              <td>19</td>
          </tr>
          <tr>
              <td>Teste</td>
              <td>cidade teste</td>
              <td>20</td>
          </tr>
      </tbody>
  </table>

  * Note que o primeiro item de cada linha se refere ao primeiro item do cabeçalho da tabela e o segundo item da linha ao segundo item do cabeçalho.

* ### FORMULÁRIOS
  
  * Um formulário em HTML é uma forma de o usuário interagir e inserir os dados na página, e além disso é possível definir o arquivo ao qual será enviado esse formulário.

  #### TAGS PARA CONSTRUIR OS FORMULÁRIOS
  
  ##### `<form>`, `</form>` 
    * É utilizado para definir a seção onde vai ficar as tags dos formulários.

    * Nelas possui 2 atributos importante que são `action=`, que define o arquivo ao qual será enviado os dados, e o `method=` que define o método do formulário.

    * Esse atributo `method=` aceita os seguinte valores:

    VALORES|UTILIDADE
    :-----:|:------:
    "post"| Define que os dados desse formulário serão enviados para o arquivo definido pelo `action= `

  ##### `<label>`, `</label>`
    * É utilizado para nomear os campos em que o usuário irá digitar, ajudando o própio a ter noção de quais dados colocar.

  #####  `<input>`, `</input>`
    * É utilizado para definir os campos onde o usuário poderá digitar os dados.

    * Essa tag possui dois atributos principais, que são `placeholder=` que define um texto temporário para o campo quando está vazio, e `type=` que define o tipo de input que usuário irá digitar.

    * Esse atributo `type=` aceita alguns valores que são os seguintes:

    VALOR|UTILIDADE
    :---:|:---------:
    "text" | Utilizado para textos no geral
    "email" | Utilizado para email
    "date" | Utilizado para inserir datas
    "password" | Utilizado para inserir senhas, ocultando o que é digitado pelo usuário
    "submit" | Cria um botão de envio

    ~~~~HTML
      <form action="form.php" method="post">
        <div> 
             <label>Primeiro nome</label>
             <input type="text" placeholder="Digite seu primeiro nome">
        </div>
        <br>
        <div>
            <label>Segundo Nome</label>
            <input type="text">
        </div>
        <br>
        <div>
            <label>email</label>
            <input type="email">
        </div>
        <br>
        <div>
            <label>Data nascimento</label>
            <input type="date">
        </div>
        <br>
        <div>
            <label>Senha</label>
            <input type="password">
        </div>
      </form>
    ~~~~

    <form>
      <div> 
            <label>Primeiro nome</label>
            <input type="text" placeholder="Digite seu primeiro nome">
      </div>
      <br>
      <div>
          <label>Segundo Nome</label>
          <input type="text">
      </div>
      <br>
      <div>
          <label>email</label>
          <input type="email">
      </div>
      <br>
      <div>
          <label>Data nascimento</label>
          <input type="date">
      </div>
      <br>
      <div>
          <label>Senha</label>
          <input type="password">
      </div>
      <br>
      <div>
        <input type="submit">
      </div>
    </form>

  ##### `<select>`, `</select>`
   * É utilizado para criar uma seção que permite o usuário escolher uma opção.

   * Para criar essas opções é utilizado as tags `<option>` e `</option>`, onde nas quais possuem um atribuito chamado `value=` que define o valor que aquela opção terá

   ~~~~HTML
  <form>
    <div>
        <label>Gênero</label>
        <select>
            <option value="valor 1">Opção 1</option>
            <option value="valor 2">Opção 2</option>
        </select>
    </div>
  </form>
   ~~~~ 

    <form>
    <div>
        <label>Gênero</label>
        <select>
            <option value="valor 1">Opção 1</option>
            <option value="valor 2">Opção 2</option>
        </select>
    </div>
  </form>
    


* ### `<link>`
  
  * Tag utilizada para definir a relação do documento com fontes externas, o ícone e o estilo da página.

  * Essa tag possui alguns atributos, sendo um deles o `rel` que define o tipo de relação do documento e o que vai ser referenciado através do `href`.

  #### EXEMPLO `<link>`

  ~~~~HTML
  <!-- Define o ícone da página-->
  <link rel= "shortcut icon" ref= "icon.ico">
  ~~~~

  #### VALORES DO `rel`

  ATRIBUTO|DESCRIÇÃO
  :-------:|:--------:
  "shrotcut icon"|Define o ícone do atalho da página
  "preconnect"|Faz uma conexão antes de exibir a página, agindo de forma analoga ao `import` do python
  "stylesheet"|Faz uma conexão com um arquivo CSS

* ### `<div>`, `</div>`

  * Serve para dividir certos trechos do script HTML em um bloco.
  
  #### EXEMPLO `<div>`, `</div>`
  ~~~~HTML
  <div class>
      <h1>Olá, mundo!</h1>
      <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Quod ducimus quo veritatis velit similique reprehenderit quibusdam saepe cum ipsa dicta assumenda harum voluptates optio fuga, magnam atque exercitationem dignissimos deleniti.
      </p>
  </div>

  <p>Esse é um parâgrafo fora da divisão</p>
  ~~~~

* ### `<button>`, `</button>`
  * Cria um botão na página

  #### EXEMPLO `<button>`, `</button>`

  ~~~~html
  <button>Isso é um botão</button>
  ~~~~

  #### RESULTADO `<button>`, `</button>`

  <button>Isso é um botão</button>

* ### `<blockquote>`, `</blockquote>`
  
  * Serve para indentificar citações no documento HTML.

  * Possui um atributo chamado cite, no qual indica a origem da citação.

  #### EXEMPLO `<blockquote>`, `</blockquote>`

  ~~~~HTML
  <blockquote cite="https://google.com">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quasi, repudiandae?</blockquote>
  ~~~~ 

  #### RESULTADO `<blockquote>`, `</blockquote>`

  <blockquote cite="https://google.com">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quasi, repudiandae?</blockquote>


* ### `<abbr>`, `</abbr>`

  * Serve para indicar abreviações no HTML.

  * Possui um atributo chamado `title=` que serve para indicar o que significa a abreviação.

  #### EXEMPLO `<abbr>`, `</abbr>`
  
  ~~~~HTML
  <p>Eu amo a <abbr title="World wide web"> WWW </abbr></p>
  ~~~~

  #### RESULTADO `<abbr>`, `</abbr>` 



* ### LISTAS HTML
  * Para definir uma lista no HTML são utilizadas as seguintes tags:
  
  **<ul>, </ul>** -> Indica uma lista de elementos desorganizadas, ou seja, que não numeradas.
  **<ol>, </ol>** -> Indica uma lista de elementos organizados, ou seja, numerados por algarismos romanos e números ou por letra. O atributo `type` define o tipo de organização.
  **<li>, </li>** -> Se refere ao item da lista.

  #### EXEMPLO LISTAS HTML
  
  ~~~~HTML
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>

  <hr>

  <ol>
    <li>Item 1</li>
    <li>
      item 2
      <ul>
        <li>sub-item 1</li>
        <li>sub-item 2</li>
      </ul>
    </li>
    <li>item 3</li>
  </ol>
  ~~~~

  #### RESULTADO LISTAS HTML
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>

  <hr>

  <ol>
    <li>Item 1</li>
    <li>
      item 2
      <ul>
        <li>sub-item 1</li>
        <li>sub-item 2</li>
      </ul>
    </li>
    <li>item 3</li>
  </ol>

* ### ATRIBUTOS `<class= >` e `<id= >`

  * Ambos os dois parâmetros servem para identificar uma ou mais tags no HTML, o que permite aplicar um estilo esclusivo usando o CSS nessas tags específicas.

  * Elas podem ser referenciadas usando no inicio de seus nomes `.` no caso das classes e `#` no caso das ids.

  * Todas as tags do HTML tem esse atributo.

  #### EXEMPLO `<class= >` e `<id= >`

  ~~~~HTML
  <h1 id= "primeiro-cabecalho">Cabeçalho 1</h1>
  <h1 class= "segundo-cabecalho">Cabeçalho 2</h1>
  ~~~~

  * Uma deve ser ter em mente a respeito dessas tags é a de que a `id=` serve para indentificar um único elemento, enquanto a `class=` serve para vários.


## Semâtica HTML

  * É uma forma de estruturação e organização de um script HTML que permite não só a fácil manuteção do script mais também para otimizar os motores de buscas e aumentar a compatibilidade com outros navegadores.

  * As tags utilizadas nesse tipo de estruturação são:

  ### `<header>`, `</header>`

    * Define o cabeçalho do página ou seção. Contendo no geral logotipos, menus de navegação e o título da página

  ### `<nav>`, `</nav>`

    * Define blocos usados para navegação entre menus principais e rodapés. Contém links internos e externos de forma organizada.

  ### `<footer>`, `</footer>`

    * Define o rodapé da página. Onde fica informações de contato, referências e de direitos autorais.

  ###  `<article>`, `</article>`

    * Define um bloco de conteúdo independente e autossuficiente, como artigos de blogs, noticias e postagens de foruns.

  ### `<section>`, `</section>`

    * Usada para definir seções dentro de um documento, como capítulos, grupos de conteúdo relacionadado ou partes de uma página com conteúdo específico.

  ### `<aside>`. `</aside>`

    * Usada para definir conteúdos que fogem da temática do conteúdo principal, como barras laterais, e conteúdos complementares.

  ### `<main>`, `</main>`

    * Destina-se ao conteúdo principal de uma página, ajudando a destacar a parte mais importante.

  ### EXEMPLO UTILIZANDO A SEMÂNTICA

  ~~~~HTML
  <!DOCTYPE html>
  <html lang="pt-br">
  <head>
      <meta charset="UTF-8">
      <title>Meu Blog de Programação</title>
  </head>
  <body>

      <header>
          <h1>Blog de Programação</h1>
          <nav>...</nav>
      </header>
      
      <main>
          <section>
              <h2>HTML Semântico</h2>
              <article>...</article>
              <article>...</article>
          </section>
          <aside>...</aside>
      </main>
      
      <footer>
          <p>2024 Blog de Programação.</p>
      </footer>

  </body>
  </html>
  ~~~~

## Símbolos especiais no HTML
  
  TAG DO SÍMBOLO|SÍMBOLO
  :-------------:|:-----------:
  `&gt;`|>
  `&lt;`|<
  `&reg;`|&reg;
  `&copy;`|&copy;
  `&trade;`|&trade;
  `&euro;`|&euro;
  `&pound;`|&pound;
  `&yen;`|&yen;
  `&cent;`|&cent;
  `&delta;`|&delta;
  `&Delta;`|&Delta;
  `&uparrow;`|&uparrow;
  `&leftarrow;`|&leftarrow;
  `&rightarrow;`|&rightarrow;
  `&downarrow;`|&downarrow;
