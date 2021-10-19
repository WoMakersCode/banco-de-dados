# Operador IS NULL

O operador **NULL** é utilizado em banco de dados quando uma informação é desconhecida ou não aplicável. É uma palavra chave em banco de dados, que atribui valor **nulo** ao campo, ou seja, é um valor diferente de zero, espaço em branco ou ausência de caracteres.

### Sintaxe básica

```sql
SELECT coluna1, coluna2
FROM nome_tabela
WHERE coluna1 IS NULL;
```

Abaixo temos uma tabela com funcionários de uma empresa:

| id | nome | data_nascimento | telefone |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | '1985-02-02' | '(21) 99555-4455' |
| 2 |	Ester Daniela | null | '(51) 99999-8888' |
| 3 |	Márcio Felipe | null | '(11) 99999-1234' |
| 4 | Luana Gama | '1999-12-11' | ''(51) 99999-4321'' |
| 5 | João Gabriel | '2000-03-13' | '(21) 99999-6677' |
| 6 | Amanda Luiza | null  | '(51) 99999-8844' |
| 7 | Erick Daniel | ''  | '(51) 99999-8844' |

Vamos fazer uma pesquisa por todos os funcionários que estão com data de nascimento nula:

```sql
SELECT * FROM funcionarios
WHERE data_nascimento IS NULL;
```

| id | nome | data_nascimento | telefone |
| - |:-------------|:-----| --:|
| 2 |	Ester Daniela | null | '(51) 99999-8888' |
| 3 |	Márcio Felipe | null | '(11) 99999-1234' |
| 6 | Amanda Luiza | null  | '(51) 99999-8844' |

O resultado será composto apenas pelos funcionários que não possuem data de nascimento informada.

Note que no resultado não retornada a linha de **id 7** apesar de não ter informação de data de nascimento. Ao utilizar **IS NULL** para realizar a consulta SQL informamos ao banco de dados que queremos como retorno apenas as linhas que possuem data de nascimento **NULA**. Na linha de id 7 a data de nascimento é **vazia**, logo não é um valor **nulo**.


### IS NOT NULL

Podemos utilizar também a sintaxe **IS NOT NULL** para resgatar todos os resultados que não estão nulos.
Utilizando a mesma tabela anterior, vamos pesquisar por todos os funcionários que possuem data de nascimento informada:


```sql
SELECT * FROM funcionarios
WHERE data_nascimento IS NOT NULL;
```

| id | nome | data_nascimento | telefone |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | '1985-02-02' | '(21) 99555-4455' |
| 4 | Luana Gama | '1999-12-11' | ''(51) 99999-4321'' |
| 5 | João Gabriel | '2000-03-13' | '(21) 99999-6677' |
| 7 | Erick Daniel | ''  | '(51) 99999-8844' |

Serão retornados os quatro funcionários que possuem algum tipo de informação na coluna data_nascimento. 

Importante ressaltar que nessa pesquisa teremos também como resultado a linha de **id 7**, isso acontece pois a data de nascimento deste funcionário foi cadastrada em branco **''**, logo o banco de dados entende que o valor **não é nulo**.

### Order by de valores NULL

Quando utilizamos o **order by** para ordenar uma coluna que possui valores **NULL** o resultado terá diferença de acordo com o banco de dados que está sendo utilizado. Não existe um padrão de ordenação para **NULL**. Assim, os valores NULL podem ser adicionados tanto no inicio quanto ao final do resultado, dependerá do banco de dados que está sendo utilizado.

Alguns exemplos do comportamento utlizando **order by ASC**:

- PostgreSQL: Irá adicionar os valores **NULL** ao final do resultado.
- MySQL: Adiciona os valores **NULL** no inicio do resultado.
- SQL Server: Adiciona os valores **NULL** no inicio do resultado.

