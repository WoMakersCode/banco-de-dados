# Utilizando Alias de Tabela

Um dos desafios quando se está trabalhando com multiplas tabelas é organizar e identificar os atributos de forma clara. Um do caminhos para esta organização é a utilização de **Alias** (pseudônimos) para as tabelas e colunas. 

Com o uso de um **alias** é possível tornar mais clara e simples a composição de um comando SQL, sendo um bom caminho quando existem nomenclaturas de tabelas muto longas ou complexas. 

É possível utilizar qualquer termo como alias, normalmente será um termo mais curto e amigável, servindo tanto para realizar uma junção (_join_) de tabelas como para retornar títulos de colunas de forma mais intuitiva. 

#### Sintaxe Básica

A sintaxe utiliza a cláusula **AS** para informar o alias no SQL. Vejamos exemplos:

```sql
SELECT coluna1 AS alias_coluna
FROM nome_tabela AS alias_tabela
WHERE coluna = id ;
```

Vamos considerar as seguintes tabelas para nossos exemplos:

 **Tabela:** funcionarios

| id | name | job | salary |
| - |:-------------|:-----| --:|
| 1 | Tereza Cristina | Desenvolvedora | $5794 |
| 2 |	Ester Daniela | Gerente de Projetos | $6158 |
| 3 |	Márcio Felipe | Analista de Negócios | $5220 |
| 4	| Ester Gama | Coordenador de Sistemas | $7500 |
| 5	| João Gabriel | Gerente de Projetos | $7000 |
| 6	| Tereza Cristina | Coordenadora de Sistemas  | $9500 |

**Tabela:** phone
| id | id_worker | phone_number | 
| - |:-----|:-----| 
| 1 | 2 | +55539993421| 
| 2 |	2 | +55629821726 |
| 3 |	1 | +1 45 5557382 |
| 4	| 3 | +558264837171 |
| 5	| 5 | +552194813847 |


#### Exemplo de utilização

**Ex.1** Selecionar o nome do funcionário com id = 1: 

```sql
SELECT f.name AS 'Nome do funcionário'
FROM funcionarios AS f
WHERE f.id = 1;
```

| Nome do funcionário | 
|:-------------|
|Tereza Cristina |


Neste exemplo o resultado será apenas o nome do funcionário que possui id=1. 

**Ex.2** Selecionar o nome do funcionário de id=2 e o número de telefone

```sql
SELECT f.name AS 'Nome do funcionário', p.phone_number AS 'Telefone'
FROM funcionarios AS f, phone AS p
WHERE f.id = 1;
```

| Nome do funcionário | Telefone |
|:-------------|:-------------|
|Ester Daniela |  +55539993421 |
|Ester Daniela |  +55629821726 |

O resultado desta consulta irá retornar duas linhas pois a funcionárioa possui dois números de telefone cadastrados.

Neste segundo exemplo utilizamos o **Alias** como forma desanbiguar a coluna **id** pois ambas as tabelas possuem esta informação e o SQL não saberia em qual das tabelas buscar a informação se na cláusula **where** não fosse indicado qual a tabela.
