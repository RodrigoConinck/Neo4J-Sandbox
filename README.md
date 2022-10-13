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

Esse comando irá criar um node do tipo Person, com a propriedade name com valor Patrick

### Match
É utilizado para buscar nodes que correspondem a um padrão específico.
### Comando 1
