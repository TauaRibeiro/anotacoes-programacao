# MANIPULAÇÃO DE STRINGS

FUNÇÕES|DESCRIÇÃO
:--------:|:-------:
str.find(), str.index()| Retorna o índice da primeira ocorrêcia de um valor, caso não encontre retorna -1
str.rfind(), str.rindex()| A mesma coisa do anterior, só que vai da direita para esquerda
str.replace()| Substitui uma substring por outra.
str.split()| Divide uma string em uma lista baseado em um delimitador
str.join()| Junta uma lista de strings baseado em uma única string com delimitador específico
str.capitalize() | Converte o primeiro caractere para maiúscula
str.title() | Converte o primeiro caractere de cada palavra para maiúscula.
str.upper(), str.lower()| Converte todos os caracteres para maíusculas e minúsculas respectivamente
str.strip(), str.rstrip(), str.lstrip()| Remove espaços ou caracteres específicos do início e/ou final de uma string
str.center(), str.ljust(), str.rjust()| Alinha a string ao centro, à esquerda, à direita com preenchimento. 
|

* ### EXPRESSÕES REGULARES
    * As expressões regulares são ferramentas poderosas para realizar buscas e manipulações de string mais sofisticadas. Pois elas pemitem a definição de um padrão de busca complexo.

    * Para utilizar essas funcionalidade é necessário importar o módulo `re`.

    * Sintaxe Básica:
        - `.`: Corresponde a qualquer caracter, exceto uma nova linha.
        - `^`: Corresponde ao início de uma string.
        - `$`: Corresponde ao final de uma string.
        - `*`: Corresponde a 0 ou mais ocorrências.
        - `+`: Corresponde a 1 ou mais ocorrências.
        - `?`: Corresponde a 0 ou 1 ocorrências do padrão anterior.
        - `{n}`: Corresponde exatamente n ocorrências do padrão.
        - `{n,m}`: Corresponde de n a m ocorrências dod padrão.
        - `[]`: Define um conjunto de caracteres.
        - `|`: Operador "ou". Corresponde a uma das alternativas fornecidas.
        - `\`: Caracter de escape para correspondências literais ou para usar classes especias.

    * Classes de caracteres especiais:
        - `\d`: Corresponde a qualquer dígito (equivalente a `[0, 9]`)
        - `\D`: Corresponde a qualquer caracter que não seja um dígito.
        - `\w`: Corresponde a qualquer caracter alfanumérico ou sublinhado `([A-Z, a-z, 0-9,_])`
        - `\W`: Corresponde a qualquer caracter que não seja alfanumérico
        - `\s`: Corresponde a qualquer espaço branco (espaços, tabulações, novas linhas)
        - `\S`: Corresponde a qualquer caracter que não seja espaço em branco.  


    FUNÇÕES | DESCRIÇÃO
    :-------:|:-------:
    re.search(padrão, string)| Procura pela primeira ocorrência de um padrão dentro de uma string.
    re.match(padrão, string) | Verifica se o início da string corresponde ao padrão.
    re.findall(padrão, string) | Retorna todas as correspondências de um padrão em uma string.
    re.sub(padrão, subst,string) | Substitui todas as correspondências de um padrão por outra string.
    re.finditer(padrão, string) | Retorna um iterador com objetos `match` para todas as corrêspodências do padrão na string
    re.split(padrão, string) | Divide a string com base no padrão e retorna uma lista

    EXEMPLO:
    ~~~~PYTHON
    import re

    texto = 'O número de telefone é 1234-5678'
    padrao = r'\d{4}-\d{4}' # Padrão para um número de telefone

    numero = re.serch(padrao, texto)
    print(numero.group()) # Output: 1234-5678
    ~~~~


    Exemplo de substituição:
    ~~~~python
    texto = 'A cor é azul, azul é lindo'
    novo_texto = re.sub(r'azul', 'vermelho', texto)
    print(novo_texto) # Saída: A cor é vermelho, vermelho é lindo
    ~~~~


    * Grupos e captura:
        * Usar parêntese `()` permite capturar partes específicas do padrão. Os grupos podem ser referenciados postriormente no código ou usados em substituições.

        Exemplo:
        ~~~~python
        pattern = r'(\d+)-(\d+)-(\d+)'
        string = "2024-08-21"
        match = re.match(pattern, string)

        if match:
            print(match.group(1))  # Ano
            print(match.group(2))  # Mês
            print(match.group(3))  # Dia
        ~~~~
    
    * Flags:
        - #### As flags modificam o comportamento da busca. Algumas das mais comuns são:
            - `re.IGNORECASE` (`re.I`): Ignora maiúsculas e minúsculas
            - `re.MULTILINE` (`re.M`): Permite que `^` e `$` correspondam ao início e fim de cada linha, não apenas do texto completo
            - `re.DOTALL` (`re.S`): Faz com que o ponto (`.`) corresponda a qualquer caracter, incluindo novas linhas

        Exemplo:
        ~~~~python
        pattern = r'^abc'
        string = "ABCdef"
        match = re.match(pattern, string, re.IGNORECASE)
        if match:
            print("Correspondência encontrada:", match.group())

        ~~~~~

# SETS
* Sets (ou conjuntos), são uma estrutura de dados que armazena elementos únicos. São úteis quando se precisa manter uma coleção de itens distintos e deseja realizar operações matemáticas.

    ### Características
    1. Elementos únicos, ou seja, não podem se repetir
    2. Os elementos não possuem uma ordem específica.
    3. São mutéveis
    4. Os elementos de um set devem ser imutáveis, como por exemplo números e strings. Objetos mutáveis (como listas e dicionários) não podem ser inseridos diretamente.

    ### Criar um set
    ~~~~python
    # Criando sets
    s1 = {1, 2, 3, 4}    # Set com quatro elementos
    s2 = set([1, 2, 3, 4])  # Convertendo uma lista para set

    # Criando um set vazio
    s3 = set()  # Isso é um set vazio
    ~~~~

    > OBS: Um `{}` sozinho irá criar um dicinário vazio, não um set

    ### Operações com sets
    1. Adicionar elementos
    * Para adicionar um elemento, se usa o método `add()`.

    ~~~~python
    s = {1, 2, 3}
    s.add(4)
    print(s)  # Saída: {1, 2, 3, 4}
    ~~~~

    2. Remover elementos
    * `remove(elemento)`: Remove um elemento específico, levantando um erro se não estiver no set
    * `discard(elemento)`: Remove um elemento, mas não lança erro se o elemento não estiver presente
    * `pop()`: Remove e retorna um elemento aleatório do set.

    ~~~~python
    s = {1, 2, 3, 4}
    s.remove(2)
    print(s)  # Saída: {1, 3, 4}
    ~~~~

    > OBS: `pop` vai sempre escolher remover o menor número de um set, caso haja strings ele irá escolher aletóriamente entre o menor número e a(s) strings.

    3. Verificar a existência de um elemento
    * Você pode verificar se um elemento está em um set usando a palavra-chave `in`

    ~~~~python
    s = {1, 2, 3}
    print(2 in s)  # Saída: True
    ~~~~

    4. Operações matemáticas
    * Sets suportam diversas operações matemáticas baseadas em conjuntos:
        * União (`union()` ou `|`): Combina todos os elementos de dois sets (sem duplicatas)
        * Interseção (`intersection()` ou `&`): Retorna apenas os elementos presentes em ambos os sets.
        * Diferença (`difference()` ou `-`): Retorna os elementos presentes em um set, mas não no outro.
        * Diferença simétrica (`symmetric_difference()` ou `^`): Retorna os elementos que estão em um outro set, mas não em ambos.

    ~~~~python
    s1 = {1, 2, 3}
    s2 = {3, 4, 5}

    # União
    print(s1 | s2)  # Saída: {1, 2, 3, 4, 5}

    # Interseção
    print(s1 & s2)  # Saída: {3}

    # Diferença
    print(s1 - s2)  # Saída: {1, 2}

    # Diferença simétrica
    print(s1 ^ s2)  # Saída: {1, 2, 4, 5}
    ~~~~

    5. Métodos úteis para sets
        * `issubset()`: Verifica se um set é um subconjunto de outro.
        * `issupperset()`: Verifica se um set é um superconjunto de outro.
        * `copy()`: Cria uma cópia do set
        * `clear()`: Remove todos os elementos

        ~~~~python
        s1 = {1, 2, 3}
        s2 = {1, 2}

        print(s2.issubset(s1))  # Saída: True
        print(s1.issuperset(s2))  # Saída: True
        ~~~~

    6. frozensets():
    * A função `frozensets()` transforma o conjunto em um conjuto imutável, o que permite que adicione um conjuto a outro conjuto.
    
    Exemplo:
    ~~~~python
    conjuntos = {
    frozenset({1, 2, 3}),
    frozenset({2, 3, 4}),
    frozenset({3, 5}),
    frozenset({6}),
    frozenset({1, 7, 8}),
    }
    ~~~~ 

# MANIPULAÇÃO DE DADOS
## PILHA
* As pilhas segurem o princípio **LIFO** (Lanst In, First Out), ou seja, o último elemento a ser inserido é retirado primeiro.

* ### OPERALÕES COMUNS:
    * Adiciona um elemento ao topo da pilha.
    * Remove o elemento do topo da pilha.
    * Retorna o elemento no topo da pilha sem removê-lo.
    * Verifica se a pilha está vazia.

    Exemplo:
    ~~~~python
    # Implementando uma pilha em Python
    pilha = []

    # Adicionando elementos (push)
    pilha.append(10)
    pilha.append(20)
    pilha.append(30)

    # Removendo o topo da pilha (pop)
    elemento_topo = pilha.pop()  # 30 será removido

    # Verificando o topo da pilha sem removê-lo (peek)
    elemento_topo = pilha[-1]  # Retorna 20, sem remover

    # Verificando se a pilha está vazia
    e_vazia = len(pilha) == 0
    ~~~~

## Fila (Queue)
* Uma fila segue o princípio de **FIFO (First In, First Out)**, ou seja, o primeiro elemento inserido é o primeiro a ser removido.

* ### OPERAÇÕES COMUNS:
    * Adicionar um elemento ao final da fila.    
    * Remover um elemento do inicio da fila.    
    * Retornar o primeiro elemento sem removê-lo.    
    * Verificar se a fila está vazia.    
    
    Exemplo:
    ~~~~python
    # Implementando uma fila em Python
    fila = []

    # Adicionando elementos (enqueue)
    fila.append(10)
    fila.append(20)
    fila.append(30)

    # Removendo o primeiro elemento da fila (dequeue)
    primeiro_elemento = fila.pop(0)  # 10 será removido

    # Verificando o primeiro elemento sem removê-lo (front)
    primeiro_elemento = fila[0]  # Retorna 20

    # Verificando se a fila está vazia
    e_vazia = len(fila) == 0
    ~~~~

## Deque (Double-ended Queue)
Um deque é uma estrutura que permite a inserção e remoção de dados tanto pela início quanto pelo fim. Sendo assim uma combinação de fila e pilha.

* ### OPERAÇÕES COMUNS:
    * Adicionar um elemento ao final.
    * Adicionar um elemento ao inicio.
    * Remover o elemento do final.
    * Remover o elemento do início.

    ~~~~python
    # Criando um deque
    deque = []

    # Adicionando elementos no final
    deque.append(10)
    deque.append(20)

    # Adicionando elementos no início
    deque.insert(0, 5)

    # Removendo o elemento do final
    ultimo_elemento = deque.pop()  # Remove 20

    # Removendo o elemento do início
    primeiro_elemento = deque.pop(0)  # Remove 5
    ~~~~

> * OBS: Existe uma biblioteca do python chamado `collections` onde nele contem funções e modulos para manipulação de dados com filas, pilhas e queues.

# LAMBDA
* As funções `lambda` são funções anônimas(não possuem um nome explicito), pequenas e rápidas que são usadas em espressões simples
* Diferente das funções tradicionais, ao invés de usar `def`, você usa `lambda`

~~~~python
# lambda <parâmetro 1, parâmetro 2, ...>: <retorno>
soma = lambda x, y: x + y

print(soma(2, 3)) # Resultado = 5
~~~~

# FUNÇÕES DE ORDEM SUPERIOR
* As funções de ordem superior são funções que podem receber outras funções como argumentos ou retornar outras funções como resultado. 
* São fundamentais na programção funcional, pois permitem que valores sejam passados e manipulados como quaisquer outros objetos.
* Algumas funções mais comuns desse tipo são: `map()`, `filter()`, `reduce()`, e `sorted()`

* ## MAP
    * A função `map()` aplica uma função a cada item iterável (ex: listas, tuplas) e retorna um iterador (objeto que permite percorrer elementos sem um ídice explicito).

    ~~~~python
    numeros = [1, 2, 3, 4, 5]

    print(list(map(lambda x: x*2, numeros))) # Resultado: [2,4,6,8,10]
    ~~~~

    * No exemplo acima, dentro da função `print()`, `map()` recebe como parâmetros a função `lambda` que retorna o dobro de um elemento, e a lista `numeros`.
    * Após isso o resultado de `map()` é convertido em uma lista e então é mostrado na tela o resultado

* ## FILTER
    * A função `filter()` realiza o filtro de itens iteráveis baseado em função que retorna um valor booleano(True ou False). Apenas os itens para qual a função retorna `True` são mantidos no resultado final.

    ~~~~python
    numeros = [1,2,3,4,5]

    pares = list(filter(lambda x: x % 2 == 0, numeros)) # Filtra pares
    impares = list(filter(lambda x: x % 2 != 0, numeros)) #Filtra ímpares

    print(f'PARES: {pares}\nÍMPAERS: {impares}')

    '''
    Resultado:
    PARES: [2, 4]
    ÍMPARES: [1, 3, 5]
    ''' 
    ~~~~

    * O que ocorre no exemplo acima é o seguinte, as variáveis (pares, impares) recebem uma lista de valores filtrados da função `filter()`. Onde o primeiro argumento é a função `lambda`, que é responsável por verificar se um número é par ou ímpar, e o segundo é a lista numeros.

* ##  REDUCE
    > ### IMPORTANTE
    > Para usar essa função, primeiro é necessário importá-la da biblioteca `functools`.
    
    * A função `reduce()` faz a redução de um iterável para um único elemento através de uma função que será aplicada cumulativamente.

    ~~~~python
    from functools import reduce

    numeros = [1,2,3,4,5]

    print(f'SOMA: {reduce(lambda x, y: x+y, numeros)}')
    print(f'SUBTRAÇÃO: {reduce(lambda x, y: x-y, numeros)}')
    print(f'MULTIPLICAÇÃO: {reduce(lambda x, y: x*y, numeros)}')
    print(f'DIVISÃO: {reduce(lambda x, y: x/y, numeros):.2f}')

    '''
    RESULTADO:
    SOMA: 15
    SUBTRAÇÃO: -13
    MULTIPLICAÇÃO: 120
    DIVISÃO: 0.01
    '''
    ~~~~

    * O que ocorre no exemplo é o seguinte, vamos analisar soma para entender melhor o que ocorre, em o primeiro parâmetro de `reduce()` é função `lambda()` que faz soma de dois elementos.
    * Primeiro ocorre a soma de 1 + 2, em que a função `lambda()` retorna 3, depois ocorre a soma do resultado anterior (3) + 3, retornando 6, e assim por diante até o fim da lista números.

    > ### NOTA IMPORTANTE
    > * A função reduce pode receber um valor adicional que é o valor inicial, que é o valor em que ele irá fazer as acumulações.

    ## SORTED
    * A função `sorted` ordena os itens de um iterável, e pode passar uma função como argumento.

    ~~~~python
    pessoas = [('joão', 25), ('Maria', 22), ('Ana', 28)]

    ordenado = sorted(pessoas, key= lambda x: x[1]) # Ordena os itens apartir da idade

    print(ordenado) 
    # Resultado: [('Maria', 22), ('João', 25), ('Ana', 28)]
    ~~~~

    * Neste exemplo a função usa a idade retornada por `lambda()` para fazer a organização dos elementos em ordem crescente, criando assim uma nova lista com os valores organizados.

    >### NOTA IMPORTANTE
    > * A função sorted pode tamber receber um argumento opcional que é o `reverse`, que funciona da mesma que o reverse de `sort()`
    ~~~~python
    pessoas = [('João', 25), ('Maria', 22), ('Ana', 28)]

    ordenado = sorted(pessoas, key= lambda x: x[1], reverse= True)

    print(ordenado) 
    # Resultado: [('Ana', 28), ('João', 25), ('Maria', 22)]
    ~~~~

    ## FUNÇÕES COMO OBJETOS DE PRIMEIRA CLASSE
    * Em python as funções podem ser tratadas como objetos de primeira classe, ou seja, podem ser atribuídas a variáveis, passadas como argumento, retornadas e armazenadas em estruturas de dados(ex: listas ou dicionários).

    Exemplo 1:
    ~~~~python
    def saudacao(nome):
        return f'olá, {nome}'

    # Atribuindo a função a uma variável
    cumprimentar = saudacao

    # Chmando a função através da nova variável
    print(cumprimentar('Maria'))
    ~~~~
    * Explicação: A função `saudacao` é atribúida à variável `cumprimentar`, permitindo chamar a função através dela.

    Exemplo 2:
    ~~~~python
    def aplicar_operacao(x, y, operacao):
        return operacao(x, y)

    def soma(a, b):
        return a + b

    def multiplicacao(a, b):
        return a * b

    # Passando a função soma como argumento
    resultado_soma = aplicar_operacao(5, 3, soma)
    print(f"Resultado da soma: {resultado_soma}")

    # Passando a função multiplicacao como argumento
    resultado_multiplicacao = aplicar_operacao(5, 3, multiplicacao)
    print(f"Resultado da multiplicação: {resultado_multiplicacao}")

    ~~~~
    Explicação: Nesse exemplo a função `apilcar_operacao` recebe outra função como argumento(`operacao`) e aplica aos valores x e y. O que permite aplicar diferente operações (soma, multiplicar) sem alterar o código da função.
    
    Exemplo 3:
    ~~~~python
    def saudacao_personalizada(saudacao):
    def saudar(nome):
        return f"{saudacao}, {nome}!"
    return saudar

    # Criando uma nova função com uma saudação personalizada
    bom_dia = saudacao_personalizada("Bom dia")
    boa_noite = saudacao_personalizada("Boa noite")

    # Usando as novas funções
    print(bom_dia("Carlos"))
    print(boa_noite("Ana"))

    ~~~~
    Explicação: A função `saudação personalizada` retorna outra função (`saudar`), que é personalizada com uma saudação específica. Assim, podemos criar várias versões da função `saudar` com diferentes saudações.

    Exemplo 4:
    ~~~~python
    def somar(x, y):
    return x + y

    def subtrair(x, y):
        return x - y

    # Armazenando funções em um dicionário
    operacoes = {
        "soma": somar,
        "subtracao": subtrair
    }

    # Usando funções a partir do dicionário
    resultado = operacoes["soma"](10, 5)
    print(f"Resultado da soma: {resultado}")

    resultado = operacoes["subtracao"](10, 5)
    print(f"Resultado da subtração: {resultado}")

    ~~~~
    Explicação: Neste exemplo, as funções somar e subtrair são armazenadas em um dicionário e podem ser acessadas e chamadas usando as chaves do dicionário.

    ## CLOSURE
    * Uma closure é quando uma função interna(definida dentro de outra função) "lembra" do ambiente em que foi criada, mesmo após a função externa ter finalizado a sua execução.
    * Um exemplo prático de uma closure é o exemplo 3 da parte de `FUNÇÕES COMO OBJETOS DE PRIMEIRA CLASSE`:
    
    ~~~~python
    def saudacao_personalizada(saudacao):
    def saudar(nome):
        return f"{saudacao}, {nome}!"
    return saudar

    bom_dia = saudacao_personalizada("Bom dia")
    boa_noite = saudacao_personalizada("Boa noite")

    print(bom_dia("Carlos"))
    print(boa_noite("Ana"))

    ~~~~
    * Neste exemplo, a função externa (`saudacao_personalizada`) recebe um argumento chamado *saudacao* e define uma função interna chamada `saudar`.
    * E esta função interna consegue usar a variável *saudacao* definida na função externa e a combina com o argumento *nome* que ela própria recebe.
    * Após isso a função externa retorna a função interna.
    * E é por isso que mesmo depois de a função `saudacao_personalizada` ter terminado de excutar, as funções *bom_dia* e *boa_noite* "lembram" do valor de saudacao que foi passado quando foram criadas.

    exemplo:
    ~~~~python
    def criar_contador(inicial=0):
    contador = inicial

    def incrementar():
        nonlocal contador
        contador += 1
        return contador

    return incrementar

    # Criando um contador que começa em 10
    contador_10 = criar_contador(10)

    print(contador_10())  # Saída: 11
    print(contador_10())  # Saída: 12
    print(contador_10())  # Saída: 13

    ~~~~
    Explicação:
    * A função `criar_contador` cria e retorna a função `incrementar`.
    * `incrementar` utiliza a variável da função externa, e com nonlocal, permite modificar essa variável em cada chamada.
    * Mesmo após a função externa terminar, a função incrementar mantém o estado de contador. 

    ## DECORADORES
    * Um decorador é essencialmente uma função que recebe outra função como argumento, adiciona alguma funcionalidade a ela, e retorna uma nova função ou a função original decorada. Eles são frequêntemente usados para reutilizar código, implementar lógica de pré e pós-processamento, ou adicionar comportamentos como loggin, autenticação, controle de acesso, etc.

    ### Estrutura básica

    ~~~~python

    def meu_decorador(funcao):
        def funcao_decorada(*args, **kwargs):
            # Código antes da execução da função original
            print("Antes de chamar a função")
        
            resultado = funcao(*args, **kwargs)
    
            # Código após a execução da função original
            print("Depois de chamar a função")
    
        return resultado
    return funcao_decorada

    ~~~~

    * Para aplicar um decorador em uma função se usa o símbolo `@` seguido do nome do decorador, logo antes da definição da função:

    ~~~~python
    @meu_decorador
    def diga_oi():
        print('Oi!')
    
    # Chamando a função decorada
    diga_oi()
    '''
    Saída:
    Antes de chamar a função
    Oi!
    Depois de chamar a função
    '''
    ~~~~
    
    ### Como Funciona?
    1. A função `meu_decorador` recebe outra função como argumento (no caso, `diga_oi`)
    2. Dentro do decorador, a função interna `funcao_decorada` é definida, que envolve a função original. Essa função interna executa algum código antes e depois de chamar a função original.
    3. O decorador retorna a função `funcao_decorada`, que agora envolve a função original com comportamento adicional.
    4. Ao aplicar `@meu_decorador` em `diga_oi`, você está substituinda diga_oi pela versão decorada, que executa o código adicional.

    ### Decoradores com argumentos
    * Às vezes, você pode querer passar argumentos para um decorador. Isso é feito criando uma função que retorna o decorador
    ~~~~python
    def repetir(n):
        def decorador(funcao):
            def funcao_decorada(*args, **kwargs):
                for _ in range(n):
                    funcao(*args, **kwargs)
            return funcao_decorada
        return decorador

    @repetir(3)
    def diga_oi():
        print("Oi!")

    # Chamando a função decorada
    diga_oi()
    ~~~~
    Explicação:
    * `@repetir(3)` cria um decorador que repete a função original 3 vezes
    * A função decorada `diga_oi` agora é executada três vezes

    ### Decoradores comuns em python
    * Alguns decoradores são amplamentes usados na comunidade Python e são até mesmo fornecidos como parte da linguagem:
    1. `@staticmethod` e `@classmethod`:
        * Usado em classes para definir métodos que não dependem da instância (@staticmehod) ou que são chamados na classe em si (@classmethod)
        
        Exemplo `@staticmethod`:
        ~~~~python
        class Calculadora:
            @staticmethod
            def somar(a, b):
                return a + b
            
            @staticmethod
            def subtrair(a, b):
                return a - b

        # Chamando métodos estáticos diretamente pela classe
        print(Calculadora.somar(10, 5))      # Saída: 15
        print(Calculadora.subtrair(10, 5))   # Saída: 5

        ~~~~
        Explicação: Os métodos criados na classe são métodos estáticos, ou seja, podem serem chamados diretamente a partir de uma classe sem criar uma instância dela.

        Exemplo `@classmethod`:
        ~~~~python
        class Pessoa:
            ano_atual = 2024

            def __init__(self, nome, ano_nascimento):
                self.nome = nome
                self.ano_nascimento = ano_nascimento

            @classmethod
            def criar_pessoa_pelo_ano_de_nascimento(cls, nome, idade):
                ano_nascimento = cls.ano_atual - idade
                return cls(nome, ano_nascimento)

        # Criando instâncias usando o método de classe
        pessoa1 = Pessoa("Carlos", 1990)
        pessoa2 = Pessoa.criar_pessoa_pelo_ano_de_nascimento("Maria", 30)

        print(pessoa1.nome, pessoa1.ano_nascimento)  # Saída: Carlos 1990
        print(pessoa2.nome, pessoa2.ano_nascimento)  # Saída: Maria 1994
        ~~~~
        Explicação: 
        * `criar_pessoa_pelo_ano` é um método de classe que usa o atributo ano_atual para calcular o ano de nascimento e criar uma nova instância de Pessoa.
        * Isso permite criar objetos de maneira personalizada sem precisar passar diretamente o ano de nascimento. 

    2. `@property`:
        * Usado para definir métodos que podem ser acessados como atributos, permitindo um estilo mais Pythonic ao acessar dados de uma classe.

        ~~~~python
        class Funcionario:
            def __init__(self, nome, salario):
                self.nome = nome
                self._salario = salario  # Atributo privado

            @property
            def salario(self):
                return self._salario

            @salario.setter
            def salario(self, valor):
                if valor < 0:
                    raise ValueError("Salário não pode ser negativo!")
                self._salario = valor

        # Criando uma instância de Funcionario
        func = Funcionario("Ana", 5000)

        # Acessando o salário
        print(func.salario)  # Saída: 5000

        # Modificando o salário usando o setter
        func.salario = 6000
        print(func.salario)  # Saída: 6000

        # Tentando atribuir um salário negativo
        # func.salario = -1000  # Isso gera um erro: ValueError: Salário não pode ser negativo!
        ~~~~
        Explicação: salario é um atributo com getter(método que permite pegar ou obter um valor) e um setter(método que é usado para definir ou setar um valor). O getter permite acessar salario enquanto o setter permite modificar com uma validação.


    3. `@functools.wraps`:
        * Usado para preservar as informações da função original ao criar um decorador, como o nome e a docstring da função original.

        Exemplo:
        ~~~~python
        import functools

        def log(funcao):
            @functools.wraps(funcao)
            def funcao_decorada(*args, **kwargs):
                print(f"Chamada da função {funcao.__name__} com os argumentos {args} e {kwargs}")
                resultado = funcao(*args, **kwargs)
                print(f"Função {funcao.__name__} retornou {resultado}")
                return resultado
            return funcao_decorada

        @log
        def soma(a, b):
            return a + b

        # Chamando a função decorada
        resultado = soma(5, 10)
        ~~~~
        Explicação: O decorador `log` envolve a função soma, adicionando logs antes e depois da chamada da função, registro os parâmetros de entrada e o valor de retorno
    
    ## GERADORES
    * Os geradores são um tipo especial de função que permitem iterar sobre uma sequência de valores de forma preguiçosa(lazy evaluation), ou seja, os valores são gerados sob demanda, um de cada vez, em vez de todos de uma vez. Isso economiza memória e processamento, especialmente ao lidar com grandes conjuntos de dados.

    ### Como funcionam os geradores?
    * Um gerador é criado usando uma função normal, mas em vez de usar a palavra-chave `return`, usa-se yield.
    * Toda vez que a função com `yield` é chamado, ela pausa sua execução e retorna um valor.
    * Na próxima vez que a função for chamada, ela retorna exatamente de onde parou, matendo o estado das varáveis.

    ### Sintaxe
    ~~~~python
    def meu_gerador():
    yield 1
    yield 2
    yield 3

    # Chamando o gerador
    gen = meu_gerador()

    # Iterando sobre o gerador
    for valor in gen:
        print(valor)
    ~~~~
    Explicação:
    * yield: Em vez de retornar um valor e terminar a função, ele "pausa" a execução e retorna o valor. Na próxima vez que o gerador for chamado, a execução continua a partir do ponto onde foi pausada.
    * A função `meu_gerador()` retorna um objeto gerador, que pode ser iterado como uma lista, mas sem criar todos os elemento de uma vez.

    ### Vantagens dos geradores
    1. Eficiência de memória: Geradores não armazenas todos os vlaores na memória, o que é útil para trabalhar com grandes volumes de dados ou fluxos de dados infinitos.
    2. Lazy evaluation: Os valores são gerados sob demanda, o que significa que você pode começar a trabalhar com o primeiro valor imediatamente sem precisar esperar que toda a sequência seja gerada.
    3. Iteração infinitamente longa: Como os valores são gerados conforme necessário, você pode criar geradpres que nunca terminam, como geradores de números infinitos.

    Exemplo:
    ~~~~python
    def contador_infinito(inicio=0):
    while True:
        yield inicio
        inicio += 1

    # Criando o gerador
    gen = contador_infinito()

    # Pegando os primeiros 5 valores
    for _ in range(5):
        print(next(gen))

    ~~~~
    Explicação: O gerador usa um loop, gerando números continuamente a partir do valor inicial. Toda vez que yield é chamado, o gerador "pausa" e estrutura pela próxima iteração para continuar.

    ### `next()` e geradores
    * Você pode chamar explicitamente o próximo valor de um gerador usando a função `next()`:
    * Toda vez que você chama `next()`, o gerador avança para o próximo valor, recomeçando a execução da função a partir de onde foi pausada.

    ~~~~python
    gen = contador_infinito(10)
    print(next(gen))  # Saída: 10
    print(next(gen))  # Saída: 11
    print(next(gen))  # Saída: 12
    ~~~~

    * Além do `next()` existe o método `send()`, que permite enviar o ponto em que foi pausado (no yield). Esse valor é passdo como argumento para o gerador, substituindo o valor de retorno do yield na proxima iteração.

    Exemplo:
    ~~~~python
    def contador():
    numero = 0
    while True:
        incremento = yield numero  # Espera por um valor enviado com `send()`
        if incremento is not None:
            numero += incremento
        else:
            numero += 1  # Se nada for enviado, incrementa normalmente

    # Inicializa o gerador
    gen = contador()

    # Avança até o primeiro `yield`
    print(next(gen))  # Saída: 0

    # Envia um valor que será usado para alterar o comportamento
    print(gen.send(5))  # Saída: 5

    # Continua a contagem sem enviar nada
    print(next(gen))  # Saída: 6

    # Envia um novo valor para o incremento
    print(gen.send(3))  # Saída: 9
    ~~~~

    > ## OBS!
    > * O método send só aceita um argumento, então para passar vário você precisa transforma os valores que deseja passar em uma tupla, lista, dicionário. Ex: `gerador.send((2, 5))`

    ### Geradores e compreensão de listas
    * Python oferece uma maneira concisa dee criar geradores, semelhante a compreensão de listas, mas usando parênteses em vez de colchetes.

    Exemplo:
    ~~~~python
    # Compreensão de listas
    lista = [x * x for x in range(5)]
    print(lista)  # Saída: [0, 1, 4, 9, 16]

    # Compreensão de gerador
    gerador = (x * x for x in range(5))
    print(gerador)  # Saída: <generator object <genexpr> at 0x7f934e2bb200>

    # Iterando sobre o gerador
    for valor in gerador:
        print(valor)

    ~~~~
    Explicação: Aque, a compreensão do gerador não cria a lista inteira na memória, mas gera os valores sob demanda conforme são solicitados.

# MANIPULAÇÃO DE ARQUIVOS
## CSV
* Um arquivo CSV (**Coma-Separeted Values**) é um arquivo de texto simples que organiza dados em forma de tabela, onde:
    * Cada linha respresenta um registro;
    * Cada valor detro dessa linha é separado por uma vírgula (ou outro delimitador, como ponto e vírgula ou tabulação)

Exemplo:
~~~~CSV
nome,idade,cidade
João,30,São Paulo
Maria,25,Rio de Janeiro
Carlos,35,Brasília
~~~~ 

* Aqui, temos três colunas: nome, idade, cidade. Cada linha subsequente representa uma pessoa com essas informações.

### 1. Leitura de arquivos CSV
* A leitura desses arquivos em python podem ser feitas por diversas formas. Contudo python fornece por padrão a biblioteca csv, que facilita essa operação.

* #### Método 1: csv.reader():
    * Nesse método, o arquivo é lido linha por linha e cada linha é retornada como uma lista. Este método é útil quando você deseja uma maneira simples de acessar os dados, sem se preocupar com os cabeçalhos.

    ~~~~python
    import csv

    # Abrir o arquivo CSV no modo de leitura ('r')
    with open('teste csv.csv', 'r', encoding= 'utf-8') as arquivo_csv:
        leitor_csv = csv.reader(arquivo_csv)  # Cria um objeto leitor
        for linha in leitor_csv:
            print(linha)  # Cada linha é uma lista de valores
    ~~~~
    Explicação:
    * O `csv.reader()` lê o arquivo linha por linha
    * Cada linha é convertida em uma lista onde cada elemento é um valor separado por vírgula no CSV.
    * O `with open(...)` abre o arquivo, garantido que ele seja fechado automaticamente após a leitura. O parâmetro `encoding` é definido para `utf-8` para que seja possível ler acentos.
    * A primeira linha sempre será o cabeçalho enquanto as demais linhas serão os dados.

* ### Método 2: csv.DictReader():
    * Nesse método, ao invés de os dados serem passados como uma lista, eles são passados como um dicionário, onde o nome das colunas são as chaves.

    Exemplo:
    ~~~~python
    import csv

    # Abrir o arquivo CSV no modo de leitura ('r')
    with open('teste csv.csv', mode='r', encoding= 'utf-8') as arquivo_csv:
        leitor_csv = csv.DictReader(arquivo_csv)  # Cria um objeto leitor de dicionários
        for linha in leitor_csv:
            print(linha)  # Cada linha é um dicionário
    ~~~~
    Explicação:
    * O `csv.DictReader()` interpreta a primeira linha do arquivo (o cabeçalho) como as chaves do dicionário
    * Cada linha subsequente é lida como um dicionário, onde os valores estão associados às chaves.

### 2. Escrita de arquivos CSV
* Assim como podemos ler dados, podemos escrever eles em CSV em um arquivo.
* Isso é feito usando os seguintes métodos:

* #### Método 1: csv.writer()
    * Esse método escreve dados como listas, onde cada lista respresenta uma linha no arquivo CSV.

    Exemplo:
    ~~~~python
    import csv

    dados = [
        ['nome', 'idade', 'cidade'],
        ['João', 30, 'São Paulo'],
        ['Maria', 25, 'Rio de Janeiro'],
        ['Carlos', 35, 'Brasília']
    ]

    with open('teste csv.csv', 'w', encoding= 'utf-8', newline= '') as arquivo:
        escritor_csv = csv.writer(arquivo)
        escritor_csv.writerows(dados)
    ~~~~
    Explicação:
    * O `csv.writter()` cria um objeto que pode escrever em arquivos CSV.
    * O método `writerows()` recebe uma lista de listas e escreve cada uma dessas listas como uma linha no arquivo.
    * O argumento `newline` garante que o arquivo seja salvo corretamente sem adicionar linhas em branco entre as entradas (comportamento que varia dependendo do sistema operacional)

* ### Método 2: csv.DictWriter()
    * Esse método é usado caso os dados estejam organizados como um dicionario.

    ~~~~python
    import csv

    # Dados que serão escritos no arquivo CSV como dicionários
    dados = [
        {'nome': 'João', 'idade': 30, 'cidade': 'São Paulo'},
        {'nome': 'Maria', 'idade': 25, 'cidade': 'Rio de Janeiro'},
        {'nome': 'Carlos', 'idade': 35, 'cidade': 'Brasília'}
    ]

    # Abrir o arquivo CSV no modo de escrita ('w')
    with open('teste csv.csv', mode='w', encoding= 'utf-8',newline='') as arquivo_csv:
        campos = ['nome', 'idade', 'cidade']  # Definir as colunas (cabeçalhos)
        escritor_csv = csv.DictWriter(arquivo_csv, fieldnames= campos)
        
        escritor_csv.writeheader()  # Escreve o cabeçalho (primeira linha)
        escritor_csv.writerows(dados)  # Escreve os dados
    ~~~~
    Explicação:
    * O `csv.DictWriter()` aceita uma lista de dicionário.
    * O método `writerheader()` escreve o cabeçalho do CSV (as chaves do dicionário)
    * O método `writerows()` escreve os valores de cada dicionário como uma linha no arquivo.

## JSON
* JSON (JavaScript Object Notation) é um formato leve e aplamente utilizado para armazenar e transportar dados. Ele é muito popular em APIs, aplicações web e sistemas que precisam trocar informações entre si. Apesar de ter "JavaScript" no nome, ele é usado em muitas outras linguagens de programação.

* Em python, existe o módulo embutido chamado `json`, que facilita a manipulação de arquivos JSON.

Exemplo JSON
~~~~python
{
    "pessoas": [
        {"nome": "João", "idade": 30, "cidade": "São Paulo"},
        {"nome": "Maria", "idade": 25, "cidade": "Rio de Janeiro"},
        {"nome": "Carlos", "idade": 35, "cidade": "Brasília"}
    ]
}
~~~~
Neste exemplo:
* O JSON tem uma estrutura hierárquica
* A chave "pessoas" tem como valor uma lista de dicionários, onde cada dicionário representa uma pessoa com informações de nome, idade e cidade.

* ### Leitura de arquivos JSON
    * Quando lemos um rquivo JSON em python, os dados são automaticamente convertidos em estruturas de dados python (como listas e dicionários). Para isso usamos os seguintes métodos.

    ### 1. json.load()
    * Vamos supor que tenha um arquivo `teste.json` com o conteúdo do último exemplo. A leitura dos dados desse arquivo será feito da seguinte form.
    ~~~~python
    import json

    # Abrir o arquivo JSON no modo de leitura ('r')
    with open('teste.json', 'r', encoding= 'utf-8') as arquivo_json:
        dados = json.load(arquivo_json)  # Lê o JSON e converte em um dicionário
        print(dados)
    ~~~~
    Explicação:
    * `with open('teste.json', 'r', encoding= 'utf8')` abre um arquivo JSON no modo de leitura, o `encoding= 'utf-8'` permite que seja lido assentos.
    * O `json.load(arquivo_json)` lê o conteúdo do arquivo e o converte automaticamente em um dicionário (pode ser também convertido em uma lista de dicionários, mas isso depende de como o JSON foi estruturado).

    ### 2. json.loads()
    * Além de arquivos, você também pode ler strings que estão no formato JSON. Para isso, usamos o método `json.loads()`.

    Exemplo:
    ~~~~python
    import json

    # String JSON
    json_string = '{"nome": "João", "idade": 30, "cidade": "São Paulo"}'

    # Convertendo a string JSON em um dicionário Python
    dados = json.loads(json_string)
    print(dados)
    ~~~~

* ### Escrita de arquivos JSON
    * Da mesma forma que podemos ler, também podemos escrever dados em um arquivo JSON. Em python usamos os seguintes métodos.

    * ### 1. json.dump()
    * Vamos supor que você tenha um conjunto de dados em python e deseja salvá-los em um arquivo JSON.

    ~~~~python
    import json

    # Dados em formato de dicionário (ou listas de dicionários)
    dados = {
        "pessoas": [
            {"nome": "João", "idade": 30, "cidade": "São Paulo"},
            {"nome": "Maria", "idade": 25, "cidade": "Rio de Janeiro"},
            {"nome": "Carlos", "idade": 35, "cidade": "Brasília"}
        ]
    }

    # Abrir o arquivo JSON no modo de escrita ('w')
    with open('teste.json', 'w', encoding= 'utf-8') as arquivo_json:
        json.dump(dados, arquivo_json, indent= 4)  # Escreve o JSON no arquivo com indentação
    ~~~~  
    Explicação:
    * O método `json.dump(dados, arquivo_json)` grava os dados no arquivo teste.json em formato JSON.
    * O parâmetro `indente= 4` é opcional, mas ele é usado para deixar o JSON mais fácil de ler. Pois sem ele os dados seriam gravdos em uma única linha.

* ### Tratamento de erros com JSON
    * Como os arquivos JSON podem vir de diversas fontes diversas (por exemplo, APIs, banco de dados ou sistemas internos), é importante tratar erros que podem ocorrer ao manipular esse dados. Alguns dos erros mais comuns são:

    1. ### Erro de sintaxe (json.decoder.JSONDecoderErros)
        * Causa: Isso pode ocorrer quando um arquivo JSON que você está tentando abrir está mal formatado. Podendo ser por ter vírgulas a mais, chaves ou colchetes não fechados, aspas simples ao invés de duplas, etc.
        Exemplo
        ~~~~json
        {
            "nome": "Ana", 
            "idade": 25 // Vírgula faltando
            "cargo": "Desenvolvedor"  
        }
        ~~~~

        * Como evitar: Certifique-se de que o arquivo segue a sintaxe correta. Para isso pode ser usado ferramentas online para a verificação do formato

    1. ### FileNotFoudError
        * Causa: Ocorre quando tenta um abrir um arquivo JSON que não esxiste no caminho especificado

        Exemplo:
        ~~~~python
        with open('dados_inexistente.json') as arquivo:
            dados = json.load(arquivo)  # Arquivo não encontrado
        ~~~~

        Como evitar: Verifique o caminho correto do arquivo antes de tentar carrega-lo. Existe uma função que é `os.path.exist()` para verificar se o arquivo realmente existe.

    1. ### json.JSONDecoderError ao ler um arquivo vazio
        * Causa: Se o arquivo que estiver tentando ler está vazio, a função `json.load()` irá falhar, pois não consegue interpretar um arquivo vazio.

        * Como evitar: Verifique se o arquivo contém dados antes de carregá-lo. Por exemplo:

        ~~~~python
        if os.path.getsize('dados.json') > 0:
        with open('dados.json') as arquivo:
            dados = json.load(arquivo)

        ~~~~
    
    1. ### Erros ao manipular dados não estruturados corretamente
        * Causa: O arquivo pode não conter chaves ou valores esperados, ou pode ter tipos de dados incorretos (por exemplo, uma lista on se espera um dicionário)

        Exemplo:
        ~~~~json
        {
            "nome": "Carlos",
            "idade": "vinte e cinco"  // Espera-se um número, mas é uma string
        }
        ~~~~

        * Como evitar: Sempre verifique o tipo de dados antes de manipulá-los, usando `isinstance()`. Certifique-se também de que as chaves esperadas estão presentes:

        ~~~~python
        if 'idade' in dados and isinstance(dados['idade'], int):
            # Prossiga

        ~~~~

    1. ### Erros ao atualizar JSON em memória sem salvar no arquivo
        * Causa: Após modificar o conteúdo de um dicionário ou lista em memória, você esquece de salvar as alterações de volta no arquivo JSON.

        * Como evitar: Após realizar alterações, certifique-se de escrever o JSON de volta no arquivo usando `json.dump()`

        ~~~~python
        with open('dados.json', 'w') as arquivo:
            json.dump(dados, arquivo, indent=4)

        ~~~~

    1. ### Erros de serialização
        * Causa: Esse erro ocorre quando você tenta serializar um objeto que não pode ser convertido diretamente em JSON, como objetos de data/hora, classes personalizadas, ou tipos complexos como sets.

        Exemplo:
        ~~~~python
        import json
        from datetime import datetime

        dados = {'data': datetime.now()}
        json.dump(dados, arquivo)  # datetime não é serializável por padrão

        ~~~~
        
        * Como evitar: Para lidar com objetos que não podem ser serializados converter esses objetos para um formato compatível ou usar uma função personalizada:

        ~~~~python
        def converter(obj):
            if isinstance(obj, datetime):
                return obj.isoformat()
            raise TypeError(f"Objeto do tipo {type(obj)} não é serializável")

        json.dump(dados, arquivo, default=converter)

        ~~~~
    
    1. ### Erros de codificação (UnicodeEncodeError ou UnicodeDecodeError)
        * Causa:  Isso ocorre quando você tente ler ou gravar dados que contêm caracteres esoeciais ou não ASCII sem especificação correta.

        * Como evitar: Sempre especifique a codição correta ao abrir o arquivos JSON, especialmente quando o arquivo contém caracteres especiais:

        ~~~~python
        with open('dados.json', 'r', encoding='utf-8') as arquivo:
            dados = json.load(arquivo)
        ~~~~
    
    1. ### Erro ao usar json.load() em uma string em vez de json.loads()
        * Causa: Usar a função errada para o tipo errado de entrada.

        * Como evitar: Use json.loads() para strings JSON e json.load() para arquivos JSON.
    
## XML
* XML (eXtensible Markup Language) é uma linguagem de marcação que estrutura dados de maneira hierárquica.
* ElA é muito usado para armazenar e transportar dados, especialmente em comunicação entre sistemas (como API's).
* Diferente do JSON, XML é mais verboso e usa tags aninhadas para organizar os dados.

Exemplo:
~~~~XML
<pessoas>
    <pessoa>
        <nome>João</nome>
        <idade>30</idade>
        <cidade>São Paulo</cidade>
    </pessoa>
    <pessoa>
        <nome>Maria</nome>
        <idade>25</idade>
        <cidade>Rio de Janeiro</cidade>
    </pessoa>
    <pessoa>
        <nome>Carlos</nome>
        <idade>35</idade>
        <cidade>Brasília</cidade>
    </pessoa>
</pessoas>

~~~~
Neste exemplo:
1. O elemento raíz é `<pessoas>`, que contém várias pessoas.
1. Cada `<pessoa>` tem filhos como `<nome>`, `<idade>`, `<cidade>`, que contêm os valores correspondentes.

* Agora, vamos aprender à como ler e escrever arquivos XML usando Python.

* ## Leitura de arquivos XML
    * Para ler um arquivo XML, utilizando a função `parse()` da biblioteca `xml.etree.ElementTree`, que converte o XML em uma estrutura de árvore que pode ser manipulada como objetos Python.

    Exemplo de leitura:
    ~~~~python
    import xml.etree.ElementTree as ET

    # Carregar o arquivo XML
    arvore = ET.parse('dados.xml')  # 'arvore' representa toda a árvore XML
    raiz = arvore.getroot()  # O elemento raiz <pessoas>

    # Iterar sobre cada elemento <pessoa>
    for pessoa in raiz.findall('pessoa'):
        nome = pessoa.find('nome').text
        idade = pessoa.find('idade').text
        cidade = pessoa.find('cidade').text
        print(f'{nome} tem {idade} anos e mora em {cidade}.')

    ~~~~
    Explicação:
    * `ET.parse('dados.xml')`: Lê o arquivo XML e constrói uma árvore de elementos.
    * `getroot()`: Obtém o elemento raiz do documento, neste caso, `<pessoas>`
    * `findall('pessoas')`: Encontra todas as instâncias do elemento `<pessoa>` sob o elemento raiz `<pessoas>`
    * `find('tag').text`: Busca um subelemento (`<nome>`, `<idade>`, `<cidade>`) dentro de cada `<pessoa>` e retorna seu conteúdo como texto.   
 
# DUNDER (Double Underscore)
* Métodos e atributos especiais que tem nome rodeados por duas linhas sublinhada (ex: \_\_init\_\_).
* São usados para definir comportamentos especiais de classes e objetos, permitindo customização.
* Alguns exemplos são:

DUNDER | FUNÇÃO 
:-----:|:------
\_\_init\_\_| É chamado quando um novo objeto é criado. É conhecido como o contrutor da classe.
\_\_str\_\_| Define o que deve ser retornado quando a função str() é chamada no objeto. É utilizado para criar representações légíveis do objeto.
\_\_repr\_\_| Define a representação "oficial" do objeto e é usado principlamente para depuração. O objeto fornece uma string que, se passada para `eval()`, recria o objeto
\_\_add\_\_| Permite o comportamento do operador `+` para classes.
\_\_len\_\_| Define o que deve ser retornado pela função `len()` quando apicada ao objeto 

* Caso necessário consultar [site](https://www.geeksforgeeks.org/dunder-magic-methods-python/ "Tem muita coisa lá") para mais métodos dunder.