# Utilizando a Cláusula WHERE

A cláusula **WHERE** é utilizada para filtrar registros em uma tabela. Ela extraí os registros que atendam a uma condição específica.

Sintaxe base:

```sql
SELECT coluna1, coluna2
FROM nome_tabela
WHERE condicao;
```

> Nota: A cláusula **WHERE** pode ser utilizada em instruções _SELECT_, _UPDATE_, _DELETE_ e etc.!

Abaixo uma tabela de funcionários de uma empresa, que será utilizada em nossos exemplos:

| id  | nome            | cargo                    | salario |
| --- | :-------------- | :----------------------- | ------: |
| 1   | Tereza Cristina | Desenvolvedora           |    5794 |
| 2   | Ester Daniela   | Gerente de Projetos      |    6158 |
| 3   | Márcio Felipe   | Analista de Negócios     |    5220 |
| 4   | Ester Gama      | Coordenador de Sistemas  |    7500 |
| 5   | João Gabriel    | Gerente de Projetos      |    7000 |
| 6   | Tereza Cristina | Coordenadora de Sistemas |    9500 |

### Exemplo de consulta **WHERE com valor em texto**:

A instrução SQL abaixo, seleciona todos os funcionários que possuam o cargo _Desenvolvedora_:

```sql
SELECT * FROM funcionarios
WHERE cargo = 'Desenvolvedora';
```

Resultado da consulta:

| id  | nome            | cargo          | salario |
| --- | :-------------- | :------------- | ------: |
| 1   | Tereza Cristina | Desenvolvedora |    5794 |

### Exemplo de consulta **WHERE com valor numérico**:

A instrução abaixo seleciona todos os funcionários que possuam o salário de _7000_:

```sql
SELECT * FROM funcionarios
WHERE salario = 7000;
```

Resultado da consulta:

| id  | nome         | cargo               | salario |
| --- | :----------- | :------------------ | ------: |
| 5   | João Gabriel | Gerente de Projetos |    7000 |
