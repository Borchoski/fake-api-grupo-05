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
	"name": "João Borchoski"
	"age": "20",
	"favoriteGames": [
		{
			"name": "Fortinite",
			"genre": "Battle royale"
		},
		{
			"name": "PUBG",
			"genre": "Battle royale"
		},
		{
			"name": "Valorant",
			"genre": "FPS"
		},
		{
			"name": "Minecraft",
			"genre": "Survival"
		}
	],
	"socialMedia": "@joao_borchoski"
}
```

#### Respostas Da Resquisição: <br/>

Modelo de resposta caso de certo:

```
{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImpvYW9Aam9hby5jb20iLCJpYXQiOjE2NzI3NjQ5NzQsImV4cCI6MTY3Mjc2ODU3NCwic3ViIjoiMSJ9.6b5uaKQnxksDcVrXcjLufX-0N2nFuyKx04D5vgZqYKU",
	"user": {
		"email": "joao@joao.com",
		"name": "João Borchoski",
		"age": "20",
		"favoriteGames": [
			{
				"name": "Fortinite",
				"genre": "Battle royale"
			},
			{
				"name": "PUBG",
				"genre": "Battle royale"
			},
			{
				"name": "Valorant",
				"genre": "FPS"
			},
			{
				"name": "Minecraft",
				"genre": "Survival"
			}
		],
		"socialMedia": "@joao_borchoski",
		"id": 1
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
		"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImpvYW9Aam9hby5jb20iLCJpYXQiOjE2NzI3NjYwMTcsImV4cCI6MTY3Mjc2OTYxNywic3ViIjoiMSJ9.2J-riwhQrFAlsYeTo27yWn2oDg7t3YG95yI-2lvnOXw",
	"user": {
		"email": "joao@joao.com",
		"name": "João Borchoski",
		"age": "32",
		"favoriteGames": [
			{
				"name": "Fortinite",
				"genre": "Battle royale"
			},
			{
				"name": "PUBG",
				"genre": "Battle royale"
			},
			{
				"name": "Valorant",
				"genre": "FPS"
			},
			{
				"name": "Minecraft",
				"genre": "Survival"
			}
		],
		"socialMedia": "@joao_borchoski",
		"id": 1,
	}
}
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

<br/>
# User

Rotas utilizadas para fins relacionados ao usuario
<br/>

## Rotas que necessitam de autorização:

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
	"password": "$2a$10$TmkqJZ3wgsLNWN8MInbfFeWQPiEDkcI4lXy3yDeW7HVx9MYT3ufO2",
	"name": "Borchoski",
	"age": "32",
	"favoriteGames": [
		{
			"name": "Fortinite",
			"genre": "Battle royale"
		},
		{
			"name": "PUBG",
			"genre": "Battle royale"
		},
		{
			"name": "Valorant",
			"genre": "FPS"
		},
		{
			"name": "Minecraft",
			"genre": "Survival"
		}
	],
	"socialMedia": "@joao_borchoski",
	"id": 1
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

<br/>
## Posts

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

<br/>

## Listar Usuarios

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
		"name": "João Borchoski"
		"age": "20",
		"favoriteGames": [
			"Fortnite",
			"Valorant",
			"Minecraft"
		],
		"socialMedia": "@joao_borchoski",
		"id": 1,
	},
	{
		"email": "anna@anna.com",
		"password": "$2a$10$y.nBDceslzxMiG8Cif.Pvec35qKxJ742Mz9tml76AJHbkblAS1lya",
		"name": "Anna"
		"age": "20",
		"favoriteGames": [
			{
				"name": "Disney Dreamlight Valley",
				"genre": "RPG"
			}
		],
		"socialMedia": "@anna",
		"id": 2
	}
]
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

### Para listar um usuario especifico use:

GET /users/:id

Requisição sem body.

Modelo de resposta caso de certo:

```
{
	"email": "joao@joao.com",
	"password": "$2a$10$TmkqJZ3wgsLNWN8MInbfFeWQPiEDkcI4lXy3yDeW7HVx9MYT3ufO2",
	"name": "joao",
	"age": "32",
	"favoriteGames": [
		{
			"name": "Fortinite",
			"genre": "Battle royale"
		},
		{
			"name": "PUBG",
			"genre": "Battle royale"
		},
		{
			"name": "Valorant",
			"genre": "FPS"
		},
		{
			"name": "Minecraft",
			"genre": "Survival"
		}
	],
	"socialMedia": "@joao_borchoski",
	"id": 1
}
```

Modelo de resposta caso de errado:
`{"Descrição do erro"}`

<br/>

## Rotas que não necessitam de autorização:

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

