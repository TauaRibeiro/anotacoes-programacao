# HTML

## O que é HTML

* Hyper Text Markup Languange, ou linguagem de marcação de hiper texto é uma linguagem amplamente usada em sites para definir a posição de textos, imagens e ou vídeos.
* A linguagem faz isso através da utilização de tags que demarcam onde inicia e onde termina determinado trecho.
* A extensão utilizada para indicar arquivos desse tipo é a `.html`.

  ## OBS

  * A extensão `.htm` também é usada para indicar um arquivo HTML, mas a mais utilizada é a `.html`.

## Estrutura geral das tags do HTML

* As tags do HTML são escritas a partir de um nome que fica entre os caracteres `<` e `>`, quando é formado somente por esses elementos geralmente significa que o início de um trecho.
* Para indicar um fechamento de uma tag é colocado o caractere `/` no início do nome para indicar que é um fechameno.

  ## Exemplo

    ~~~~HTML
    <html>

    </html>
    ~~~~

* Neste exemplo a tag `<html>` indica o início do campo enquanto a versão com a `/` (`</html>`) indica o fechamento.

## Tags do HTML
  
* ## NOTA IMPORTANTE

  * As tags que serão mostardas não são todas as que existem no HTML, as tags 

* ### `<h1>`, `<h2>`, ..., `<h6>`
  * Essas tags representam o título do texto a ser inserido.
  * Sendo que essas tags, sem formatação, tem tamanhos de fontes diferentes, tendo a tag `<h1>` a maior formatação dentre as 6, enquanto a `<h6>` tem a menor.

  ## EXEMPLO
  
    ~~~~HTML
    <h1>TESTE</h1>
    <h2>TESTE</h2>
    <h3>TESTE</h3>
    <h4>TESTE</h4>
    <h5>TESTE</h5>
    <h6>TESTE</h6>
    ~~~~

  ## RESULTADO
    <h1>TESTE</h1>
    <h2>TESTE</h2>
    <h3>TESTE</h3>
    <h4>TESTE</h4>
    <h5>TESTE</h5>
    <h6>TESTE</h6>

* ## `<p>`, `<i>`, `<b>`, `<a>`, `<img>`
  
  TAG|FUNÇÃO
  :-----:|:--------:
  `<p>`|Indica um parágrafo|
  `<i>`|Indica um texto em itálico
  `<b>`|Indica um texto em negrito
  `<a>`|Indica um hyperlink
  `<img>`|Indica uma imagem

  ## EXEMPLO

  ~~~~HTML
  <p>
    Esse é um parágrafo.<i> E esse é um texto em itálico</i>
  </p>
  <b>Texto em negrito</b>
  <p>Hyperlink: <a href= "https://www.youtube.com/watch?v=dQw4w9WgXcQ">Esse texto é um link</a></p>
  <p>Imagem:</p> 
  <img src="https://stickers.pw/wp-content/uploads/2024/09/whats_stickers_featured_memes_brazil-min.png" alt= "Um texto que será exibido quando a imagem não carregar" width= 200 height= 160>

  ~~~~

  ## RESULTADO
  <p>
    Esse é um parágrafo.<i> E esse é um texto em itálico</i>
  </p>
  <b>Texto em negrito</b>
  <p>Hyperlink: <a href= "https://www.youtube.com/watch?v=dQw4w9WgXcQ">Esse texto é um link</a></p>
  <p>Imagem:</p> 
  <img src="https://stickers.pw/wp-content/uploads/2024/09/whats_stickers_featured_memes_brazil-min.png" alt= "Um texto que será exibido quando a imagem não carregar" width= 200 height= 160></img>
  