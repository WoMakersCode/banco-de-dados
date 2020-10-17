# O que é um banco de dados?

São coleções de informações que se relacionam de forma que crie um sentido. São de vital importância para empresas. Podemos dizer que é a principal peça dos sistemas de informações de um empresa.

Outra explicação seria, que é uma coleção de dados que interligados entre si e organizados podem fornecer alguma informação.

O que não podemos é confundir dados com informações, pois :

 - dados: são a formas brutas, primárias, e sozinhas muitas vezes não fazem sentido.
 - informações: são agrupamento de dados que de forma organizada fazem sentido, geram conhecimento.

Por exemplo, 2020 só o número não faz sentido nenhum, mas se agrupar ele a alguns outros dados pode se tornar uma informação "2020 o ano em que estamos no momento da criação deste repositório".

Ai podemos incluir um conhecimento a mais também, que é o termo "metadado", que usando o exemplo dado "o ano em que estamos no momento da criação deste repositório" é um metadado, pois ele é um dado sobre o dado "2020". Um exemplo bem comum de se encontrar na vida real, é quando temos uma tabela "cliente", e nele encontramos campos como "nome" que tem como metadados: "telefone", "endereço", entre outros.

Nisso podemos concluir que um banco de dados é um conjunto de dados e metadados, que organizados, podemos extrair informações.

E hoje em dia existem diversos tipos de SGBD's (Sistemas de Gerenciamento de Banco de Dados), ex: Oracle, BD2, MySQL, SQL Server, PostgreSQL, MongoDB, entre outros.

Entre esses SGBD's existem os relacionais e os não relacionais.
 - relacionais : são criados no paradigma da orientação a conjuntos. Dessa forma os dados são armazenados em tabelas, e cada tabela terá atributos ou registros responsáveis por organizar as informações. A linguagem usada nesse formato é o SQL, Structured Query Language. É comum o uso dele quando o sistema é um CRM's ou ERP.

 - não-relacionais: são responsáveis por atender a demandas que o modelo relacional não consegue atender ou suprir. Exemplo disso é quando a demanda são dados misturados, como mistura de tabelas, imagens e mapas e que não pooderão ser tabulados em linha e colunas em uma tbela. Esse tipo de solução tem como princípio o uso de serviços de nuvem, e a linguagem usada nesse formato é o NoSQL, Not Only SQL. Um dos mais conhecidos nesse caso é o MongoDB. 