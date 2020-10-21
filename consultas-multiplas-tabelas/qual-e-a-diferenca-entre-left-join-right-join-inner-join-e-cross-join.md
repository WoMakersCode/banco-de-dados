# Qual é a diferença entre Left Join, Right Join, Inner Join e Cross Join?

Para facilitar o entendimento, vamos usar como exemplo duas tabelas genéricas, sendo a primeira a TabelaA e a segunda a TabelaB.

# INNER JOIN
A claúsula do INNER JOIN permite usar um operador de comparação para comparar os valores de colunas provenientes de tabelas associadas, usando as cláusulas WHERE e FROM para especificar esse tipo de associação.Em outras palavras, ele apenas retorna algum resultado, se em ambas tabelas tiverem as "palavras chaves" correspondentes na cláusula ON do JOIN.

Ex: SELECT TabelaA. *, TabelaB. *
INNER JOIN TabelaB ON TabelaA.chave = TabelaB.chave

Ou seja, ele faz a junção entre duas tabelas, onde a projeção é todos os elementos que pussuem em ambas.

Outro exemplo, supondo que você esteja manipulando algum banco de dados de empresa e queira saber sobre os clientes cadastrados em determinadas lojas, ficaria uma query parecida com essa :

SELECT *    --- me traga todas as informações
FROM Clientes  --- da tabela clientes
INNER JOIN Lojas ON Cliente.idLoja = Lojas.idLoja  --- que tiverem em ambas tabelas

# LEFT JOIN
A claúsula LEFT JOIN permite além de obter os dados relacionados de duas tabelas, também os dados relacionados encontrados na tabela à esquerda da claúsula JOIN. Se caso não tiver dados relacionados a esquerda da tabela ele retornará nulo.

Usando nosso exemplo de tabelas, ele retornará todos os registros da TabelaA, sendo que da TabelaB só será retornados os registros que tiverem alguma relação de igualdade com a cláusula do JOIN.

Ex: SELECT TabelaA. , TabelaB.
    FROM TabelaA LEFT JOIN TabelaB ON TabelaA.chave = TabelaB.chave

Outro exemplo, supondo que você queira saber o sálario dos funcionários que você tem na empresa, segundo os cargos que estão ocupados, a query ficaria assim:

SELECT C.NOMECARGO [CARGO], F.SALARIOFUNCIONARIO AS [SALÁRIO]
FROM CARGO AS C
LEFT JOIN FUNCIONARIO AS F ON C.IDCARGO = F.IDCARGO

assim ele retornaria os cargos e salários que você possui naquele momento, e o cargo que não possuisse ninguém registrado retorna NULL(nulo).

# RIGHT JOIN 
Ao contrário do LEFT JOIN, essa clásula retorna os valores que forem encontrados na tabela a direita do JOIN. Segue a mesma lógica caso não tenha a informação, retornando NULO (NULL).


Ex: SELECT TabelaA. , TabelaB.
    FROM TabelaB RIGHT JOIN TabelaA ON TabelaB.chave = TabelaA.chave

assim ela faz o comparativo da tabela da direita com a esquerda, e retorna todos os valores da TabelaB e os valores da TabelaA que corresponderem a consulta.

# CROSS JOIN
Nesta clásula, todos os dados da esquerda do JOIN são cruzados com os dados da tabela á direita de JOIN por meio do CROSS JOIN, também conhecido como produto cartesiano. É possível cruzarmos informações de duas ou mais tabelas.

Basicamente, o resultado de uma query que use essa cláusula, fica da seguinte forma, para cada linha da TabelaA são retornados todas as linhas da TabelaB. Seria como um "JOIN sem cláusula ON", ou seja. todas as combinações de linhas A e B são devolvidas.

E se caso, você usar um ON nessa clásula, ele retorna um simples INNER JOIN.

Um exemplo de uma query que use isso seria :

SELECT TabelaA., TabelaB.
FROM TabelaA
CROSS JOIN TabelaB


como resultado dessa query, para cada linha da TabelaA, viria como retorno todas as linhas da TabelaB. Vale atentar-se para uma observação, todos os campos pedidos no select retornará, independente de existirem para aquela linha específica. Se o conteúdo da linha for NULL, essa mesma retornará apenas para uma das tabelas.