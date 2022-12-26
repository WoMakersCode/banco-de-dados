# Utilizando o LIMIT

O operador LIMIT é utilizado para limitar a quantidade de dados que serão exibidos em uma *view*.

Quando desejamos visualizar os dados de uma base mas apenas algumas linhas de uma tabela, por exemplo, podemos usar esse operador. Veja um exemplo abaixo:

```sql
SELECT *
  FROM hotel
 LIMIT 10;
```
Neste exemplo, selecionamos todas as colunas da tabela **hotel**, mas limitando a visualização a apenas 10 resultados.

É importante pontuar que o operador LIMIT vem sempre por último quando escrevemos um código em SQL.

Quando interpretar o código escrito, em primeiro lugar, o SQL verá de qual tabela se deseja extrair dados, em seguida verá se existem condições para essa extração, por exemplo, se serão selecionadas algumas ou todas as colunas de uma tabela, e em seguida lerá o operador que limita a quantidade de dados a ser exibida.

Vejamos mais um exemplo de como o LIMIT pode ser usado:

```sql
SELECT nome, idade, altura
  FROM cadastro_academia
 WHERE idade > 25
 LIMIT 15;
 ```

 No caso dessa visualização teremos como saída de dados, os nomes, idades e alturas de 15 pessoas da tabela cadastro_academia, cuja idade é maior do que 25 anos.

 Sendo assim, quem definiu e teve prioridade para restringir a visualização de dados foi o operador WHERE e o operador LIMIT finalizou a restrição ao informar para o SQL que a saída de dados exibiria apenas quinze linhas dessa tabela, nessas condições específicas.