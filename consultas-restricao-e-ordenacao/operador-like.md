# Operador LIKE

O operador **LIKE** é utilizado em consultas SQL para permitir a busca de informações tendo como parametro de comparação um valor textual. Com o uso do **LIKE**, é possivel encontrar os registros considerando uma determinada palavra ou um certo trecho de caracteres.

### Sintaxe básica

```sql
SELECT coluna1, coluna2
FROM nome_tabela
WHERE coluna LIKE 'texto';
```

Abaixo é uma tabela com funcionários de uma empresa:

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | Desenvolvedora | $5794 |
| 2 |	Ester Daniela | Gerente de Projetos | $6158 |
| 3 |	Márcio Felipe | Analista de Negócios | $5220 |
| 4	| Ester Gama | Coordenador de Sistemas | $7500 |
| 5	| João Gabriel | Gerente de Projetos | $7000 |
| 6	| Tereza Cristina | Coordenadora de Sistemas  | $9500 |

Vamos fazer uma pesquisa por nome:

```sql
SELECT * FROM funcionarios
WHERE nome LIKE 'Tereza Cristina';
```

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | Desenvolvedora | $5794 |
| 6	| Tereza Cristina | Coordenadora de Sistemas  | $9500 |

O resultado será composto apenas pelos funcionários que possuirem o nome cadastrado exatamente como difinido na pesquisa SQL.

### Caracteres coringa

As consultas utilizando o operador **LIKE** podem ser mais efetivas quando usamos uma combinação de caracteres coringas para compor as strings de comparação. O SQL nos oferece dois caracteres coringa: **%** e **_** (sublinhado).

#### Caracter **%**

O caracter **%** indica que pode retornar qualquer texto no resultado da pesquisa. A sintaxe de uso seria a seguinte:

- **%texto%**: Ao utilizar o caracter **%** antes e depois do __texto__, informamos ao SQL que desejamos receber todos os resultados que possuem o __texto__ informado. Por exemplo: 

```sql
SELECT * FROM funcionarios
WHERE nome LIKE '%ter%';
```

Resultado da consulta será:

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | Desenvolvedora | $5794 |
| 2 |	Ester Daniela | Gerente de Projetos | $6158 |
| 4	| Ester Gama | Coordenador de Sistemas | $7500 |
| 6	| Tereza Cristina | Coordenadora de Sistemas  | $9500 |

São retornados todos os funcionários que possuem os caracteres **ter** no nome (TEReza, esTER).

- **%texto**: Outra opção é utilizar o caracter **%** apenas no inicio oa expressão de busca. Nesse caso serão retornados apenas os resultados que possuirem o valor do campo terminando com o __texto__. 

```sql
SELECT * FROM funcionarios
WHERE cargo LIKE '%Projetos';
```

Resultado da consulta será:

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 2 |	Ester Daniela | Gerente de Projetos | $6158 |
| 5	| João Gabriel | Gerente de Projetos | $7000 |

São retornados todos os funcionários que possuem a palavra **Projetos** no final do seu cargo.

- **texto%**: A terceira forma é utilizar o caracter **%** apenas no final oa expressão de busca. Nesse caso serão retornados apenas os resultados que possuirem o valor do campo iniciando com o __texto__. 

```sql
SELECT * FROM funcionarios
WHERE cargo LIKE '%Analista';
```

Resultado da consulta será:

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 3 |	Márcio Felipe | Analista de Negócios | $5220 |

São retornados todos os funcionários que possuem a palavra **Analista** no inicio do seu cargo.

#### Caracter **_**

O caracter sublinhado **_** permite a realização de pesquisas mais exatas nos campos das tabelas. A utilização deste caracter permite a busca de um termo especifico considerando apenas um caracter como coringa. Vejamos exemplos.

- **_ala**: O resultado será o conjunto de todos os termos que terminem com __ala__ e tenham 1 caracter qualquer no começo. Será possível ter registros como bala, mala, pala, tala etc.

- **b_m**: O resultado será de itens que iniciem com a letra B, possuam qualquer caracter logo após e terminem com a letra M.

- **menin_**: O resultado será de registros que iniciam com __menin__ e possuem qualquer caracter final, podendo ser menina, menino, menine etc.

**Dica** - É possivel combinar os caracteres especiais para otimizar as consultas, criando termos de pesquisa mais efetivos e que atendam a necessidade do projeto, por exemplo:

```sql
SELECT * FROM funcionarios
WHERE cargos LIKE '_e%';
```

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | Desenvolvedora | $5794 |
| 2 |	Ester Daniela | Gerente de Projetos | $6158 |
| 5	| João Gabriel | Gerente de Projetos | $7000 |

O resultado será o conjunto de cargos que iniciam com qualquer caracter, depois possuem a letra __E__ e finalizam com qualquer grupo de caracteres. 
