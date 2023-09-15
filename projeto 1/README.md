# Modelo para Apresentação do Projeto 1 - Modelo Conceitual e Lógico

## Slides da Apresentação

> Coloque aqui o link para o PDF da apresentação

## Motivação e Contexto
Objetiva-se, por meio deste projeto, realizar uma análise econômica e social no tocante à dietas e alimentos consumidos ao redor do globo, levando em conta os conceitos e ferramentas relacionados à Banco de Dados.
Para isso, utilizamos, principalmente, as bases World Food Prices, CulinaryDB e FooDB, que nos garantem acesso aos custos de ingredientes e receitas da maioria das regiões ao redor do planeta. Desse modo, conseguimos avaliar nutricional e economicamente as múltiplas dietas adotadas mundialmente e associá-las ao seu contexto regional, econômico e social.

## Bases de Dados
| título da base     | link                           | breve descrição             |
`World Food Prices` | `https://data.humdata.org/dataset/wfp-food-prices` | `Base de dados que contém informações sobre o preço de alimentos como arroz, feijão, açúcar, entre outros; de mais de 1500 mercados distribuídos por 76 países ao redor do mundo.`
`Culinary DB` | `https://cosylab.iiitd.edu.in/culinarydb/#databasedescription` | `Base de dados que contêm informações sobre ingredientes utilizados e receitas tradicionais de 22 regiões geoculturais do globo.`
`FooDB` | `https://foodb.ca/` | `Base de dados sobre informações químicas e biológicas, como macro e micronutrientes, de centenas de alimentos utilizados no planeta inteiro.`

## Modelo Conceitual

> <img src="./images/imagem_er_projeto1.jpeg" width="800px" height="auto">

## Modelos Lógicos

```
Food_DB(_Food_ID_, foodb_name, nutrients)
W_F_Prices(_Food_region_ID_, foodw_name, food_price, Country)
Culinary_DB(_Recipe_ID_, _ingredient_, recipe_name, region)
Check_price(_foodb_name_, _foodw_name_)
  foodb_name chave estrangeira -> Food_DB(foodb_name)
  foodw_name chave estrangeira -> W_F_Prices(foodw_name)
Food_in_recipe(_foodb_name_, _Recipe_ID_, Food_ID, ingredient)
  foodb_name, Food_ID chave estrangeira -> Food_DB(foodb_name, Food_ID)
  Recipe_ID, ingredient chave estrangeira -> Culinary_DB(Recipe_ID, ingredient)
Check_region(_Country_, _region_)
  region chave estrangeira -> Culinary_DB(region)
  Country chave estrangeira -> W_F_Prices(Country)
```

## Perguntas de Pesquisa/Análise

> Liste aqui as perguntas de pesquisa/análise. Nem todas as perguntas precisam de implementação associada. É possível haver perguntas em que a solução é apenas descrita para demonstrar o potencial da base. Abaixo são ilustradas três perguntas, mas pode ser um número maior a critério da equipe.

#### Pergunta/Análise 1

> - Pergunta 1
>
>   - Explicação sucinta da análise que será feita.

#### Pergunta/Análise 2

> - Pergunta 2
>
>   - Explicação sucinta da análise que será feita.

#### Pergunta/Análise 3

> - Pergunta 3
>
>   - Explicação sucinta da análise que será feita.

### Perguntas/Análise Propostas mas Não Implementadas

#### Pergunta/Análise 1

> - Pergunta 1
>
>   - Explicação em linhas gerais de como a base pode ser usada para responder esta pergunta e a sua relevância.

#### Pergunta/Análise 2

> - Pergunta 2
>
>   - Explicação em linhas gerais de como a base pode ser usada para responder esta pergunta e a sua relevância.

#### Pergunta/Análise 3

> - Pergunta 3
>
>   - Explicação em linhas gerais de como a base pode ser usada para responder esta pergunta e a sua relevância.
