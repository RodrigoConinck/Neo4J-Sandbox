# Neo4J-Sandbox

## Conceitos Básicos
### Nodes (p:Person)
Representam entidades do banco, são como as linhas de um banco relacional. Devem ser escritos entre parênteses, onde **p** é a variável e **Person** o tipo.

### Relações [p:Play]
Representa as relações entre os nodes, deve ser escrito entre chaves, onde **p** é a variável e **Play** indica o tipo da relação.

### Labels :labels
São nomes/identificadores para as relações e nodes, possuim o prefixo `:` e devem ser usadas depois de variáveis

### Propriedades p.prop
Utilizadas para adicionar atributos nos nodes e relacionamentos. Onde **p** representa a variável da entidade e **prop** o nome da propriedade

## Principais comandos
### Create
Utilizado para criar nodes/relações. O comando abaixo irá criar um node do tipo `Person`, com a propriedade `name` com valor Patrick<br>
![image](https://user-images.githubusercontent.com/61787168/195723099-693a34fa-0e89-4b93-958f-91965ffa687b.png)
<br>
Já este comando vai criar uma relação de saída (denotado pela direção da seta) `:PLAYED` entre os nodes existentes Person e Game, retornando o tipo de relacionamento.<br>
![image](https://user-images.githubusercontent.com/61787168/195988682-7e5b588a-38ee-4f7e-9bef-6de4a14dce2d.png)

### Match
É utilizado para buscar nodes que correspondem a um padrão específico.<br>
![image](https://user-images.githubusercontent.com/61787168/195723267-a502c1ba-32bf-4bb0-9467-8b9b9959f079.png)
<br>O exemplo acima é um jeito básico de fazer a busca, no qual está limitado a fazer comparações simples entre strings. Para filtrar os resultados mais efetivamente, deve ser usado a cláusula **WHERE** junto de operadores de comparação `Starts With, Ends, >, <, etc`.<br>
![image](https://user-images.githubusercontent.com/61787168/195723736-f336a75c-3c09-404b-a753-91bda0ab472e.png)<br>
![image](https://user-images.githubusercontent.com/61787168/195723898-8d232e30-e04e-4540-a7b6-1813f3162d5f.png)

### Merge
É usado para buscar nodes existentes e relacioná-los ou então para criar novos nodes e relacioná-los. Ele basicamente é um combinação do **Match** e do **Create**, permitindo também realizar comandos adicionais quando os dados forem achados/criados.<br>
![image](https://user-images.githubusercontent.com/61787168/195988143-4135e8e1-59c5-4179-82e8-654ccc15a32d.png) <br>
Esse comando, vai criar o node `Person` caso não exista e configurar a propriedade `createdAt` com o horário atual, mas se ele já exisitir, vai apenas configurar a propriedade `lastLoggedInAt` no horário atual.

### Set
Ele funciona como o `UPDATE` do SQL. Permite que façamos alteração em nodes existentes. O exemplo abaixo vai buscar pela pessoa **Patrick** e adicionar a proprieade `surname`.<br>
![image](https://user-images.githubusercontent.com/61787168/195989548-b8a4f3a2-f6e3-4083-90ea-3abbe0d29a52.png)<br>
Caso fosse necessário alterar a propriedade `surname`, podemos usar o mesmo comando, apenas alterando o valor atribuido.

### Delete
Com esse comando conseguimos excluir relacionamentos e nodes. É preciso primeiro achar o node/relacionamento que deseja excluir com o `MATCH` e adicionar `DELETE` no final do comando.<br>
![image](https://user-images.githubusercontent.com/61787168/195989884-33e0c25d-590b-4ec4-9a95-3378b81f28e2.png)<br>
O comando acima deleta o relacionemtno entre dois nodes, para deleter um node sem relacionamentos é preciso efetuar este comando:<br>
![image](https://user-images.githubusercontent.com/61787168/195989974-f356635c-116c-4464-8493-13dcfa625664.png)<br>
Para não precisar executar dois comandos para deletar um node com relacionamento, pode ser executado o `DETACH DELETE`, que primeiro remove todas relacionamentos de um node para então deletá-lo.<br>
![image](https://user-images.githubusercontent.com/61787168/195990105-93f886de-7e73-4aa5-9024-19e21cb1e14c.png)<br>
Por último, também tem como deletarmos as propriedades com delete, mas existem maneiras melhores de efetuarmos esta operação. Uma delas é usando `REMOVE`, isso irá remover a propriedade do node.<br>
![image](https://user-images.githubusercontent.com/61787168/195990244-5a0fb5eb-e171-48d8-a5dc-474b16046224.png)<br>
Também conseguimos o mesmo resultado atualizando a proprieade para nulo com o `SET`. Isto porque o Neo4j não guarda propriedades com o valor nulo.<br>
![image](https://user-images.githubusercontent.com/61787168/195990318-70e8ce85-d480-4b85-9719-adc06a141685.png)
