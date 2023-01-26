# Banco de Dados
O que é ? Linguagem usada para consultar Dados em um banco de dados

O que é dados?
Coleção de fatos como, fotos, palavras e números

Relacional


Banco de Dados é tudo e usamos todo dia é um repositório de dados.
Podendo ser salvo de várias formas como tabular, como planilhas que são colunas e linhas.
Porém nem todos usam formato tabular.

### DDL Data definition Language; Define, change, or drop data
### DML Data Manipulation Language; read and modify data

___
# Comandos Simples

## Create a table
_____
## Insert (inserir dados)
_____
## Select (seleciona dados de uma tabela) com clausula ORDER BY;
 * por exemplo, temos um data base de uma biblioteca e precisamos consultar alguns livros por ordem de titulo
 ~~~~
 db2 => select title from book
            order by title
 ~~~~
 E assim o resultado é exibido por ordem alfabetica
_____
### ORDER BY por ordem ascendente e descendente;
 * Ascendente
 ~~~
 db2 => select title from book
            order by title
 ~~~
 Desta maneira ele sempre vira como padrão ascendente 

 * Descendente por ordem Keyword 
 ~~~
 db2 => select title from book
            order by title desc
 ~~~
 * Por ordem Ascendente de números
 ~~~
 db2 => select title from book
            order by 2
 ~~~
 E assim acessando o número da coluna 2 


____
## Update (atualiza dados de uma tabela) 
____
## Delete (exclui dados de uma tabela)
____
## Count(É uma função de banco de dados integrada que recupera o número de linhas que correspodem aos critérios da consulta Exemplos; Para obter o total de linhas em uma dada tabela, select Count(*) from tablename) 
___
## Distinct é usado para remover valores duplicados de um conjunto de resultados. 
* Exemplos; para obter valores únicos em uma coluna;
~~~
 select DISTINCT columnname from tablename
 ~~~
 ~~~
 db2 => select country from author order by 1 
 ~~~ 
 E assim visualizamos resultados duplicados.

Já neste exemplo vemos o uso do DISTINCT
 ~~~
 db2 => select distinct(country) from author 
 ~~~
 Desta forma elimina valores duplicados.

## LIMIT que é usada para restringir o número de linhas obtidas do banco de dados,
* Exemplos; obtendo as primeiras 10 linhas de uma tabela;
~~~ 
select * from tablename LIMIT 10
~~~
____
# Funções de banco de dados integradas Aggregate ou Column
* INPUT: Grupo de valores 
* OUTPUT: Um único valor
Exemplos: SUM(), MIN(), MAX(), AVG(), etc.
Na Função SUM é usado para adicionar todos os valores em uma coluna
~~~ 
SUM(COLUMN_NAME)
~~~
Usaremos como exemplo um DB de uma petshop.
Exemplo: somar todos os valores na coluna  SALEPRICE:
~~~
select SUM (SALEPRICE) from PETSALE
~~~
Agora queremos chamar a coluna anterior na saida
~~~
select SUM(SALEPRICE) as SUM_OF_SALEPRICE from PETSALE
~~~
Na função MIN, retorna o valor mínimo.

Exemplo: obtenha a quantidade Minima da coluna ID para cães

~~~
select MIN(ID) FROM PETSALE where ANIMAL = 'Dog'
~~~


Na função MAX, retorna o valor máximo.

Exemplo: Obter a quantidade máxima de animais vendidos em uma única transação:
~~~
select MAX (QUANTITY) from PETSALE
~~~

Na função Average AVG() retorna o valor médio ou a média 

Exemplo: Para vermos o valor médio do preço de venda é:

~~~
select AVG(SALEPRICE) from PETSALE
~~~

Podemos realizar tambem operações matemáticas entre colunas e em seguida aplicar a função Aggregate.
Exemplo: Calcule o preço médio de venda por cão é:
~~~~
select AVG(SALEPRICE / QUANTITY) FROM PETSALE
where ANIMAL = 'Dog'
~~~~

Na função SCALAR realiza operações em valores individuais como: ROUND(), LENGHT(),UCASE, LCASE

Exemplo: Arredondar o valor de venda(SALEPRICE) para cima ou para baixo.
~~~~
select ROUND(SALEPRICE) FROM PETSALE
~~~~

Para valores em strings que são char e varchar LENGTH()
Exemplo:
~~~~
select LENGTH (ANIMAL) from PETSALE
~~~~

Em funções UCASE or LCASE serve para retornar valores em maiusculas ou minusculas de strings 

Exemplo: Retornar o valor ANIMAL maiusculas:
~~~~
select UCASE(ANIMAL) from PETSALE
~~~~

Funções SCALAR podem ser usadas em na clausula WHERE:
~~~~
select * from  PETSALE 
where  LCASE  (ANIMAL) = 'Cat'
 ~~~~

Também podendo usar uma função operate em outra função 
  Exemplo:
  ~~~~
  select DISTINCT (UCASE(ANIMAL)) from PETSALE
  ~~~~

## Funções DATE, TIME
Na maioria dos databases possuem tipos de dados especiais para datas e horas.

DATA: YYYYMMDD

TIME: HHMMSS

TIMESTAMP: YYYYXXDDHHMMSSZZZZZZ   X representa mês e Z microsegundos

FUNÇÕES DATE/TIME :
Há funções para obter o dia, mês, dia do mês, dia da semana, dia do ano, semana, hora, minuto e segundo.

Obter uma porção do dia de uma data:

~~~~
select DAY (SALEDATE) from PETSALE 
where  ANIMAL = 'Cat'
~~~~

________
# Banco de Dados na nuvem
### Vantagens de usar;
* Fácil de se usar,
 * Acesso de qualquer lugar com o uso de uma API de fornecedores ou interface web. 
 * Escalabilidade, pois será mais fácil de se expandir capacidade de armazenamento em Runtime, organizaçoes pagam pelo que usa. Recuperação de desastres, caso tenha uma falha de equipamento por desastre natural ou queda de energia, os dados sao recuperados de backups em servidores remotos.

 # Modelos de Informaçao e Modelos de Dados 
 Os modelos de informação e modelos de dados sao diferentes e servem para propositos diferentes.
 O modelo de informção está no nivel conceitual e define as relações entre os objetos, ja o modelo de dados são concretos e e específicos e incluem detalhes.

 O mais familiar é o hierarquico, tipicamente usado para mostrar gráficos de organização, organizando assim seus dados em uma estrutura de árvore, a raiz da árvore é o nó pai seguido pelos nós filhos. Um filho nao pode ter mais que um pai, porém um pai podem ter vários nós filhos. 
 









