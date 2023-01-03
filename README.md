# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada em nosso Projeto FrontEnd.
<br/>

## Cadastro

POST /register

Não necessita de autorização

Modelo de Requisição:

```
{
"email": "joao@joao.com",
"password": "1212",
"age": "20",
"favoriteGames": ["Fortnite",
"Valorant",
"Minecraft"],
"socialMedia": "@joao_borchoski"
}
```

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
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
}
```

Modelo de resposta caso de errado:

`{"Descrição do erro"}`

## Login

POST /login

Não necessita de autorização

Modelo de Requisição:

```
{
"email": "joao@joao.com",
"password": "1212"
}
```

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
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
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

<!-- # Rotas que necessitam de autorização -->

# User

Rotas utilizadas para fins relaçionados ao usuario
<br/>

## Rotas que não necessitam de autorização:

### Atualização do próprio Usuario

PATCH /users/:id

Modelo de Requisição:

```
{
"name": "Borchoski",
"age": "32"
}
```

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
{
	"email": "joao@joao.com",
	"password": "$2a$10$i5DXc0KFVTCDXWI/Pv3P1.Z3LsYZLdMtHkWja7qhU4ufMNa5qs6vO",
	"age": "32",
	"favoriteGames": [
		"Fortnite",
		"Valorant",
		"Minecraft"
	],
	"socialMedia": "@joao_borchoski",
	"id": 1,
	"name": "Borchoski"
}
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

### Deletar próprio Usuario

DELETE /users/:id

Requisição sem body.

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
{}
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

### Criação de Post

POST /posts

Modelo de Requisição:

```
{
	"title": "Um titulo aqui",
	"content": "Um conteudo aqui",
	"userId": "1"
}
```

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
{
	"title": "Um titulo aqui",
	"content": "Um conteudo aqui",
	"userId": "1",
	"id": 1
}
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

### Atualizar Post

PATCH /posts/:post_id

Modelo de Requisição:

```
{
	"title": "Outro title para o post"
}
```

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
{
	"title": "Outro title para o post",
	"content": "Um conteudo aqui",
	"userId": "1",
	"id": 1
}
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

### Deletar Post

DELETE /posts/:post_id

Requisição sem body

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
{}
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

## Rotas que necessitam de autorização:

### Listar Posts

GET /posts

Requisição sem body

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
[
	{
		"title": "Um titulo aqui",
		"content": "Um conteudo aqui",
		"userId": "1",
		"id": 1
	}
]
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

### Listar Usuarios

### Para listar todos os usuarios use:

GET /users

Requisição sem body.

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
[
    	{
		"email": "joao@joao.com",
		"password": "$2a$10$i5DXc0KFVTCDXWI/Pv3P1.Z3LsYZLdMtHkWja7qhU4ufMNa5qs6vO",
		"age": "20",
		"favoriteGames": [
			"Fortnite",
			"Valorant",
			"Minecraft"
		],
		"socialMedia": "@joao_borchoski",
		"id": 1,
		"name": "joao"
	},
	{
		"email": "anna@anna.com",
		"password": "$2a$10$y.nBDceslzxMiG8Cif.Pvec35qKxJ742Mz9tml76AJHbkblAS1lya",
		"age": "20",
		"favoriteGames": [
			"Fortnite",
			"Valorant",
			"Minecraft"
		],
		"socialMedia": "@joao_borchoski",
		"id": 2
	}
]
```

Modelo de resposta caso de errado:
```{"Descrição do erro"}```

### Para listar um usuario especifico use:

GET /users/:id

Requisição sem body.

Modelo de resposta caso de certo:

```
{
	"email": "joao@joao.com",
	"password": "$2a$10$i5DXc0KFVTCDXWI/Pv3P1.Z3LsYZLdMtHkWja7qhU4ufMNa5qs6vO",
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
```

Modelo de resposta caso de errado:
```{"Descrição do erro"}```
