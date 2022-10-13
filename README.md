# Neo4J-Sandbox [Movies]

## Conceitos Básicos
### Nodes (p:Person)
Representam entidades do banco, são como as linhas de um banco relacional. Devem ser escritos entre parênteses, onde **p** é a variável e **Person** o tipo.

### Relações [p:Play]
Representa as relações entre os nodes, deve ser escrito entre chaves, onde **p** é a variável e **Play** indica o tipo da relação.

### Labels :labels
São nomes/identificadores para as relações e nodes, possuim o prefixo ":" e devem ser usadas depois de variáveis

### Propriedades p.prop
Utilizadas para adicionar atributos nos nodes e relacionamentos. Onde **p** representa a variável da entidade e prop o **nome** da propriedade

## Principais comandos
### Create
Utilizado para criar nodes/relações. <br>
![image](https://user-images.githubusercontent.com/61787168/195723099-693a34fa-0e89-4b93-958f-91965ffa687b.png)
<br>Esse comando irá criar um node do tipo Person, com a propriedade name com valor Patrick

### Match
É utilizado para buscar nodes que correspondem a um padrão específico.<br>
![image](https://user-images.githubusercontent.com/61787168/195723267-a502c1ba-32bf-4bb0-9467-8b9b9959f079.png)
<br>O exemplo acima é um jeito básico de fazer a busca, no qual está limitado a fazer comparações simples entre strings. Para filtrar os resultados mais efetivamente, deve ser usado a cláusula **WHERE** junto de operadores de comparação (Starts With, Ends, >, <, etc).<br>
![image](https://user-images.githubusercontent.com/61787168/195723736-f336a75c-3c09-404b-a753-91bda0ab472e.png)<br>
![image](https://user-images.githubusercontent.com/61787168/195723898-8d232e30-e04e-4540-a7b6-1813f3162d5f.png)

### 
