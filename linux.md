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
    * [touch](#touch)
    * [mkdir](#mkdir)
    * [mv](#mv)
    * [rm](#rm)
    * [cp](#cp)
    * [grep](#grep)
    * [find](#find)
* [Variáveis](#variáveis)
* [Diretŕios](#diretórios)

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

## TOUCH
### NOTAÇÃO
~~~~BASH
touch <arquivo> [opcional](outro_arquivo)
~~~~

* Esse comando atualiza o acesso e o timestamp do arquivo. Caso o arquivo não exista, ele irá criar um novo com o memsmo nome e extensão passada.

* Você pode atualizar/criar mútiplos arquivos de uma só vez usando o mesmo comando.

* O comando em si é mais utilizado para criar novos arquivos.

## MKDIR
### NOTAÇÃO
~~~~bash
mkdir <diretorio>
~~~~

* Abreviação de `Make Directory`, ele cria um diretório com o mesmo nome passado no argumento do comando. 

## MV
#### NOTAÇÃO
~~~~bash
mv <origem_arquivo> <caminho_destino>
~~~~
* Abreviação de `Move`, ele move um deteminado arquivo para um outro local.

### EX1:
~~~~bash
mv arquivo.txt outroDiretorio/
mv arquivo.txt outroDiretorio/arquivo.txt
mv arquivo.txt ../arquivo.txt
~~~~

* Além disso, esse comando é também usado para renomear arquivos.

### EX2:
~~~~bash
mv arquivo.txt novoNome.txt
mv arquivo.txt diretorio/novoNome.txt
~~~~

* Caso deseje apenas mover um arquivo sem renomea-lo, basta omitir o nome do arquivo no final do caminho de destino.

## RM
### NOTAÇÃO
~~~~bash
rm [opcional](flags) <arquivo>
~~~~

* Abreviação de `remove`, esse comando remove um determinado arquivo ou diretório vazio do sistema.

### EX:
~~~~bash
rm arquivo.txt
rm diretorio/arquivo.txt
rm diretorioVazio/
~~~~

### FLAGS
Flag|O que faz
:--:|:----:
-r| Remove recursivamente todos os arquivos(incluindo subdiretórios) de um diretoŕio

#### EX:
~~~~bash
rm -r diretorio
~~~~

## CP
#### NOTAÇÃO
~~~~bash
cp [opcional](flags) <arquivo> <destino/>
~~~~

* Abreviação de `copy`, esse comando copia um determinado arquivo de um lugar para outro.

### EX:
~~~~bash
cp arquivo.txt diretorio/
cp arquivo.txt ../
cp ../diretorio/arquivo.txt ./
~~~~

### FLAGS
Flag|O que faz
:---:|:------:
-R|Copia recursivamente um todos os conteúdos de um diretório em outro diretório
|

#### EX:
~~~~bash
cp -R diretorio/ outroDiretorio/
~~~~

## GREP
### NOTAÇÃO
~~~~bash
grep [opcional](flags) <texto_procura> <arquivo> [opcional](outros_arquivos)
~~~~

* O comando funciona permite pesquisar determinada string em 1 ou mais arquivos, retornoando as linhas que a possue.

### EX: 
~~~~bash
grep "olá" words.txt
grep "olá" saudacao1.txt saudacao2.txt
~~~~

### FLAGS
Flag|O que faz
:---:|:------:
-r|pesquisa recursicamente em um diretŕoio inteiro(incluindo subdiretorios) pela string passada
|

#### EX:
~~~~bash
grep -r "olá" ./diretorio
~~~~

## FIND
### NOTAÇÃO
~~~~bash
find <diretorio> -name <nome_arquivo>
~~~~

* Esse comando procura por um determinado arquivo no diretório especificado

## EX:
~~~~bash
find diretorio -name ola.txt
~~~~

* Tambem é possível usar expressões de padrão para pesquisar arquivos de forma mais precisa.

## EX:
~~~~bash
find ../diretorio -name "*.txt" # Procura todos os arquivos terminados em .txt
~~~~

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

# TABELA PADRÕES DE COMBINAÇÃO

Caracteres|Função
:-------:|:-----:
*|Procura por uma ou mais ocorrencias
?|Procura por uma ou mais ocorrencias, retornando apenas a primeira
[]|Serve para listar os caracteres de procura

