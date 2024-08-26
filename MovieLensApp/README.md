# Website

Este site foi construído usando [Docusaurus 2](https://docusaurus.io/), um moderno gerador de sites estáticos.

### Instalação

```
$ yarn
```

### Local Development

```
$ yarn start
```

Este comando inicia um servidor de desenvolvimento local e abre uma janela do navegador. A maioria das mudanças é refletida ao vivo sem precisar reiniciar o servidor.

### Build


```
$ yarn build
```

Este comando gera conteúdo estático no diretório `build`, que pode ser servido usando qualquer serviço de hospedagem de conteúdos estáticos.

### Deployment

Using SSH:

```
$ USE_SSH=true yarn deploy
```

Not using SSH:

```
$ GIT_USER=<Your GitHub username> yarn deploy
```

Se você estiver usando GitHub Pages para hospedagem, este comando é uma maneira conveniente de construir o site e enviá-lo para o branch `gh-pages`.