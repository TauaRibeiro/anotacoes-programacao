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

  #### PARÂMETROS DA TAG `<img>`
  
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
  
  * #### PARÂMETROS DA TAG `<meta>`
  
    ##### `charset`

    * Indica a codificação/tipo de caracteres que serão usados no documento.

    * O atributo que normalmente utilizado é o "UTF-8"

    ##### `name`, `content`

    * O parâmetro `name` indica o nome de um metadado, enquanto `content` indica o seu conteúdo.

    ATRIBUTOS `name`|DESCRIÇÃO
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

* ### `<link>`
  
  * Tag utilizada para definir a relação do documento com fontes externas, o ícone e o estilo da página.

  * Essa tag possui alguns parâmetros, sendo um deles o `rel` que define o tipo de relação do documento e o que vai ser referenciado através do `href`.

  #### EXEMPLO `<link>`

  ~~~~HTML
  <!-- Define o ícone da página-->
  <link rel= "shortcut icon" ref= "icon.ico">
  ~~~~

  #### ATRIBUTOS DO `rel`

  ATRIBUTO|DESCRIÇÃO
  :-------:|:--------:
  "shrotcut icon"|Define o ícone do atalho da página

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
