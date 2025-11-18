# Endpoints da JSONPlaceholder API

## Base URL
```
https://jsonplaceholder.typicode.com
```

---

## 📝 POSTS

### GET /posts
Retorna todos os posts (100 items)

**Response:**
```json
[
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident...",
    "body": "quia et suscipit..."
  },
  ...
]
```

---

### GET /posts/{id}
Retorna um post específico

**Parâmetros:**
- `id` (path) - ID do post

**Exemplo:** `/posts/1`

**Response:**
```json
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident...",
  "body": "quia et suscipit..."
}
```

---

### GET /posts/{id}/comments
Retorna comentários de um post específico

**Parâmetros:**
- `id` (path) - ID do post

**Exemplo:** `/posts/1/comments`

**Response:**
```json
[
  {
    "postId": 1,
    "id": 1,
    "name": "id labore ex et quam laborum",
    "email": "Eliseo@gardner.biz",
    "body": "laudantium enim quasi est quidem..."
  },
  ...
]
```

---

### POST /posts
Cria um novo post

**Headers:**
```
Content-Type: application/json
```

**Body:**
```json
{
  "title": "Meu novo post",
  "body": "Conteúdo do post",
  "userId": 1
}
```

**Response:**
```json
{
  "id": 101,
  "title": "Meu novo post",
  "body": "Conteúdo do post",
  "userId": 1
}
```

---

### PUT /posts/{id}
Substitui completamente um post existente

**Parâmetros:**
- `id` (path) - ID do post

**Headers:**
```
Content-Type: application/json
```

**Body:**
```json
{
  "id": 1,
  "title": "Título atualizado",
  "body": "Corpo atualizado",
  "userId": 1
}
```

**Response:**
```json
{
  "id": 1,
  "title": "Título atualizado",
  "body": "Corpo atualizado",
  "userId": 1
}
```

---

### PATCH /posts/{id}
Atualiza parcialmente um post existente

**Parâmetros:**
- `id` (path) - ID do post

**Headers:**
```
Content-Type: application/json
```

**Body:**
```json
{
  "title": "Apenas título atualizado"
}
```

**Response:**
```json
{
  "userId": 1,
  "id": 1,
  "title": "Apenas título atualizado",
  "body": "quia et suscipit..." // mantém o valor original
}
```

---

### DELETE /posts/{id}
Deleta um post

**Parâmetros:**
- `id` (path) - ID do post

**Exemplo:** `/posts/1`

**Response:**
```json
{}
```

---

## 💬 COMMENTS

### GET /comments
Retorna todos os comentários (500 items)

**Response:**
```json
[
  {
    "postId": 1,
    "id": 1,
    "name": "id labore ex et quam laborum",
    "email": "Eliseo@gardner.biz",
    "body": "laudantium enim quasi..."
  },
  ...
]
```

---

### GET /comments/{id}
Retorna um comentário específico

**Parâmetros:**
- `id` (path) - ID do comentário

**Exemplo:** `/comments/1`

---

### GET /comments?postId={postId}
Filtra comentários por ID do post

**Parâmetros:**
- `postId` (query) - ID do post

**Exemplo:** `/comments?postId=1`

**Response:**
```json
[
  {
    "postId": 1,
    "id": 1,
    "name": "id labore ex et quam laborum",
    "email": "Eliseo@gardner.biz",
    "body": "laudantium enim quasi..."
  },
  ...
]
```

---

## 📷 ALBUMS

### GET /albums
Retorna todos os álbuns (100 items)

**Response:**
```json
[
  {
    "userId": 1,
    "id": 1,
    "title": "quidem molestiae enim"
  },
  ...
]
```

---

### GET /albums/{id}
Retorna um álbum específico

**Parâmetros:**
- `id` (path) - ID do álbum

**Exemplo:** `/albums/1`

---

### GET /albums/{id}/photos
Retorna fotos de um álbum específico

**Parâmetros:**
- `id` (path) - ID do álbum

**Exemplo:** `/albums/1/photos`

**Response:**
```json
[
  {
    "albumId": 1,
    "id": 1,
    "title": "accusamus beatae ad facilis...",
    "url": "https://via.placeholder.com/600/92c952",
    "thumbnailUrl": "https://via.placeholder.com/150/92c952"
  },
  ...
]
```

---

## 🖼️ PHOTOS

### GET /photos
Retorna todas as fotos (5000 items)

**Response:**
```json
[
  {
    "albumId": 1,
    "id": 1,
    "title": "accusamus beatae ad facilis...",
    "url": "https://via.placeholder.com/600/92c952",
    "thumbnailUrl": "https://via.placeholder.com/150/92c952"
  },
  ...
]
```

---

### GET /photos/{id}
Retorna uma foto específica

**Parâmetros:**
- `id` (path) - ID da foto

**Exemplo:** `/photos/1`

---

### GET /photos?albumId={albumId}
Filtra fotos por ID do álbum

**Parâmetros:**
- `albumId` (query) - ID do álbum

**Exemplo:** `/photos?albumId=1`

---

## ✅ TODOS

### GET /todos
Retorna todas as tarefas (200 items)

**Response:**
```json
[
  {
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false
  },
  ...
]
```

---

### GET /todos/{id}
Retorna uma tarefa específica

**Parâmetros:**
- `id` (path) - ID da tarefa

**Exemplo:** `/todos/1`

---

### GET /todos?userId={userId}
Filtra tarefas por ID do usuário

**Parâmetros:**
- `userId` (query) - ID do usuário

**Exemplo:** `/todos?userId=1`

---

### POST /todos
Cria uma nova tarefa

**Headers:**
```
Content-Type: application/json
```

**Body:**
```json
{
  "title": "Nova tarefa",
  "completed": false,
  "userId": 1
}
```

**Response:**
```json
{
  "id": 201,
  "title": "Nova tarefa",
  "completed": false,
  "userId": 1
}
```

---

## 👤 USERS

### GET /users
Retorna todos os usuários (10 items)

**Response:**
```json
[
  {
    "id": 1,
    "name": "Leanne Graham",
    "username": "Bret",
    "email": "Sincere@april.biz",
    "address": {
      "street": "Kulas Light",
      "suite": "Apt. 556",
      "city": "Gwenborough",
      "zipcode": "92998-3874",
      "geo": {
        "lat": "-37.3159",
        "lng": "81.1496"
      }
    },
    "phone": "1-770-736-8031 x56442",
    "website": "hildegard.org",
    "company": {
      "name": "Romaguera-Crona",
      "catchPhrase": "Multi-layered client-server neural-net",
      "bs": "harness real-time e-markets"
    }
  },
  ...
]
```

---

### GET /users/{id}
Retorna um usuário específico

**Parâmetros:**
- `id` (path) - ID do usuário

**Exemplo:** `/users/1`

---

### GET /users/{id}/posts
Retorna posts de um usuário específico

**Parâmetros:**
- `id` (path) - ID do usuário

**Exemplo:** `/users/1/posts`

**Response:**
```json
[
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat...",
    "body": "quia et suscipit..."
  },
  ...
]
```

---

### GET /users/{id}/albums
Retorna álbuns de um usuário específico

**Parâmetros:**
- `id` (path) - ID do usuário

**Exemplo:** `/users/1/albums`

---

### GET /users/{id}/todos
Retorna tarefas de um usuário específico

**Parâmetros:**
- `id` (path) - ID do usuário

**Exemplo:** `/users/1/todos`

---

## 📊 Resumo de Endpoints

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| GET | `/posts` | Lista todos os posts |
| GET | `/posts/{id}` | Busca post por ID |
| GET | `/posts/{id}/comments` | Comentários do post |
| POST | `/posts` | Cria novo post |
| PUT | `/posts/{id}` | Atualiza post completo |
| PATCH | `/posts/{id}` | Atualiza post parcial |
| DELETE | `/posts/{id}` | Deleta post |
| GET | `/comments` | Lista todos comentários |
| GET | `/comments/{id}` | Busca comentário por ID |
| GET | `/comments?postId={id}` | Filtra por post |
| GET | `/albums` | Lista todos álbuns |
| GET | `/albums/{id}` | Busca álbum por ID |
| GET | `/albums/{id}/photos` | Fotos do álbum |
| GET | `/photos` | Lista todas fotos |
| GET | `/photos/{id}` | Busca foto por ID |
| GET | `/photos?albumId={id}` | Filtra por álbum |
| GET | `/todos` | Lista todas tarefas |
| GET | `/todos/{id}` | Busca tarefa por ID |
| GET | `/todos?userId={id}` | Filtra por usuário |
| POST | `/todos` | Cria nova tarefa |
| GET | `/users` | Lista todos usuários |
| GET | `/users/{id}` | Busca usuário por ID |
| GET | `/users/{id}/posts` | Posts do usuário |
| GET | `/users/{id}/albums` | Álbuns do usuário |
| GET | `/users/{id}/todos` | Tarefas do usuário |

---

## 📌 Notas Importantes

1. **Todos os endpoints suportam HTTPS e HTTP**
2. **Não requer autenticação**
3. **CORS habilitado** - pode ser usado de qualquer domínio
4. **Operações de escrita são simuladas** - dados não são persistidos
5. **Sempre retorna JSON** - `Content-Type: application/json`
6. **Rate limiting:** Não possui, mas use com responsabilidade

---

**Última atualização:** Novembro 2024
