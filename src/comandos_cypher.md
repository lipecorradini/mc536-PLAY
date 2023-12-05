# Comandos para implementação do Banco de Dados em Grafos apresentado

~~~cypher
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lipecorradini/mc536-PLAY/main/data/raw/01_Recipe_Details.csv' AS line
CREATE (:Receita {id: line.`Recipe ID`, nome: line.Title, subregiao: line.Cuisine})

CREATE INDEX FOR (n:Receita) ON (n.id)

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lipecorradini/mc536-PLAY/main/data/raw/02_Ingredients.csv' AS line
CREATE (:Ingrediente {id: line.`Entity ID`, nome: line.`Aliased Ingredient Name`})

CREATE INDEX FOR (n:Ingrediente) ON (n.id)

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lipecorradini/mc536-PLAY/main/data/raw/04_Recipe-Ingredients_Aliases.csv' AS line
MATCH (i:Ingrediente {id: line.`Entity ID`})
MATCH (r:Receita {id: line.`Recipe ID`})
CREATE (r)-[:Contem]->(i)

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lipecorradini/mc536-PLAY/main/data/interim/CountriesTable.csv' AS line
CREATE (:País {nome: line.Country, subregiao: line.`World Region`})

CREATE INDEX FOR (n:País) ON (n.id)

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lipecorradini/mc536-PLAY/main/data/interim/Ingredients_to_Foodb_Groups.csv' AS line
CREATE (:SubgrupoIF {nome_ingrediente: line.NAME, categoria: line.CATEGORY, subgrupo: line.FOOD_GROUP})

MATCH (i:Ingrediente), (s:SubgrupoIF)
WHERE i.nome = s.nome_ingrediente
CREATE (i)-[:PertenceIF]->(s)

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lipecorradini/mc536-PLAY/main/data/interim/Foodb_to_Food_Prices.csv' AS line
MERGE (g:Grupo {subgrupo: line.FOOD_GROUP, nome: line.SERIES_NAME})

MATCH (i:Ingrediente)-[:PertenceIF]->(t:SubgrupoIF), (g:Grupo)
WHERE t.subgrupo = g.subgrupo
CREATE (i)-[:Pertence]->(g)

MATCH (i:Ingrediente)-[p:Pertence]->(g:Grupo)
SET p.subgrupo = g.subgrupo;

MATCH (n1)-[p:PertenceIF]->(n2)
DELETE p;

MATCH (n:SubgrupoIF)
DELETE n;

MATCH (i:Ingrediente)-[:Pertence]->(g:Grupo)
WITH i, COLLECT(g) AS grupos
UNWIND grupos AS grupo
MATCH (outroGrupo:Grupo {nome: grupo.nome})
MERGE (i)-[:PERTENCE_TESTE]->(outroGrupo)

MATCH (g:Grupo)
WITH g.nome AS nome, COLLECT (g) AS duplicatas
WHERE SIZE(duplicatas) > 1
FOREACH (duplicata IN TAIL(duplicatas) | DETACH DELETE duplicata);

MATCH (a)-[t:PERTENCE_TESTE]->(b)
WHERE NOT (a)-[:Pertence]->(b)
CREATE (a)-[:Pertence]->(b)

MATCH (n1)-[t:PERTENCE_TESTE]->(n2)
DELETE t

MATCH (g:Grupo)
REMOVE g.subgrupo;

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/lipecorradini/mc536-PLAY/main/data/raw/Food_Prices_Data.csv' AS line
MATCH (g:Grupo {nome: line.`Series Name`})
MATCH (p:`País` {nome: line.`Country Name`})
CREATE (g)-[:Custa {preço: line.`2017 [YR2017]`}]->(p)
~~~