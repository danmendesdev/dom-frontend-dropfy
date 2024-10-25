# DropFy - Frontend

Este repositório contém o código-fonte do frontend da aplicação DropFy, desenvolvido com Vue.js. O frontend fornece uma interface web para:

* Cadastrar produtos com informações básicas.
* Visualizar e editar as copys e descrições geradas pelo backend.
* Configurar as regras de precificação.
* Gerenciar os produtos na loja Shopify. (em desenvolvimento)

## Tecnologias utilizadas

* Vue.js
* Vue Router
* Axios
* [Framework CSS - ex: Tailwind CSS, Bootstrap]
* Docker

## Como executar

### Usando Docker

1. Construa a imagem Docker: `docker build -t nome-da-imagem .`
2. Execute o container: `docker run -p 80:80 nome-da-imagem`

### Executando localmente (sem Docker)

1. Clone o repositório: `git clone <URL_do_repositorio>`
2. Instale as dependências: `npm install`
3. Execute a aplicação em modo de desenvolvimento: `npm run dev`

## Deploy

[Descreva como fazer o deploy da aplicação, ex: buildar os arquivos estáticos e copiar para o servidor]

## Dockerfile

```dockerfile
FROM node:lts-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

RUN npm run build

FROM nginx:alpine

COPY --from=0 /app/dist /usr/share/nginx/html   


EXPOSE 80
