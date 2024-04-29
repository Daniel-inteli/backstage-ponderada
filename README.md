# Deploying backstage on docker

## Instalar Backstage
Para iniciar a instalação, criei este respositório no Github e dentro dele abri o terminal e inseri o comando `npx @backstage/create-app@latest --skip-install`, após executar o comando, o terminal irá solicitar a escolha de um nome para a aplicação.
Neste momento se estiver com o yarn desatualizado, execute o comando `npm install --global yarn` para atualizar. Após esses papos, execute `yarn install` para baixar as dependências do backstage.

![Yarn Install](/assets/yarn%20install.png)

## Build
Agora que o projeto do Backstage foi instalado, precisamos buildar o projeto para subir a imagem no Docker. Primeiro iremos executar o comando `yarn install --frozen-lockfile` para verificar se as dependências do package.json e yarn.lock estão em conformidade. Depois iremos executar o comando `yarn tsc` para ativar com compilador Typescript para o projeto, e por último iremos executar o comando `yarn build:backend` que de fato irá buildar o projeto.

## Docker

Para subir a imagem no Docker iremos utilizar o comando `docker image build . -f packages/backend/Dockerfile --tag backstage --no-cache`, e o comando `docker run -it -p 7007:7007 backstage` para executar o backstage de forma local na porta 7007

## Backstage
