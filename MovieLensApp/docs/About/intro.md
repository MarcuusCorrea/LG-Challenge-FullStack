---
sidebar_position: 1
---

# Sobre

MovieLens App é uma aplicação web que utiliza o conjunto de dados MovieLens para listar e recomendar filmes, além de exibir suas classificações.

### Tecnologias
- NestJS
- PrismaORM
- SQLite
- ReactJS
- Docusaurus
- Docker

NestJS e PrismaORM foram utilizados para implementar a API que fornece dados para o cliente. NestJS é um framework robusto para NodeJS, com diversas implementações e ferramentas disponíveis para o desenvolvimento de APIs. 
PrismaORM é uma biblioteca de mapeamento objeto-relacional (ORM), utilizando o banco de dados SQLite.

Para o cliente, foi utilizado o framework Docusaurus, criado pelo Facebook, que permite a criação de páginas web e o uso de arquivos Markdown, perfeito para a documentação do projeto. 
Por trás das cenas, o Docusaurus roda com React, permitindo a personalização das páginas e aproveitando todo o poder que o React oferece.

Para rodar os sistemas no ambiente, foi utilizado Docker. Foram criados Dockerfiles para a API e para o Cliente, e ambos são executados através do docker-compose, que possui um arquivo de configuração `.yml`.

## Executando a Aplicação

Para rodar a aplicação, você precisa ter o Docker instalado em sua máquina.
- [Instalar Docker Desktop no Windows](https://docs.docker.com/desktop/install/windows-install/)

Com o Docker instalado, execute o seguinte no terminal:

```console
user@desktop:$ git clone https://github.com/devRaelBraga/LG-Challenge-FullStack.git
user@desktop:$ cd MovieLensApp/ 
user@desktop:MovieLensApp$ docker-compose up -d --build
```
Após isso, a aplicação estará disponível em http://localhost:3000.

### Processamento de Dados
Utilizando o conjunto de dados do MovieLens, o script movie-lens-api/src/migrator.js foi usado para ler o dataset em formato CSV, e com a biblioteca csv-parser, os dados foram transformados em objetos JavaScript. Com isso, eles são inseridos no banco de dados usando o Prisma.

Assim, ao final da execução, temos um banco de dados com uma tabela FilmeRating, que possui os seguintes parâmetros:
- title
- year
- genres
- rating (average rating)
- quantity (quantity of user ratings)


### Disponibilizando Dados
A API MovieLens disponibiliza dados nas seguintes rotas:

- obter todos os filmes: GET /
- buscar filmes: GET /search?title=&year=&genre=&top=
- obter filmes recomendados: GET /recomendation

### Consumindo Dados

O cliente consome os dados em localhost:3003 via fetch e os exibe para o usuário em uma tabela. Também é possível ordenar os filmes por ano ou por classificação, clicando no cabeçalho da tabela "Ano" ou "Classificação".

![image](https://i.imgur.com/mZEqZha.png)
