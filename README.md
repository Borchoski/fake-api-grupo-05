# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada em nosso Projeto FrontEnd.

## Endpoints

A API tem um total de 6 endpoints, podendo cadastrar seu usuario, realizar login, atualizar e deletar o usuario alem de buscar os mesmos.

Para ter a sua base URl rode a API localmente e use "localhost:3001"

## Rotas que não necessitam de autorização
### Cadastro

POST /register <br/>

Modelo de Requisição:

{
"email": "joao@joao.com",
"password": "1212",
"age": "20",
"favoriteGames": ["Fortnite",
"Valorant",
"Minecraft"],
"socialMedia": "@joao_borchoski"
}
<br/>

Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:
{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImFubmFAYW5uYS5jb20iLCJpYXQiOjE2NzI3NDk2NDQsImV4cCI6MTY3Mjc1MzI0NCwic3ViIjoiMiJ9.htijfuvCLwWCALTPb3PFm1-QXnk-ztnUHZwtugEIh_o",
"user": {
"email": "joao@joao.com",
"age": "20",
"favoriteGames": [
"Fortnite",
"Valorant",
"Minecraft"],
"socialMedia": "@joao_borchoski",
"id": 2
}
<br/>
Modelo de resposta caso de errado:
{"Descrição do erro"}
}

### Login

POST /login <br/>

Modelo de Requisição:

{
"email": "joao@joao.com",
"password": "1212"
}
<br/>

Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:
{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImpvYW9Aam9hby5jb20iLCJpYXQiOjE2NzI3NTA0NzgsImV4cCI6MTY3Mjc1NDA3OCwic3ViIjoiMSJ9.HrlTeC6hF1dWgIIOiIFd8ynUBkxCuyLSmH4HMY5a6Ss",
"user": {
"email": "joao@joao.com",
"age": "20",
"favoriteGames": [
"Fortnite",
"Valorant",
"Minecraft"
],
"socialMedia": "@joao_borchoski",
"id": 1,
"name": "joao"
}
}
<br/>

Modelo de resposta caso de errado:
{"Descrição do erro"}

## User 

PATCH /