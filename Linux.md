# SOBRE

* Campo de anotações onde estarei colocando algumas anotações sobre linux, focando principalmente em comandos que costumo usar ou que achei interessante.

# SUMÁRIO

* [Sobre](#sobre)
* [Comandos](#comandos)
    * [echo](#echo) 
    * [whoami](#whoami)
    * [expr](#expr)
    * [history](#history)
    * [clear](#clear)
    * [pwd](#pwd)
    * [ls](#ls)
    * [cd](#cd)
    * [cat](#cat)
    * [head e tail](#headtail)
    * [less e more](#moreless)
* [Variáveis](#variáveis)

# COMANDOS

## ECHO

### NOTAÇÃO

~~~~bash
echo <texto qualquer>
~~~~

* Ao executar esse comando você irá imprimir o que está logo apos o nome do comando


##### EX: 
~~~~bash
echo Olá mundo
~~~~

## WHOAMI

### NOTAÇÃO

~~~~bash
whoami
~~~~

* Ao executar esse comando será imprimido no terminal o nome do usuário logado na sessão

## EXPR

### NOTAÇÃO

~~~~bash
expr <arg1> <operador> <arg2>
~~~~

* Ao executar esse comando será imprimido no terminal o resultado da expressão dado deterterminado operador

OPERADOR|FUNÇÃO
:-----:|:-----:
<|Verifica se arg1 é menor que arg2
\>|Verifica se arg1 é maior que arg2
<=|Verifica se arg1 é menor ou igual à arg2
\>=|Verifica se arg1 é maior ou igual à arg2
=|Verifica se arg1 é igual à arg2
!=|Verifica se arg1 é diferente de arg2
+|Operação de soma entre arg1 e arg2
-|Operação de subtração entre arg1 e arg2
*|Operação de multiplicação entre arg1 e arg2
/|Operação de divisão de arg1 por arg2
%|Operação de resto de divisão entre arg1 e arg2
|

## HISTORY
* Mostra todo o histórico de comandos executados

### EX:
~~~~bash
history
~~~~

## CLEAR
* Limpa o as informações mostradas no terminal (stdout)

### EX:
~~~~bash
clear
~~~~

## PWD
* Abreviação de `Print Work Directory`, mostra o caminho absoluto do diretório atual.

### EX:
~~~~bash
pwd
~~~~

## LS

### NOTAÇÃO
~~~~bash
ls <caminho>
~~~~

* Abreviação de `List`, lista todos os conteúdos de um diretório. Caso nenhum caminho seja passado irá lista os conteúdos do diretório atual.

### EX:
~~~~bash
ls
ls ./diretorio
ls /home/users/diretorio
~~~~

* O comando tanto aceita o caminho relativo quanto o absoluto.

## CD
### NOTAÇÃO
~~~~bash
cd <caminho>
~~~~

* Abreviação para `change directory`, muda o diretório em que está trabalhando para um outro apartir de um caminho relativo ou absoluto.

### EX:
~~~~bash
cd / # ROOT
cd ~ # Home, o mesmo que cd /home
cd /home/users
cd ./outroDiretorio
cd outroDiretorio
cd .. # Volta para o diretório anterior
~~~~

* Lembrando que se for utilizar o caminho relativo você deve conseguir apartir do diretório em que está.

## CAT
### NOTAÇÃO
~~~~bash
cat <caminho_arquivo> [opcional](<outros_caminhos_arquivos>)
~~~~

* Abreviação de `concatenate`, concatena os conteúdos de um ou mais arquivos passados e exibe eles no terminal (stdout)

### EX:
~~~~bash
cat arquivo1.txt diretorio/arquivo2.txt
~~~~

## HEAD/TAIL
### HEAD
#### NOTAÇÃO
~~~~bash
head [opcional](-n <numero_linhas>) <caminho_arquivo>
~~~~

* Exibe um número `n` de linhas de um documento apartir de da primeiro linha.

#### EX:
~~~~bash
head -n 5 arquivo.txt
~~~~

### TAIL
#### NOTAÇÃO
~~~~bash
tail [opcional](-n <numero_linhas>) <caminho_arquivo>
~~~~

* Funciona da mesma forma que o `head`, porém a contagem começa no final do arquivo.

#### EX:
~~~~bash
tail -n 5 arquivo.txt
~~~~

* Em ambos os comandos, caso não seja passado o número de linhas, será exibido todas as linhas.

## MORE/LESS
* Ambos os comandos exibem os conteúdos de um arquivo como uma página, permitindo que veja um arquivo uma linha de cada vez ao invés de tudo de uma vez.

* Contudo é recomendado que utilize o `less`, pois ele faz tudo o que o `more` faz só que com mais alguns atributos.

* É recomendado que utilize o `more` em sistemas que não possuem o `less`

### NOTAÇÃO
~~~~bash
less [opcional](flags) <caminho_arquivo>
~~~~

### COMO UTILIZAR A PÁGINA INTERATIVA
comando|oque faz
:-----:|:------:
seta para baixo ou j|Abaixa a página em uma linha
seta para cima ou k|Sobe a página em uma linha
enter ou f|Avança uma página
b|Volta uma página
h|Menu de ajuda
q|Sair
|

### FLAGS
Flag|Função
:--:|:---:
-N|Faz com as linhas sejam numeradas

# VARIÁVEIS
## CRIAR
* É possível criar vairáveis no terminal do linux da seguinte forma.

~~~~bash
<nome_variavel>=<valor>
~~~~

### EX:
~~~~bash
nome=Tauã
~~~~

## USAR
* Para usar uma variável criada você deve utiliizar um símbolo de $ antes do nome dela

### EX:
~~~~bash
echo $nome
~~~~

# DIRETÓRIOS
## ROOT
* O root(raiz) é o diretório primário do sistema, é a partir dele que são criados os demais diretórios.
* Ele é representado pelo símbolo '/'