# NOTA IMPORTANTE!

* É preciso deixar claro que os conteúdos desse arquivo são anotações minhas que foram adicionadas de acordo com o meu conhecimento sobre o assunto, e não uma documentação oficial de CSS.

* Portanto não tome nada daqui como a verdade absoluta ou que o conteúdo desse arquivo é tudo que precisa saber de CSS. E sim como anotações.

* Caso deseja saber mais afundo sobre o assunto recomendo fazer a própria pesquisa e as próprias anotações, mas é muito bem vindo a utilizar essas anotações como um pequeno guia ou até mesmo uma revisão.

* Outra coisa importante é a de que é recomedável ver sobre HTML antes de prosseguir com essas anotações.


# O que é CSS?

* CSS ou Cascandig Style Sheets é uma liguagem de estilo que permite personalizar elementos de uma página web, deixando-a mias bonita e légivel.

* É possível utilizar o CSS direto do arquivo HTML, mas é uma boa prática colocar os códigos CSS em um arquivo separado uqe tenha como extensão ***.css*** (styles.css é um exemplo de arquivo css).

* Para poder aplicar um arquivo CSS em um arquivo HTML é necessário realizar um link no `<head>` do arquivo HTML da seguinte forma.

~~~~HTML
<link rel="stylesheet" href="./styles.css">
~~~~


# Estrutura básica do CSS

* O CSS segue a seguinte estrutura:

~~~~CSS
body {
    color: red;
}
~~~~

* ## Seletor

    * É colocado anes das chaves, serve para identificar em que parte do arquivo está sendo aplicado essa formatação, no caso do explo acima está sendo aplicado no `<body>` do arquivo HTML.

    * Também é possível colocar um caminho no seletor para que possa ser aplicado em uma parte específica, como pro exemplo:

    ~~~~HTML
    <div id="categoria">
        <p>Categorias</p>
        <ul>
            <li>item</li>
            <li>item</li>
            <li>item</li>
        </ul>
    </div>
    ~~~~
    ~~~~CSS
    #categorias ul li{
        color: red;
    }
    ~~~~

    * Neste exemplo acima, estamos basicamente dizendo que é para aplicar a cor vermelha nos itens da lista desordenada da div categorias. 

    * Uma coisa que é possível notar é que para se referir a div foi utilizado `#categorias` e não o `div`, isso porque div possui um atributo chamado `id=`
    que contem o valor `"categorias"`.

    * A utilização de ids e classes no HTML permitem dizer ao CSS especificadamente de qual elemento estamos falando.

    * Para se referenciar a uma classe no CSS é colocado um `.` antes do nome enquanto para o id é utilizado o `#`.

    * Caso queira aplicar uma propriedade especifica em todos elementos da página é utilizado o símbolo `*`.

* ## Declaração

    * A declaração fica dentro das chaves, ela começa pela proprieda que é o que deseja alterar no elemento, no caso do exemplo acima é a propriedade é a `color`, e depois dos `:` vem o valor da propriedade, por fim finaliza a propriedade com um `;`.

    # Estrutura do elemento de uma página

* Os elementos de uma pagina web tem a seguinte estrutura

<img src= https://www.freecodecamp.org/news/content/images/2021/08/Screen-Shot-2021-08-03-at-1.38.36-AM.png alt= "Estruta de padding dos elementos"></img>

* ## PADDING
    * É um espaçamento entre a borda e o conteúdo em si

* ## BORDER 
    * É a borda do conteúdo.

* ## MARGIN
    * É o espaçamento entre a borda do conteúdo e a página


# Propriedades do CSS

* ## `color`

    * Define a cor do elemento, essa propriedade pode aceitar seus valores como:

    * Texto ex(red, blue, etc)
    * Código hex ex(#00000, #FFFFF)
    * <abrr title= "RED GREEN BLUE">__RGB__</abrr> ex( rgb(0, 0, 255) ) 
    * RGBA ex( rgba(0, 0, 255, 0.6), no rgba o último elemento controla o contraste sendo o máximo 1 e o mínimo 0)

    ~~~~CSS
    body{
        color: rgba(255 , 0, 0, 0.6);
    }
    ~~~~

* ## `background`
   
    * Define os valores de fundo de um elemento, seja ele cor ou imagem.

    ~~~~CSS
    body{
        background: rgba(255 , 0, 0, 0.6);
    }
    ~~~~

* ## `box-sizing`

    * Define qual o ponto de referência para dimensionar o elemento, podendo ser definido pelo borda (`"border-box"`) ou pelo conteúdo (`"content-box"`), que o padrão do CSS.

    ~~~~CSS
    body{
        box-sizing: border-box;
    }
    ~~~~

* ## `font-family`

    * Define o tipo de fonte do elemento.

    ~~~~CSS
    body{
        font-family: 'Times New Roman', Times, serif;
    }
    ~~~~

    * No exemplo acima percebe-se que foi colcado 3 tipos de fontes diferentes.

    * O motivo disso se deve ao fato de que caso não seja possível aplicar a primeira opção (Times New Roman), será aplicado a segunda e assim por diante.

* ## `font-sizing`

    * Define o tamanho da fonte.

    ~~~~CSS
    body{
        font-size: 18px;
    }
    ~~~~

* ## `width`, `height`

    * Define o comprimento e a altura do elemento respectivamente.

    ~~~~CSS
    body{
        width: 18px;
        height: 50% /*A porcentagem é definida a parte do tamanho da página*/
    }
    ~~~~

* ## `margin`, `padding`

    * Define o tamanho da margin e do padding respectivamente.

    ~~~~CSS
    body{
        margin: 18px;
        padding: 10px;
    }
    ~~~~

    * Há também como definir para partes específicas (cima, baixo, esquerda, direita).

    ~~~~CSS
    body{
        margin-top: 18px; /*Define a margem de cima como 18 pixels*/
        margin-bottom: 19px; /*Define a margem de baixo como 10 pixels*/
        margin-left: 20px; /*Define a margem da esquerda como 20 pixels*/
        margin-right: 15px; /*Define a margem da direita como 15 pixels*/
    }
    ~~~~

* ## `border`

    * Define a borda do elemento, podendo até mesmo desbilitar a borda.

    ~~~~CSS
    body{
        border 15px /*Tamanho da borda*/ solid /*estilo da borda*/ red /*cor*/;
    }
    ~~~~

* ## `text-align`

    * Define o alinhamento do texto de um elemento.

    ~~~~CSS
    body{
        text-align: center;
    }
    ~~~~

*  ## `list-style`

    * Define o estilo de enumeração/organização de uma lista.

    ~~~~CSS
    ul{
        list-style: none;  
    }

    ul{
        list-style: circle;
    }
    ~~~~

* ## `text-decoration`

    * Define o tipo de formatação do elemento (negrito, sublinhado, italico, nenhum)

    ~~~~CSS
    a{
        text-decoration: None;
    }
    ~~~~