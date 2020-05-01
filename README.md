# 🚀Back-end Node.js🚀

## Criando um projeto Node:
```
mkdir backend
yarn init -y
```

Adicionando Express para configuração de rotas:
```
yarn add express
```

Criar o arquivo `src/index.js` e inicializando uma rota:
```
const express = require('express')
const app = express()

app.get('/', (request, response) => {
  return response.json({ message: 'Hello world' })
})

app.listen(3333, () => {
  console.log('🚀 Back-end started')
})
```

Adicionando Nodemon para hot reload do projeto:
```
yarn add nodemon -D
```

Adicionar o script no `package.json`:
```
{
  "name": "backend",
  "version": "1.0.0",
  "main": "src/index.js",
  "license": "MIT",
  "scripts": {
    "dev": "nodemon"
  },
  "dependencies": {
    "express": "^4.17.1"
  },
  "devDependencies": {
    "nodemon": "^2.0.3"
  }
}
```

## Métodos HTTP:

**GET**: Buscar informações do back-end.
**POST**: Criar uma informação no back-end.
**PUT/PATCH**: Alterar uma informação no back-end.
**DELETE**: Deletar uma informação no back-end.

```
app.get
```

**Instalação do Insomnia**

---

## Tipos de parâmetros
**Query Params**: Filtros e paginação
**Route Params**: Identificar recursos (atualizar/deletar).
**Request Body**: Conteúdo na hora de criar ou editar um recurso (JSON).

Colocar antes de todos as rotas:

```
app.use(express.json())
```

Como pegar os parâmetros:
```
app.get('/projects', (request, response) => {
  const { title, owner } = request.query
  const body = request.body
  return response.json([
    'Projeto 1',
    'Projeto 2',
    'Projeto 3',
  ])
})
```

## Middleware:
Interceptador de requisições que interrompe totalmente a requisição ou altera dados da requisição