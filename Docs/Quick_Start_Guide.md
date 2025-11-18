# Guia de Início Rápido - JSONPlaceholder API

## 🚀 Começando em 5 minutos

Este guia irá te ajudar a fazer suas primeiras requisições à API JSONPlaceholder.

---

## 📥 1. Importar a Collection no Postman

1. Abra o **Postman**
2. Clique em **Import** no canto superior esquerdo
3. Selecione o arquivo `JSONPlaceholder_API.postman_collection.json`
4. Clique em **Import**

✅ Pronto! A collection já está configurada e pronta para uso.

---

## 🎯 2. Suas Primeiras Requisições

### Teste 1: Buscar todos os posts

1. Na collection, navegue até: **Posts → Get All Posts**
2. Clique em **Send**
3. Você verá 100 posts no response

**Endpoint usado:**
```
GET https://jsonplaceholder.typicode.com/posts
```

---

### Teste 2: Buscar um post específico

1. Navegue até: **Posts → Get Post by ID**
2. Clique em **Send**
3. Verá os detalhes do post ID 1

**Endpoint usado:**
```
GET https://jsonplaceholder.typicode.com/posts/1
```

**Response esperado:**
```json
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit\nsuscipit recusandae..."
}
```

---

### Teste 3: Criar um novo post

1. Navegue até: **Posts → Create New Post**
2. Veja o body da requisição (já configurado)
3. Clique em **Send**
4. Verá o post criado com um novo ID (101)

**Endpoint usado:**
```
POST https://jsonplaceholder.typicode.com/posts
```

**Body enviado:**
```json
{
  "title": "Meu Novo Post",
  "body": "Este é o conteúdo do meu post de teste",
  "userId": 1
}
```

---

## 🔧 3. Personalizando Requisições

### Modificar o ID em URLs

Para testar com diferentes IDs:

1. Clique na requisição desejada
2. Na barra de URL, altere o número após `/posts/` ou `/users/`
3. Exemplo: mude de `/posts/1` para `/posts/5`
4. Clique em **Send**

---

### Modificar o Body das Requisições

Para POST, PUT ou PATCH:

1. Selecione a requisição
2. Vá na aba **Body**
3. Edite o JSON conforme necessário
4. Clique em **Send**

**Exemplo - Criar seu próprio post:**
```json
{
  "title": "Aprendendo APIs REST",
  "body": "Este é meu primeiro teste com Postman!",
  "userId": 1
}
```

---

## 📚 4. Explorando Recursos

### Testar Comentários

1. **Comments → Get All Comments** - Ver todos comentários
2. **Comments → Get Comments by Post ID** - Ver comentários de um post específico

### Testar Usuários

1. **Users → Get All Users** - Ver lista de 10 usuários
2. **Users → Get User Posts** - Ver todos posts de um usuário

### Testar Todos (Tarefas)

1. **Todos → Get All Todos** - Ver 200 tarefas
2. **Todos → Create New Todo** - Criar uma tarefa

---

## 🎨 5. Testando Filtros

### Filtrar posts por usuário

1. Vá em **Posts → Get All Posts**
2. Adicione query parameter:
   - Key: `userId`
   - Value: `1`
3. URL ficará: `https://jsonplaceholder.typicode.com/posts?userId=1`
4. Clique em **Send**

### Filtrar comentários por post

1. Vá em **Comments → Get Comments by Post ID**
2. Query parameter já configurado: `postId=1`
3. Altere o valor para testar outros posts
4. Clique em **Send**

---

## ✅ 6. Testando Todos os Métodos HTTP

### GET - Buscar dados
✅ Já testado acima

### POST - Criar recursos
```
Posts → Create New Post
Todos → Create New Todo
```

### PUT - Substituir completamente
```
Posts → Update Post (PUT)
```
- Substitui TODOS os campos do recurso

### PATCH - Atualizar parcialmente
```
Posts → Update Post (PATCH)
```
- Atualiza apenas os campos enviados

### DELETE - Deletar recursos
```
Posts → Delete Post
```
- Remove o recurso (simulado)

---

## 💡 7. Dicas Importantes

### ⚠️ Dados não são salvos
```
A API simula operações POST, PUT, PATCH e DELETE.
Os dados não são realmente persistidos no servidor.
```

### ✅ Perfeito para testes
```
- Testar frontend durante desenvolvimento
- Aprender sobre APIs REST
- Criar protótipos rápidos
- Fazer demos e tutoriais
```

### 🔓 Sem autenticação
```
Todos os endpoints são públicos.
Não precisa de API keys ou tokens.
```

---

## 🧪 8. Exercícios Práticos

### Exercício 1: Buscar e filtrar
1. Busque todos os usuários
2. Escolha um ID de usuário
3. Busque todos os posts desse usuário
4. Busque os álbuns desse usuário

### Exercício 2: CRUD completo
1. **C**reate - Crie um novo post
2. **R**ead - Busque o post criado (use ID 101)
3. **U**pdate - Atualize o post com PATCH
4. **D**elete - Delete o post

### Exercício 3: Explorar relacionamentos
1. Busque o post ID 1
2. Busque os comentários desse post
3. Identifique o userId do post
4. Busque informações do usuário

---

## 📊 9. Recursos Rápidos

### Quantidades de dados disponíveis:
- 👥 **Users:** 10
- 📝 **Posts:** 100
- 💬 **Comments:** 500
- 📷 **Albums:** 100
- 🖼️ **Photos:** 5000
- ✅ **Todos:** 200

---

## 🆘 10. Troubleshooting

### Erro 404 - Not Found
```
Verifique se o ID existe (ex: post 999 não existe)
Posts válidos: 1-100
Users válidos: 1-10
```

### Resposta vazia {}
```
Normal para DELETE requests
Indica que a operação foi bem-sucedida
```

### CORS Error no browser
```
Não deve acontecer - JSONPlaceholder tem CORS habilitado
Se ocorrer, verifique sua conexão com internet
```

---

## 🎓 Próximos Passos

1. ✅ **Você completou o básico!**
2. 📖 Leia a documentação completa: `API_Documentation.md`
3. 🔍 Veja todos os endpoints: `Endpoints_Reference.md`
4. 💻 Integre com seu código (JS, Python, etc.)
5. 🚀 Explore outras APIs públicas

---

## 📞 Suporte e Links

- **API oficial:** [jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com)
- **Guia online:** [jsonplaceholder.typicode.com/guide](https://jsonplaceholder.typicode.com/guide)
- **GitHub:** [github.com/typicode/json-server](https://github.com/typicode/json-server)

---

**Boa sorte com seus testes! 🎉**

*Última atualização: Novembro 2024*
