---
sidebar_position: 2
---

# Tecnologias utilizadas

Esta seção mostrará as tecnologias usadas para criar o MovieLensApp.

## NestJS

[Nest](https://nestjs.com/) é um framework poderoso e robusto para NodeJS. Ele permite o desenvolvimento de aplicações altamente confiáveis e escaláveis.
Escolhi o Nest devido ao seu alto uso e poder, permitindo uma escalabilidade rápida e expansão das aplicações.
Para esta aplicação, como é bastante simples, apenas um módulo foi necessário, já que há apenas uma tabela no banco de dados.

Junto com o NestJS, foram usados:
- [PrismaORM](https://www.prisma.io/docs) - Usado para acessar e gerenciar o banco de dados
- [SQLite](https://www.sqlite.org/index.html) - Usado como banco de dados
- [Jest](https://jestjs.io/pt-BR/) - Usado para testes unitários

## Docusaurus

[Docusaurus](https://docusaurus.io/) é um framework [React](https://react.dev/) focado na documentação de aplicações,
ele permite o uso de arquivos Markdown no React e possibilita a personalização e criação de novas páginas. Escolhi o Docusaurus porque queria usar arquivos Markdown para a documentação deste app, e como ele roda React, pude personalizar e criar minhas próprias páginas.

## Docker

[Docker](https://www.docker.com/) é uma plataforma open-source projetada para automatizar a implantação de aplicações e gerenciar aplicações em contêineres. No seu núcleo, o Docker usa contêineres para encapsular aplicações e suas dependências, garantindo que elas funcionem de forma consistente em diferentes ambientes, desde o laptop de um desenvolvedor até um servidor de produção. Ele permite escalabilidade, portabilidade, eficiência de recursos e é uma parte essencial do DevOps.

Nesta aplicação, há dois sistemas funcionando: ```MovieLens API``` e ```MovieLens Client```, cada um com seu próprio Dockerfile, configurando o ambiente, a imagem e testando (no caso da API). Para uma construção e execução rápidas, foi utilizado um arquivo ```docker-compose.yml``` para construir e executar as imagens da API e do Cliente.

O MovieLens API tem uma etapa de testes onde ele executa as suítes de teste e só constrói a aplicação se todos os testes passarem.