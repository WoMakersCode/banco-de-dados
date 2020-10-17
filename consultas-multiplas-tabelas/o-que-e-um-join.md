# O que é um JOIN?

A cláusula JOIN é usada em operações de junção em álgebra relacional, basicamente ela combina dados de mais de uma tabela do banco de dados para conseguir o resultado da query. Essa consulta ocorre da seguinte forma, ele consulta valores em comum com cada tabela, e pode ser tanto criado uma nova tabela com o resultado quanto usado essa informação como esta.

No SQL padrão temos alguns tipos de JOIN: INNER, LEFT, RIGHT, FULL OUTER e CROSS.

Para entender melhor, vamos de exemplo:
 - supondo que você tenha duas tabelas:
    -  uma sendo Cliente,
    -  e outra Pedidos.

 - é possível usando o JOIN, especificar quais colunar das tabelas serão associadas. Para isso vamos definir uma chave estrangeira de uma tabela e a chave relacionada em outra tabela. Esses valores serão comparados com operadores lógicos, podemos usar o FROM como uma clásula para especificar a associação e o WHERE para referenciar as condições de buscas.

 - usando esse exemplo o query ficaria assim:
    SELECT * --- selecionar tudo
    FROM CLIENTES AS C --- determinando a tabela CLIENTES como sendo C
    JOIN PEDIDOS AS P ON C.IDCLIENTE = P.IDPEDIDO  --- condição da consulta usando operadores lógicos

Lembrando que nesse exemplo acima, não foi citado qualificações no SELECT, pois é apenas um exemplo de uso do JOIN, porém, é recomendado o que use a qualificação para identifcar coluna/tabela que será consultada.

Um exemplo disso, seria um SELECT assim:
    SELECT CLIENTES.IDCLIENTE, CLIENTES.NOME, PEDIDOS.DESCRICAO, PEDIDOS.VALOR --- tabela e coluna a ser consultados
    FROM CLIENTES, PEDIDOS --- tabelas que serão consultados
    WHERE CLIENTES.IDCLIENTE = PEDIDOS.IDPEDIDO AND PEDIDOS.VALOR > 50.00 --- condições da consulta usando operadores lógicos.

Essa associação segue uma sequência, onde a primeira clásula a ser "ouvida" é o FROM, depois aplica-se as condições do WHERE e por fim o HAVING (não foi citado aqui).