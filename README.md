## Aplicativo MovieLens
O aplicativo MovieLens é uma aplicação web que utiliza o conjunto de dados do MovieLens para listar e recomendar filmes e exibir suas classificações.

## Tecnologias
 - NestJS
 - PrismaORM
 - SQLite
 - ReactJS
 - Docusaurus
 - Docker

O NestJS e o PrismaORM foram utilizados para implementar a API que fornece dados para o cliente. O NestJS é um framework robusto para NodeJS, com muitas implementações e ferramentas disponíveis para o desenvolvimento de APIs. O PrismaORM é uma biblioteca para mapeamento objeto-relacional (ORM), utilizando o banco de dados SQLite.

Para o cliente, foi utilizado o framework Docusaurus, criado pelo Facebook, que permite a criação de páginas web e o uso de arquivos Markdown, ideal para a implementação da documentação do projeto. Por baixo do capô, o Docusaurus executa o React, permitindo a personalização de páginas e utilizando todo o poder que o React oferece.

Para executar os sistemas no ambiente, foi utilizado o Docker. Foram criados Dockerfiles para a API e o Cliente, e ambos são executados através do docker-compose, que possui um arquivo de configuração .yml.

Executando a Aplicação
Para executar a aplicação, é necessário ter o Docker instalado na sua máquina.

Instale o Docker Desktop no Windows.
Com o Docker instalado, execute os seguintes comandos no terminal:

    ```
    user@desktop:$ git clone https://github.com/devRaelBraga/LG-Challenge-FullStack.git
    user@desktop:$ cd MovieLensApp/ 
    user@desktop:MovieLensApp$ docker-compose up -d --build

Após isso, a aplicação estará disponível em http://localhost:3000.

## Processamento de Dados
Utilizando o conjunto de dados do MovieLens, o script movie-lens-api/src/migrator.js foi utilizado para ler o conjunto de dados em formato CSV e, com a biblioteca csv-parser, os dados foram transformados em objetos JavaScript. Com isso, eles foram inseridos no banco de dados usando o Prisma.

Assim, ao final da execução, temos um banco de dados com uma tabela FilmeRating que possui os seguintes parâmetros:

título
ano
gêneros
classificação (média das classificações)
quantidade (quantidade de classificações dos usuários)
Disponibilizando os Dados
A API MovieLens disponibiliza os dados nas seguintes rotas:

obter todos os filmes: GET /
pesquisar filmes: GET /search?title=&year=&genre=&top=
obter filmes recomendados: GET /recommendation
Os melhores filmes recomendados foram classificados utilizando a fórmula:

    movieScore = movieRating * quantityRating / 2

## Consumindo os Dados
O cliente consome os dados em localhost:3003 via fetch e os exibe para o usuário em uma tabela. Também é possível ordenar os filmes por ano ou por classificação, bastando clicar no cabeçalho da tabela "Ano" ou "Classificação".
