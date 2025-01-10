# Financial Move Tech Development Docs

Github: https://github.com/FinanciaI-Move/

# Financial Move

## Links

Documentações: [Github](https://github.com/FinanciaI-Move) | [~~Cofluence~~](https://fmv.atlassian.net/wiki/spaces/FI/pages) | [Drive botvipfinancial](https://drive.google.com/drive/u/3/home) | [Postman](https://www.postman.com/financial-move/workspace/financial-move)

Clouds: [Vercel](https://vercel.com/financial-move) | [AWS](https://signin.aws.amazon.com) | [Google Cloud](https://console.cloud.google.com/welcome?pli=1&project=triple-skein-223305)

Apps: [Board Bot](https://fmv.atlassian.net/jira/software/projects/BOT/boards/2) | [Tickets BOT](https://fmv.atlassian.net/jira/servicedesk/projects/TIC/section/service-requests/custom/10) | [Board APP](https://fmv.atlassian.net/jira/software/projects/APP/boards/1) | [Clockfy](https://app.clockify.me/) | [Slack](slack.com)

## Projetos

| Projeto                                                                                             | Repositório                                                                               | Status    |
| --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | --------- |
| [Bot VIP (normal)](https://t.me/FinancialMoveBot) e [Bot Chefe](https://t.me/FinancialMoveChefeBot) | [bot-vip-telegram](https://github.com/FinanciaI-Move/bot-vip-telegram)                    | Ativo     |
| [Dashboard Bot Chefe](https://dashboard-vip.vercel.app/)                                            | [dashboard-vip](https://github.com/FinanciaI-Move/dashboard-vip)                          | Ativo     |
| MySQL com scripts python                                                                            | [mysql-database](https://github.com/FinanciaI-Move/mysql-database)                        | Ativo     |
| Redis                                                                                               | [redis-database](https://github.com/FinanciaI-Move/redis-database)                        | Ativo     |
| [Cryptotraders App](https://socialogin.wtlltech.com/login)                                          | [cryptotraders-app](https://github.com/FinanciaI-Move/cryptotraders-app)                  | Ativo     |
| Bot VIP (whatsapp)                                                                                  | [bot-vip-whatsapp](https://github.com/FinanciaI-Move/bot-vip-whatsapp)                    | Arquivado |
| Room VIP                                                                                            | [room-vip](https://github.com/FinanciaI-Move/room-vip)                                    | Arquivado |
| Planilha do milhão back-end                                                                         | [planilha-do-milhao-backend](https://github.com/FinanciaI-Move/planilha-milhao-backend)   | Ativo     |
| Planilha do milhão front-end                                                                        | [planilha-do-milhao-frontend](https://github.com/FinanciaI-Move/planilha-milhao-frontend) | Ativo     |

## Estrutura cloud

### Vercel

Todos os projetos que são Next serão hospedados na Vercel

- [dashboard-vip](https://vercel.com/financial-move/dashboard-vip)

### AWS

Nossa principal infraestrutura está na AWS, com instâncias EC2 e RDS, além de usar o S3 para armazenamento, Rekognition para reconhecimento de imagem, etc...

#### EC2 us-east-1

- [QA1 do cryptotraders-app](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#InstanceDetails:instanceId=i-0dace5b6d8a06fd13) (a ser migrado pós delete app_development)
- [test-server](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#InstanceDetails:instanceId=i-09eb21d17466822d1) (a ser desativado pós validação carteira bot vip)

#### EC2 sa-east-1

- [Produção do bot-vip-telegram + redis](https://sa-east-1.console.aws.amazon.com/ec2/home?region=sa-east-1#InstanceDetails:instanceId=i-0db5c1a60b86e63fc)
- [QA1 do bot-vip-telegram](https://sa-east-1.console.aws.amazon.com/ec2/home?region=sa-east-1#InstanceDetails:instanceId=i-0a9e840d76526982a)
- [Homologação da app_development do bot-vip-telegram](https://sa-east-1.console.aws.amazon.com/ec2/home?region=sa-east-1#InstanceDetails:instanceId=i-02720402df2454280) (a ser desativado pós delete app_development)

#### RDS sa-east-1

- [Produção e QA1 do mysql-database](https://sa-east-1.console.aws.amazon.com/rds/home?region=sa-east-1#database:id=db-financialmove;is-cluster=false)

#### S3 global

- [Bucket de arquivos do cryptotraders-app](https://s3.console.aws.amazon.com/s3/home?region=sa-east-1#)
- [Moderação de imagem do cryptotraders-app](https://us-east-1.console.aws.amazon.com/rekognition/home?region=us-east-1#/)

### Google Cloud

Aqui só usamos para conectar nossos projetos com o Google Workspace, para sincronização de arquivos em planilhas ou no drive.

#### Apps

- [active-report-383515](https://console.cloud.google.com/home/dashboard?authuser=3&hl=pt-br&orgonly=true&project=active-report-383515&supportedpurview=project)

## Serviços externos

<!-- Para validar essa seção, analisar os .env -->

Em nossos projetos usamos serviços externos, ou via API ou via webhook, para fazer integrações e automatizações.

- API da AWS para utilização dos serviços do cryptotraders-app
- Webhook e API do Telegram para a comunicação dos bots
- API e Websocket da Bybit para a comunicação principal com uma exchange
- API da Binance como alternativa para quando a Bybit está fora do ar
- API da Active Campaign para a sincronização dos dados internos com o CRM
- Webhook e API do Digital Guru para a sincronização dos pagamentos e assinaturas
- API da OpenAI para a utilização do GPT-3 em nossos projetos
- GraphQL do Facebook para coleta de dados de ads
- CoinMarketCap para coleta de dados de mercado

## Custos gerados pela nossa infraestrutura

| Serviço | Custo médio mensal   |
| ------- | -------------------- |
| AWS     | $ 1.500,00           |
| Vercel  | $ 20,00 x 2 = $40,00 |
| OpenAI  | $ 5,00               |
| CMC     | $ 35,00              |

## Sobre cada projeto ativo

Para saber em específico sobre cada projeto, acesse o repositório correspondente e leia o README.md

<br/>

<br/>

# Padrões de desenvolvimento

## Lemas

### Mantenha a simplicidade (e objetividade)

Não faça mais do que o necessário, não crie mais do que o necessário, não escreva mais do que o necessário, mas não se esqueça de fazer o necessário.

Nossas entregas tendem a serem simples e objetivas, com validação de MVPs e entregas rápidas, porém, sem esquecer da qualidade.

### Use o seu cérebro

Você tem permissão para pensar, e deve pensar. Se algo não te faz sentido ou parece errado, questione, e se for o caso, proponha uma solução.

Todos os membros do time tem voz e vez, e com certeza tem algo a contribuir.

### Nada está gravado a ferro e fogo

Nossos processos e padrões de desenvolvimento são flexíveis, e podem ser alterados a qualquer momento, desde que tenha ganho para o projeto e/ou time, e que seja validado por todos.

### Aprenda e ensine

Ninguém sabe tudo, e todos temos algo a aprender e a ensinar. Seja humilde para aprender, e generoso para ensinar.

#### Referências

- Parte II - A prática leva à perfeição, do livro "How to be a better programmer" de Pete Goodliffe

## Branchs

- main

  Possui o código em produção, jamais efetuar o commit diretamente nela, somente via PR da develop -> main.

- develop

  Possui o código candidato a producao, commits diretos somente para fix de algo já mergeado mas não no deploy, normalmente recebe PRs de branches de features, bugs, etc...

- qualquer outra branch

  Possuem o código de features, bugs, etc...

  Sempre criar uma branch a partir da develop e efetuar o PR para a mesma.

<br/>

<br/>

# Time de desenvolvimento

### Full Time

- [William Tavares (head)](https://github.com/wtill)
- [Lucas Kaminski (full stack)](https://github.com/lucas-kaminski)
- [Matheus Scabia (full stack)](https://github.com/mhscabia)
- [Alex Junior (back-end)](https://github.com/Alexvjunior)

### Part Time

- [Guilherme Roque (front end)]()

### Softwares recomendados

| Função         | Software recomendado                                                           |
| -------------- | ------------------------------------------------------------------------------ |
| IDE            | [VSCode](https://code.visualstudio.com/)                                       |
| SSH            | [Tabby](https://tabby.app/)                                                    |
| Banco de dados | [DBeaver](https://dbeaver.io/) ou [Beekeeper](https://www.beekeeperstudio.io/) |

### Extensões recomendadas (VSCode)

#### Geral

| Extensão                                                                                                                                                                                                                                       | Função                                                                                       |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| [Code Speel Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) e [Brazilian Portuguese](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker-portuguese) | Corretor ortográfico que suporta português brasileiro e typos tanto em pt-br quanto em en-us |
| [Color Highlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)                                                                                                                                                 | Dentro do código, destaca cores em hexadecimal, rgb, rgba, hsl e hsla                        |
| [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)                                                                                                                                      | Padroniza a formatação do código a partir de um arquivo `.editorconfig` na raiz do projeto   |
| [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost)                                                                                                                                                      | Analisa o tamanho dos imports e mostra o custo de cada um                                    |
| [indent-rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow)                                                                                                                                                   | Destaca a indentação do código com cores diferentes                                          |
| [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)                                                                                                                                          | .md toolset                                                                                  |
| [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)                                                                                                                                    | Autocompleta caminhos de arquivos e pastas                                                   |
| [Todo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)                                                                                                                                                         | Mostra todos os TODOs do projeto em uma árvore                                               |
| [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)                                                                                                                                                                 | Suporte para YAML                                                                            |

#### Python

| Extensão                                                                                         | Função                                     |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------ |
| [Black Formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.python)          | Formata o código em Python no padrão Black |
| [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)          | Intellisense para Python                   |
| [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)                   | Suporte para Python                        |
| [Python Indent](https://marketplace.visualstudio.com/items?itemName=KevinRose.vsc-python-indent) | Melhora a indentação do código Python      |
| [Flake8](https://marketplace.visualstudio.com/items?itemName=ms-python.flake8)                   | Linter para Python                         |
| [Pylint](https://marketplace.visualstudio.com/items?itemName=ms-python.pylint)                   | Linter para Python                         |
| [Python Debug](https://marketplace.visualstudio.com/items?itemName=ms-python.python-debug)       | Debug para Python                          |

#### JavaScript

| Extensão                                                                               | Função                                            |
| -------------------------------------------------------------------------------------- | ------------------------------------------------- |
| [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)   | Linter para JavaScript                            |
| [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) | Formata o código em JavaScript no padrão Prettier |

## Commands

- `mkdocs new [dir-name]` - Create a new project.
- `mkdocs serve` - Start the live-reloading docs server.
- `mkdocs build` - Build the documentation site.
- `mkdocs -h` - Print help message and exit.
