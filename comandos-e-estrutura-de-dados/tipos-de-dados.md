---
description: >-
  Neste capítulo, você aprenderá a quais os tipos de dados podem ser armazenados em tabelas no seu banco de dados.
---

# Tipos de Dados

As tabelas de um banco de dados relacional são um conjunto de dados organizados em linhas e colunas. As colunas em um banco de dados são tipicamente os campos da tabela, e esses por sua vez possuem um tipo que identifica o formato do dado que esperamos receber e recuperar desse campo. 

Nas tabelas abaixo segue a descrição de alguns tipos de dados comuns em bancos SQL, porém o nome e os detalhes sobre esses dados podem variar de banco para banco devendo sempre consultar a documentação do mesmo.

## Tipos Numéricos
| Tipo | Descrição  | 
| - |:------------- |
| BIT(size) | Um valor que armazena um digito binário |
| INT(size) | Armazena números inteiros: o campo size especifica a quantidade de caracteres aceitos nesse campo |
| TINYINT(size) | O mesmo que o campo do tipo int porém armazena um limite de 0 a 255 |
| SMALLINT(size) | O mesmo que o campo do tipo int porém armazena um limite menor de valores |
| BIGINT(size) | O mesmo que campo do tipo int porém armazena uma quantidade maior de valores |
| FLOAT(size) | O campo float armazena números irracionais com casas decimais |
| BOOL | Armazena os valores 0 ou 1 que representam FALSE ou TRUE |

--

## Tipos Texto
| Tipo | Descrição  |
| - |:------------- |
| CHAR(size) | Uma string de tamanho fixo, no campo size deve informar o tamanho desejado, sendo o padrão 1 caractere |
| VARCHAR(size) | Uma string de tamanho variável, no campo size é informado um tamanho máximo para esse texto |
| TEXT | Campo para armazenar uma string que contém um texto, uma quantidade muito grande de caracteres. O tamanho pode variar de banco para banco mas em alguns pode armazenar até 2GB de texto |
| BINARY(size) | Parecido com o campo char mas armazena a string em um formato binario e o valor padrão do campo size é 1 |
| VARBINARY(size) | Parecido com o campo varchar mas armazena a string em um formato binario |
| BLOB | Um Blob (Binary Large OBjects) é um tipo de dado onde é possível adicionar um objeto convertido em binario, um exemplo seria armazenar um documento PDF|

--

## Tipos Data e Hora
| Tipo | Descrição  | Exemplo |
| - |:------------- |:------------- |
| DATE | Data no formato YYYY-MM-DD | 1994-07-15 |
| DATETIME | Data no formato YYYY-MM-DD hh:mm:ss | 1994-07-15 10:30:00 |
| TIMESTAMP | Data no formato de segundos a partir de '1970-01-01 00:00:00' UTC até '2038-01-19 03:14:07' UTC | 1577891410 (a representação em segundos da data 2020-01-01 10:10:10)
| TIME | Hora no formato hh:mm:ss | 10:30:00

--

Existem outros tipos que podem ser usados para armazenar de forma mais precisa os valores que desejamos ter na nossa tabela, alguns bancos especificam tipos para valores como dinheiro ou até imagens. Novamente, é necessário consultar a documentação para fazer o melhor uso desses campos.