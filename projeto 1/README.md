# Modelo para Apresentação do Projeto 1 - Modelo Conceitual e Lógico

## Slides da Apresentação

> Coloque aqui o link para o PDF da apresentação

## Motivação e Contexto

> Descrição do tema do projeto, incluindo motivação e contexto gerador.

Objetiva-se, por meio deste projeto, realizar uma análise econômica e social no tocante à dietas e alimentos consumidos ao redor do globo, levando em conta os conceitos e ferramentas relacionados à Banco de Dados.
Para isso, utilizamos, principalmente, as bases World Food Prices, CulinaryDB e FooDB, que nos garantem acesso aos custos de ingredientes e receitas da maioria das regiões ao redor do planeta. Desse modo, conseguimos avaliar nutricional e economicamente as múltiplas dietas adotadas mundialmente e associá-las ao seu contexto regional, econômico e social.

## Bases de Dados

> Elencar as bases de dados fonte utilizadas no projeto.

<<<<<<< HEAD
| título da base     | link                           | breve descrição             |
| ------------------ | ------------------------------ | --------------------------- |
| `<título da base>` | `<link para a página da base>` | `<breve descrição da base>` |
=======
título da base | link | breve descrição
----- | ----- | -----
`World Food Prices` | `https://data.humdata.org/dataset/wfp-food-prices` | `Base de dados que contém informações sobre o preço de alimentos como arroz, feijão, açúcar, entre outros; de mais de 1500 mercados distribuídos por 76 países ao redor do mundo.`
`Culinary DB` | `https://cosylab.iiitd.edu.in/culinarydb/#databasedescription` | `Base de dados que contêm informações sobre ingredientes utilizados e receitas tradicionais de 22 regiões geoculturais do globo.`
`FooDB` | `https://foodb.ca/` | `Base de dados sobre informações químicas e biológicas, como macro e micronutrientes, de centenas de alimentos utilizados no planeta inteiro.`
>>>>>>> 64db65ed2790edd3ed7f917bf5e65f94717cd0ec

## Modelo Conceitual

> Coloque aqui a imagem do modelo conceitual em ER ou UML, como o exemplo a seguir:
> <img src="images/ER - Projeto1.jpeg" width="400px" height="auto">

## Modelos Lógicos

> Coloque aqui o modelo lógico relacional dos bancos de dados relacionados ao modelos conceitual. Sugere-se o formato a seguir.

> Exemplo de modelo lógico relacional

```
PESSOA(_Código_, Nome, Telefone)
ARMÁRIO(_Código_, Tamanho, Ocupante)
  Ocupante chave estrangeira -> PESSOA(Código)
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
