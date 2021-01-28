# DASA-API

DASA-API fornece a API responsável pelo gerenciamento de todos os laboratórios e exames da rede nacional brasileira.


# Architeture e Stack

## Stack

- ES6
- Express Framework
- Sequelize ORM  
- Mocha e Chai        
- CriptoJs            - Aplicado para criptografia de senhas no banco de dados
- JWT                 - Utilizado para gerar os tokens de usuários autenticados

## Architeture

- NodeJs
- PostgreSQL
- Heroku              - Para o deploy da aplicação em ambiente de produção


# Skeleton application

    .
    ├── .github
        └── workflows             # Contém o arquivo de configuração de CI para o GitHub Actions
    ├── node_modules              # Contém a instalação de todos os pacotes adicionados em package.json
    ├── src
    |   ├── config                # Contém os arquivos de configuração da instância do sequelize, token JWT e dos arquivos de migrations
    |   ├── controllers           
    |   ├── helpers               # Auxiliadores responsáveis por fazer o controle de erros e exceptions da aplicação
    |   ├── middlewares           # Contém o middleware responsável por autenticar as rotas e controlar os erros lançados em resposta a uma requisição
    |   ├── migrations            # Contém os arquivos que criam as tabelas no banco de dados
    |   ├── models
    |   ├── routes
    |   ├── seeders               # Arquivos que realizam inserções de registros no banco de dados
    |   ├── services              # Auxiliam os controles manipulando as regras de negócio em conjunto com os models
    |   ├── utils                 # Contém arquivos de classes úteis que podem ser utilizados por toda a aplicação
    |   └── validations           # Contém os schemas responsáveis por verificar e validar o corpo das requisições HTTP do tipo POST e PUT
    └── test                      # Contém todos os arquivos de testes
        └── integrations          # Contém todos os testes de integração


# Commits

A estrutura dos commits foi orientada conforme a **AngularJS commit conventions**. A convenção de escrita das mensagens, pode ser vista com mais detalhes através do link:
https://blog.geekhunter.com.br/o-que-e-commit-e-como-usar-commits-semanticos/#Commits_Atomicos


# Branches e pull requests

O sistema de branches, baseia-se em dois principais troncos: `develop` e `master`. Durante o desenvolvimento, as novas branches deverão ser criadas a partir de `develop`, obedecendo
o padrão a seguir:

- **Features:** Ao desenvolver novas funcionalidades ao projeto, definir a nomeclatura da branch como `feature/<nome da feature em inglês>`.
- **Bugs:** Ao corrigir o bug de alguma feature anteriormente desenvolvida, definir nomenclatura da branch como `bug-fix/<nome da feature em inglês>`.

Seguindo o fluxo, ao concluir o desenvolvimento da tarefa, realizar um pull request para a branch `develop`. Finalmente, todas as alterações aplicadas em `develop`, serão replicadas
para `master` através de outro pull request, concretizando os resultados em um deploy no servidor de produção.


# Versioning

Utilizou-se o versionamento semântico para que equipes paralelas, possam consumir a API, conhecendo com detalhes, todas as modificações que foram realizadas no projeto.
O versionamento semântico, foi aplicado no projeto, através do pacote `semantic-release` e configurado no arquivo de base `.realeaserc`. Foi definido que na branch nomeada
como `develop` , serão publicadas automaticamente as versões de **pre-release**, e na `master` , efetivamente a versão de **release**. Para mais detalhes sobre a convenção:
https://semver.org/


# Lint

Pensando na boa leitura e organização do código, foi adicionado o pacote do `Eslint` e o `Prettier`. Os arquivos de configuração são `.eslintrc` e `.prettierrc`. 
Ambos encontram-se na raiz do projeto.


# Tests

Na aplicação, foram realizados os testes de integração com Chai e Mocha. Em princípio, todos os testes foram executados em ambiente local através do comando `npm test`, além disso,
durante o deploy da aplicação, a bateria dos testes é executada através do Github Actions antes de ser enviada ao servidor do Heroku.


# Environment variables

As configurações do banco de dados e servidor, tais como, senhas e dados sensíveis, estão protegidos por variáveis de ambiente no servidor de produção (Heroku). Porém, para executar a aplicação
em ambiente local, você precisará definí-las através dos "arquivos de configuração", localizados na pasta `/src/config`. Veja os detalhes na sequência para entender exatamente como
realizar o procedimento:

# Running

Descrição detalhada das configurações e funcionamento do workflow aplicação + banco de dados, tanto em ambiente local, quanto em produção.

## Local/Development environment

Para executar a aplicação no seu ambiente local, siga as etapas descritas nos passos a seguir:

### 1 Arquivos de configuração

- Faça um clone do repositório https://github.com/rafagodoy/dasa-api.git em seu ambiente local.

- Crie 

### 3 Migrations

As migrations, localizadas na pasta `/src/migrations` contém os arquivos responsáveis por criar as tabelas no banco de dados.

## Production environment

## CI/Deploy

## Packages

Os pacotes encontram-se instalados na pasta `node_modules`, encontrando-se divididos entre dependências para o ambiente de desenvolvimento e produção:

```
  "dependencies": {
    "@types/chai": "^4.2.14",
    "babel-core": "^6.26.3",
    "babel-polyfill": "^6.26.0",
    "babel-preset-env": "^1.7.0",
    "babel-preset-stage-0": "^6.24.1",
    "babel-register": "^6.26.0",
    "body-parser": "^1.19.0",
    "chai": "^4.2.0",
    "chai-http": "^4.3.0",
    "chai-subset": "^1.6.0",
    "cors": "^2.8.5",
    "crypto-js": "^4.0.0",
    "dotenv": "^8.2.0",
    "eslint-config-prettier": "^6.11.0",
    "eslint-plugin-prettier": "^3.1.3",
    "express": "^4.17.1",
    "faker": "^5.1.0",
    "jsonwebtoken": "^8.5.1",
    "mocha": "^8.2.1",
    "pg": "^8.2.0",
    "pg-hstore": "^2.3.3",
    "prettier": "^2.0.5",
    "semantic-release": "^17.3.3",
    "sequelize": "^5.21.9",
    "sequelize-cli": "^5.5.1",
    "sqlite3": "^4.2.0",
    "yup": "^0.29.0"
  },
  "devDependencies": {
    "eslint": "^6.8.0",
    "eslint-config-airbnb-base": "^14.1.0",
    "eslint-plugin-import": "^2.20.2",
    "nodemon": "^2.0.3",
    "prettier": "^2.0.5",
    "sucrase": "^3.13.0"
  },
```

# API

A seguir temos

# Usuários

# Laboratórios

# Exames

# Associar exames aos laboratórios