---
sidebar_position: 3
---

# Arquitetura

Descrição detalhada da arquitetura da aplicação utilizando o modelo C4.

## Modelo C4

O Modelo C4, composto por diagramas de Contexto, Contêineres, Componentes e Código, oferece uma abordagem estruturada para o design e comunicação da arquitetura de software. No seu núcleo, ele fornece uma visão hierárquica da arquitetura de um sistema, começando pelo contexto de alto nível e gradualmente se aprofundando até o nível do código.

### Diagrama de Contexto

No diagrama de contexto, podemos ver sistemas de software externos usados por este aplicativo. Como mostrado, não há sistemas de software externos.

![image](https://i.imgur.com/8NpiO1f.png)

### Diagrama de Contêiner

No diagrama de contêiner, podemos ver os módulos de nossos sistemas, as partes do sistema que podem funcionar de forma independente.

![image](https://i.imgur.com/gG4YwBa.png)

### Diagrama de Componentes - API

Neste diagrama de componentes, podemos ver as partes do módulo da API e como elas interagem entre si. O NestJS utiliza um padrão com Módulo, Controlador e Serviço. 
Os Módulos gerenciam controladores e provedores, os Controladores gerenciam a lógica de requisições, e os Serviços são responsáveis pelas regras de negócios e pela lógica do sistema. 
Como há apenas uma tabela, foi necessário apenas um módulo, controlador e serviço.

![image](https://i.imgur.com/p7JKoDG.png)

### Diagrama de Componentes - Cliente

Neste diagrama de componentes, vemos os componentes do módulo Cliente e como eles interagem.

![image](https://i.imgur.com/SQWWOir.png)

### Esquema do Banco de Dados

Foi necessária apenas uma tabela, `FilmeRating`, contendo movieID, ano, gêneros, classificação e quantidade de classificações. O SQLite foi utilizado como banco de dados.

![image](https://i.imgur.com/CQDO3eA.png)