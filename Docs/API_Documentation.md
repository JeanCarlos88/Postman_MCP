# JSONPlaceholder API - Documentação Completa

## 📋 Visão Geral

**JSONPlaceholder** é uma API REST gratuita e confiável para testes e prototipagem. Serve aproximadamente **3 bilhões de requisições por mês** e é mantida por [typicode](https://github.com/typicode).

- **Base URL:** `https://jsonplaceholder.typicode.com`
- **Protocolo:** HTTP/HTTPS
- **Autenticação:** Não requerida
- **Formato:** JSON

---

## 🗂️ Recursos Disponíveis

A API possui 6 recursos principais com as seguintes quantidades de dados:

| Recurso | Endpoint | Quantidade |
|---------|----------|------------|
| Posts | `/posts` | 100 posts |
| Comments | `/comments` | 500 comentários |
| Albums | `/albums` | 100 álbuns |
| Photos | `/photos` | 5000 fotos |
| Todos | `/todos` | 200 tarefas |
| Users | `/users` | 10 usuários |

### Relacionamentos entre Recursos

- **Posts** possuem muitos **Comments**
- **Albums** possuem muitas **Photos**
- **Users** possuem muitos **Posts**, **Albums** e **Todos**

---

## 🔍 Métodos HTTP Suportados

Todos os métodos HTTP padrão são suportados:

- ✅ **GET** - Buscar recursos
- ✅ **POST** - Criar novos recursos
- ✅ **PUT** - Substituir recursos existentes
- ✅ **PATCH** - Atualizar parcialmente recursos
- ✅ **DELETE** - Remover recursos

> ⚠️ **Importante:** As operações POST, PUT, PATCH e DELETE são simuladas. Os dados não são realmente persistidos no servidor, mas a API retorna respostas como se fossem.

---

## 📖 Guia de Uso

### 1. Buscar um Recurso Individual

**Request:**
```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Response:**
```json
{
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit\nsuscipit recusandae...",
  "userId": 1
}
```

---

### 2. Listar Todos os Recursos

**Request:**
```javascript
fetch('https://jsonplaceholder.typicode.com/posts')
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Response:**
```json
[
  { "id": 1, "title": "...", "body": "...", "userId": 1 },
  { "id": 2, "title": "...", "body": "...", "userId": 1 },
  { "id": 3, "title": "...", "body": "...", "userId": 1 },
  ...
  { "id": 100, "title": "...", "body": "...", "userId": 10 }
]
```

---

### 3. Criar um Novo Recurso

**Request:**
```javascript
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  body: JSON.stringify({
    title: 'foo',
    body: 'bar',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Response:**
```json
{
  "id": 101,
  "title": "foo",
  "body": "bar",
  "userId": 1
}
```

---

### 4. Atualizar um Recurso Completo (PUT)

**Request:**
```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'PUT',
  body: JSON.stringify({
    id: 1,
    title: 'foo',
    body: 'bar',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Response:**
```json
{
  "id": 1,
  "title": "foo",
  "body": "bar",
  "userId": 1
}
```

---

### 5. Atualizar Parcialmente um Recurso (PATCH)

**Request:**
```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'PATCH',
  body: JSON.stringify({
    title: 'foo',
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Response:**
```json
{
  "id": 1,
  "title": "foo",
  "body": "quia et suscipit\nsuscipit recusandae...",
  "userId": 1
}
```

---

### 6. Deletar um Recurso

**Request:**
```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'DELETE',
});
```

**Response:**
```json
{}
```

---

## 🔎 Filtragem de Recursos

Você pode filtrar recursos usando **query parameters**:

**Exemplo - Buscar todos os posts de um usuário:**
```javascript
fetch('https://jsonplaceholder.typicode.com/posts?userId=1')
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Outros exemplos de filtros:**
- `/comments?postId=1` - Comentários do post 1
- `/photos?albumId=1` - Fotos do álbum 1
- `/todos?userId=1` - Tarefas do usuário 1

---

## 🔗 Recursos Aninhados (Nested Routes)

A API suporta **um nível de rota aninhada** para facilitar consultas relacionadas:

### Rotas Aninhadas Disponíveis:

| Rota | Descrição | Equivalente |
|------|-----------|-------------|
| `/posts/1/comments` | Comentários do post 1 | `/comments?postId=1` |
| `/albums/1/photos` | Fotos do álbum 1 | `/photos?albumId=1` |
| `/users/1/albums` | Álbuns do usuário 1 | `/albums?userId=1` |
| `/users/1/todos` | Tarefas do usuário 1 | `/todos?userId=1` |
| `/users/1/posts` | Posts do usuário 1 | `/posts?userId=1` |

**Exemplo:**
```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1/comments')
  .then((response) => response.json())
  .then((json) => console.log(json));
```

---

## 📊 Estrutura dos Recursos

### Post
```json
{
  "userId": 1,
  "id": 1,
  "title": "string",
  "body": "string"
}
```

### Comment
```json
{
  "postId": 1,
  "id": 1,
  "name": "string",
  "email": "string",
  "body": "string"
}
```

### Album
```json
{
  "userId": 1,
  "id": 1,
  "title": "string"
}
```

### Photo
```json
{
  "albumId": 1,
  "id": 1,
  "title": "string",
  "url": "string",
  "thumbnailUrl": "string"
}
```

### Todo
```json
{
  "userId": 1,
  "id": 1,
  "title": "string",
  "completed": boolean
}
```

### User
```json
{
  "id": 1,
  "name": "string",
  "username": "string",
  "email": "string",
  "address": {
    "street": "string",
    "suite": "string",
    "city": "string",
    "zipcode": "string",
    "geo": {
      "lat": "string",
      "lng": "string"
    }
  },
  "phone": "string",
  "website": "string",
  "company": {
    "name": "string",
    "catchPhrase": "string",
    "bs": "string"
  }
}
```

---

## 💡 Casos de Uso

### Quando usar JSONPlaceholder:

- ✅ Testes de frontend durante desenvolvimento
- ✅ Exemplos em documentação técnica
- ✅ Tutoriais e demos em CodeSandbox, JSFiddle, etc.
- ✅ Prototipagem rápida de aplicações
- ✅ Exemplos no Stack Overflow
- ✅ Testes unitários e de integração
- ✅ Aprendizado de APIs REST

---

## 🛠️ Tecnologias

JSONPlaceholder é construído com:
- **[JSON Server](https://github.com/typicode/json-server)** - Backend fake
- **[LowDB](https://github.com/typicode/lowdb)** - Banco de dados local

---

## 📚 Exemplos em Diferentes Linguagens

### JavaScript (Fetch API)
```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => response.json())
  .then(json => console.log(json))
```

### Python (requests)
```python
import requests
response = requests.get('https://jsonplaceholder.typicode.com/posts/1')
print(response.json())
```

### cURL
```bash
curl https://jsonplaceholder.typicode.com/posts/1
```

### PowerShell
```powershell
Invoke-RestMethod -Uri "https://jsonplaceholder.typicode.com/posts/1"
```

---

## 🔗 Links Úteis

- **Site Oficial:** [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com)
- **Guia Completo:** [https://jsonplaceholder.typicode.com/guide](https://jsonplaceholder.typicode.com/guide)
- **GitHub do JSON Server:** [https://github.com/typicode/json-server](https://github.com/typicode/json-server)
- **Seu próprio servidor JSON:** [https://my-json-server.typicode.com](https://my-json-server.typicode.com)

---

## ⚠️ Limitações

1. **Dados não são persistidos** - Alterações (POST, PUT, PATCH, DELETE) são simuladas
2. **Sem autenticação** - Todos os endpoints são públicos
3. **Sem validação de dados** - A API aceita qualquer payload JSON válido
4. **Dados fixos** - Sempre retorna o mesmo conjunto de dados fake
5. **Um nível de aninhamento** - Suporta apenas rotas como `/posts/1/comments`, não `/posts/1/comments/1/replies`

---

## 📄 Licença

JSONPlaceholder é um projeto open source mantido por [typicode](https://github.com/typicode).

**Última atualização:** Novembro 2024

---

> 💡 **Dica:** Para projetos reais, considere usar o [JSON Server](https://github.com/typicode/json-server) localmente para criar sua própria API fake com dados customizados!
