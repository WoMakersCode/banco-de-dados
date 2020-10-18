# Cláusula ORDER BY

A cláusula **ORDER BY** é utilizada para ordernar o resultado de uma consulta em SQL, a ordenação pode ser em ordem ascendente (ASC) ou descendente (DESC), sendo o default da ordenação *ascendente*.
Para ordernar a sua consulta em ordem descendente utilize a cláusula **ORDER BY DESC**.

Sintaxe base:

```sql
SELECT coluna1, coluna2
FROM nome_tabela
ORDER BY coluna1, coluna2 ASC ou DESC;
```

Abaixo é uma tabela com funcionários de uma empresa:

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | Desenvolvedora | $5794 |
| 2 |	Ester Daniela | Gerente de Projetos | $6158 |
| 3 |	Márcio Felipe | Analista de Negócios | $5220 |
| 4	|      Ester Gama | Coordenador de Sistemas | $7500 |
| 5	|    João Gabriel | Gerente de Projetos | $7000 |
| 6	| Tereza Cristina | Coordenadora de Sistemas  | $9500 |

### Ordenação ascendente:

Para selecionar funcionários por ordem ascendente dos nomes utilizamos:

```sql
SELECT * FROM funcionarios
ORDER BY nome;
```

Resultado da consulta:

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 |	Ester Daniela | Gerente de Projetos | $6158 |
| 2	|      Ester Gama | Coordenador de Sistemas | $7500 |
| 3	|    João Gabriel | Gerente de Projetos | $7000 |
| 4 |	Márcio Felipe | Analista de Negócios | $5220 |
| 5 | Tereza Cristina | Desenvolvedora | $5794 |
| 6	| Tereza Cristina | Coordenadora de Sistemas  | $9500 |


### Ordenação descendente:

Para selecionar funcionários por ordem descendente dos nomes utilizamos:

```sql
SELECT * FROM funcionarios
ORDER BY cargo DESC;
```

Resultado da consulta:

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | Coordenadora de Sistemas  | $9500 |
| 2 | Tereza Cristina | Desenvolvedora | $5794 |
| 3 |	Márcio Felipe | Analista de Negócios | $5220 |   
| 4	|    João Gabriel | Gerente de Projetos | $7000 |
| 5	|      Ester Gama | Coordenador de Sistemas | $7500 |
| 6 |	Ester Daniela | Gerente de Projetos | $6158 |
 

### Ordenação com mais de uma coluna:

Abaixo uma seleção com o nome dos funcionários e seu cargo em ordem ascendente. Isso significa que ele ordena por nome, mas se alguma linha possuir o nome repetido, a ordem será por ascendencia do cargo:

```sql
SELECT * FROM funcionarios
ORDER BY nome, cargo;
```

Resultado da consulta, podemos notar que a funcionária Tereza Cristina que possui o cargo Coordenadora de Sistemas foi para a quinta posição, pois o cargo foi considerado na ordenação ascendente:

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 |	Ester Daniela | Gerente de Projetos | $6158 |
| 2	|      Ester Gama | Coordenador de Sistemas | $7500 |
| 3	|    João Gabriel | Gerente de Projetos | $7000 |
| 4 |	Márcio Felipe | Analista de Negócios | $5220 |
| 5	| Tereza Cristina | Coordenadora de Sistemas  | $9500 |
| 6 | Tereza Cristina | Desenvolvedora | $5794 |

### Ordenação com mais de uma coluna exemplo 2:

O exemplo abaixo, seleciona funcionários por nome e cargo, considerando que o nome é ascendente e que o cargo é descendente:

```sql
SELECT * FROM funcionarios
ORDER BY nome ASC, cargo DESC;
```

Resultado da consulta:

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 |	Ester Daniela | Gerente de Projetos | $6158 |
| 2	|      Ester Gama | Coordenador de Sistemas | $7500 |
| 3	|    João Gabriel | Gerente de Projetos | $7000 |
| 4 |	Márcio Felipe | Analista de Negócios | $5220 |
| 5 | Tereza Cristina | Desenvolvedora | $5794 |
| 6	| Tereza Cristina | Coordenadora de Sistemas  | $9500 |
