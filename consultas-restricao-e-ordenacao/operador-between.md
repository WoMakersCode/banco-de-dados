# Operador BETWEEN

O operador **BETWEEN** seleciona valores contidos em um intervalo definido. Este valor pode ser numérico, texto ou uma data.
É um operador inclusivo, isso significa que ele inclui os valores definidos no intervalo. 

Temos também o **NOT BETWEEN**, que exclui os valores que estão no intervalo, assim como BETWEEN recebe valores numéricos, texto ou datas. É exclusivo, isso significa que ele excluí os valores do intervalo da consulta.

Em ambos o valor inicial e final devem ser sempre defindos.

Sintaxe base:

```sql
SELECT coluna1, coluna2
FROM nome_tabela
WHERE coluna1 BETWEEN valor1 AND valor2;
```

Abaixo uma tabela com produtos, que será utilizada nos nossos exemplos:

| id  |   nome    | unidade | preco |
| :-: | :-------: | :------ | :---- |
|  1  |   lápis   | 1       | 2     |
|  2  |  caneta   | 1       | 2.59  |
|  3  |  caderno  | 1       | 20    |
|  4  | borracha  | 1       | 1     |
|  5  | corretivo | 1       | 2.5   |
|  6  | lapiseira | 1       | 1.65  |

### BETWEEN exemplo com valor numérico:

A instrução SQL abaixo seleciona todos os produtos em que o preço esteja entre 1 e 2, incluíndo os valores do intervalo:

```sql
SELECT * FROM produtos
WHERE preco BETWEEN 1 AND 2;
```

Resultado:

| id  |   nome    | unidade | preco |
| :-: | :-------: | :------ | :---- |
|  1  |   lápis   | 1       | 2     |
|  4  | borracha  | 1       | 1     |
|  6  | lapiseira | 1       | 1.65  |

### NOT BETWEEN exemplo com valor numérico:

Para exibir produtos que não estão no intervalo definido, podemos utilizar o NOT BETWEEN, abaixo um exemplo:

```sql
SELECT * FROM produtos
WHERE preco NOT BETWEEN 1 AND 2;
```

O resultado da consulta são os itens que não estão no intervalo entre 1 e 2, excluíndo os valores do intervalo:

| id  |   nome    | unidade | preco |
| :-: | :-------: | :------ | :---- |
|  2  |  caneta   | 1       | 2.59  |
|  3  |  caderno  | 1       | 20    |
|  5  | corretivo | 1       | 2.5   |

### BETWEEN exemplo com valor em texto:

A instrução SQL abaixo, seleciona todos os produtos em que o nome esteja entre as linhas _caneta_ e _corretivo_:

```sql
SELECT * FROM produtos
WHERE nome BETWEEN 'caneta' AND 'corretivo';
```

Quando utilizamos o **BETWEEN com valores em texto**, estamos instruindo nossa consulta a pegar as linhas que estão entre os valores definidos, no resultado abaixo é notável que as linhas selecionadas são as que estão entre os nomes _caneta_ e _coretivo_, com os valores do intervalo incluídos:

| id  |   nome    | unidade | preco |
| :-: | :-------: | :------ | :---- |
|  2  |  caneta   | 1       | 2.59  |
|  3  |  caderno  | 1       | 20    |
|  4  | borracha  | 1       | 1     |
|  5  | corretivo | 1       | 2.5   |

### NOT BETWEEN exemplo com valor em texto:

A instrução SQL abaixo, seleciona todos os produtos em que o nome não esteja entre as linhas _caneta_ e _corretivo_:

```sql
SELECT * FROM produtos
WHERE nome NOT BETWEEN 'caneta' AND 'corretivo';
```

Assim estamos instruindo nossa consulta a pegar as linhas que não estão entre os valores definidos, no resultado abaixo é notável que as linhas selecionadas são as que não estão entre os nomes _caneta_ e _coretivo_, com os valores do intervalo excluídos:

| id  |   nome    | unidade | preco |
| :-: | :-------: | :------ | :---- |
|  1  |   lápis   | 1       | 2     |
|  6  | lapiseira | 1       | 1.65  |
