---
description: >-
  Neste capítulo, você aprenderá a recuperar dados em uma tabela usando a
  instrução SQL SELECT.
---

# Comando Select

## Introdução à instrução SQL SELECT

O SQL fornece a instrução `SELECT` que permite recuperar uma ou mais linhas de dados em uma tabela. 

Vamos imaginar que no nosso banco de dados existe uma tabela chamada `funcionarios` que armazena informações de identificador, nome, cargo e salário das pessoas que trabalham na empresa.

| id | nome | cargo | salario |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | Desenvolvedora | $5794 |
| 2 |	Ester Daniela | Gerente de Projetos | $6158 |
| 3 |	Márcio Felipe | Analista de Negócios | $5220 |

--

### Executando o comando SELECT

Abaixo temos a sintaxe básica de um comando `SELECT`, nela precisamo informar quais colunas da tabela queremos retornar e de qual tabela estamos falando.

Nesse caso queremos receber (`SELECT`) o nome e o cargo de todos os registros da tabela (`FROM`) funcionarios.
```sql
SELECT nome, cargo FROM funcionarios
```

O resultado esperado é o seguinte: 

| nome | cargo |
| - |:-------------|
| Tereza Cristina | Desenvolvedora |
| Ester Daniela | Gerente de Projetos |
| Márcio Felipe | Analista de Negócios |

--

As vezes queremos recuperar todos os campos dos registros da tabela, em tabelas pequenas é simples especificar todos os campos mas em tabelas com muitas colunas podemos usar uma sintaxe que permite de forma resumida dizer que queremos retornar todos de uma só vez e para isso usamos o `*` no lugar do nome das colunas.

```sql
SELECT * FROM funcionarios
```
Esse `SELECT` vai retornar todos os registros da tabela com todas as colunas.

--

O `SELECT` é o comando que nos permite recuperar os dados que temos armazenados no nosso banco e ele pode ser combinado com outros comando diferentes para trazer dados cada vez mais refinados das nossas tabelas. O exemplo a seguir combina o `SELECT` com o comando `WHERE` (onde) para recuperar da tabela quando a comparação descrita retorna verdadeiro.

```sql
SELECT nome, cargo, salario
FROM funcionarios 
WHERE cargo = "Desenvolvedora"
```
Para essa query temos como resultado esperado o registro abaixo.

| nome | cargo | salario |
| - |:------------- | --:|
| Tereza Cristina | Desenvolvedora | $5794 |