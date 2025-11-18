# Prompts Prontos: Postman MCP no GitHub Copilot

## 🎯 Guia Rápido de Prompts

Este documento contém **prompts prontos para copiar e colar** no GitHub Copilot para usar o Postman MCP com a API JSONPlaceholder.

---

## 🚀 Primeiros Passos

### Verificar Conexão

```
Me mostre minhas informações de usuário do Postman
```

### Listar Collections

```
Quais collections eu tenho no Postman?
```

### Listar Environments

```
Mostre meus environments do Postman
```

---

## ▶️ Executar Testes

### Execução Básica

```
Execute a collection JSONPlaceholder API
```

### Com Opções Específicas

```
Execute a collection JSONPlaceholder com timeout de 60 segundos
```

```
Execute a collection JSONPlaceholder e pare se houver erro
```

```
Rode a collection JSONPlaceholder e me mostre apenas um resumo
```

### Com Environment

```
Execute a collection JSONPlaceholder usando o environment "Production"
```

---

## 🔍 Análise de Resultados

### Resumo Geral

```
Me dê um resumo da última execução da collection JSONPlaceholder
```

### Testes que Falharam

```
Quais testes falharam na última execução?
```

```
Me mostre detalhes dos erros
```

### Performance

```
Qual foi o tempo de resposta médio?
```

```
Quais requests foram mais lentos?
```

### Taxa de Sucesso

```
Qual a taxa de sucesso dos testes?
```

---

## 🌍 Gerenciar Environments

### Criar Environment

```
Crie um environment "Test Dev" com as variáveis:
- baseUrl: https://jsonplaceholder.typicode.com
- userId: 1
- postId: 1
```

### Atualizar Environment

```
Atualize o environment "Test Dev" alterando userId para 5
```

### Usar Environment Específico

```
Execute JSONPlaceholder usando o environment "Test Dev"
```

---

## 📝 Gerenciar Collections

### Ver Detalhes

```
Me mostre os detalhes da collection JSONPlaceholder API
```

### Listar Requests

```
Quais requests existem na collection JSONPlaceholder?
```

### Ver Request Específico

```
Me mostre os detalhes do request "Create New Post"
```

> ⚠️ **Nota Importante:** O Postman MCP não suporta execução de requests individuais. Você só pode executar collections completas. Para testar um endpoint específico, crie uma collection temporária contendo apenas esse request.

---

## 🎭 Mock Servers

### Criar Mock Server

```
Crie um mock server público chamado "JSONPlaceholder Mock" para a collection JSONPlaceholder API
```

### Listar Mocks

```
Mostre meus mock servers
```

### Atualizar Mock

```
Atualize o mock server "JSONPlaceholder Mock" para privado
```

---

## 📊 Cenários Práticos

### Validação Rápida

```
Valide se a API JSONPlaceholder está funcionando
```

```
Teste se todos os endpoints estão respondendo
```

### Debug de Problema

```
Execute a collection JSONPlaceholder e me mostre quais requests de Posts falharam
```

```
Execute a collection JSONPlaceholder e me dê detalhes completos dos erros
```

### Testes com Dados Diferentes

```
Crie um environment temporário com userId=7 e execute a collection JSONPlaceholder
```

```
Execute a collection com userId=3 e depois com userId=8, e compare os resultados
```

### Preparar Demo

```
Crie um mock server público da collection JSONPlaceholder para usar em uma demo
```

### Comparação de Ambientes

```
Execute a collection JSONPlaceholder no environment "Dev" e depois no "Prod", e compare os resultados
```

### Análise de Performance

```
Execute a collection JSONPlaceholder 3 vezes e me mostre o tempo médio de execução
```

```
Identifique os requests mais lentos
```

### Validação Pré-Deploy

```
Execute a collection JSONPlaceholder completa. Se houver qualquer falha, me mostre detalhes. Se tudo passar, confirme que está OK para deploy
```

---

## 🔧 Workflows Compostos

### Criar e Testar

```
Crie um environment "Staging" com baseUrl e userId, depois execute a collection JSONPlaceholder usando esse environment
```

### Executar e Salvar

```
Execute a collection JSONPlaceholder e salve os resultados em um arquivo test-results.json
```

### Executar e Reportar

```
Execute a collection e gere um relatório markdown dos resultados
```

### Múltiplas Execuções

```
Execute a collection JSONPlaceholder 5 vezes e me mostre:
- Tempo médio
- Taxa de sucesso média
- Quantas vezes cada teste falhou
```

---

## 💬 Conversas Contextuais

O Copilot mantém contexto, então você pode:

**Primeira pergunta:**
```
Execute a collection JSONPlaceholder
```

**Seguimento (sem repetir contexto):**
```
Quantos testes passaram?
```

```
Me mostre os que falharam
```

```
Agora execute com userId=5
```

```
Compare com a execução anterior
```

---

## ⚠️ Limitações Importantes

### O que o Postman MCP NÃO suporta:

❌ **Executar requests individuais**
- Não é possível executar apenas um request específico
- Solução: Execute a collection completa ou crie uma collection temporária

❌ **Executar pastas específicas**
- Não é possível executar apenas uma pasta de requests
- Solução: Execute a collection completa

### O que o Postman MCP SUPORTA:

✅ **Executar collections completas**
```
Execute a collection JSONPlaceholder API
```

✅ **Gerenciar environments**
```
Crie/atualize/liste environments
```

✅ **Gerenciar workspaces**
```
Listar workspaces e seus conteúdos
```

✅ **Criar mock servers**
```
Crie um mock server para a collection
```

✅ **Gerar especificações OpenAPI**
```
Gere uma spec OpenAPI da collection
```

✅ **Ver detalhes de collections**
```
Me mostre os detalhes da collection JSONPlaceholder
```

---

## 🎓 Dicas de Prompts

### Seja Natural

✅ **Bom:**
```
Roda os testes da API pra mim
```

✅ **Também funciona:**
```
Execute a collection JSONPlaceholder API
```

### Use Contexto

✅ **Depois de uma execução:**
```
E com userId diferente?
```

✅ **Referenciando resultado:**
```
Por que esse teste falhou?
```

### Combine Ações

✅ **Múltiplas etapas:**
```
Crie um environment de teste, configure as variáveis que preciso, e execute a collection JSONPlaceholder
```

### Peça Explicações

```
Explique o resultado da última execução
```

```
O que significa esse erro?
```

```
Como posso corrigir isso?
```

### Salve Resultados

```
Salve os resultados em um arquivo
```

```
Gere um relatório HTML
```

```
Exporte para JSON
```

---

## 📋 Templates Personalizáveis

### Template: Execução Customizada

```
Execute a collection [NOME DA COLLECTION] 
[OPÇÕES: com timeout de X / pare no erro / usando environment Y]
[RESULTADO: e me mostre / e salve em / e compare com]
```

### Template: Criar Environment

```
Crie um environment "[NOME]" com:
- [VARIÁVEL 1]: [VALOR 1]
- [VARIÁVEL 2]: [VALOR 2]
[OPCIONAL: e execute a collection X]
```

### Template: Análise

```
[EXECUTE/ANALISE] a collection [NOME]
e [me mostre / salve / exporte / compare]
[DETALHE: apenas erros / resumo / relatório completo]
```

---

## ⚡ Atalhos Rápidos

### Manhã

```
Bom dia! Valida a API JSONPlaceholder pra mim?
```

### Durante Dev

```
Testa o endpoint que modifiquei
```

### Antes de Commit

```
Roda os testes antes de eu commitar
```

### Debugging

```
Por que isso está falhando?
```

### Deploy

```
Tudo OK para deploy?
```

---

## 🎯 Prompts por Objetivo

### Objetivo: Validação Rápida

```
✅ Execute JSONPlaceholder e confirme se está OK
✅ Valide a API rapidamente
✅ Testa se está tudo funcionando
```

### Objetivo: Debugging

```
🔍 Me mostre detalhes do erro no endpoint X
🔍 Por que o teste Y está falhando?
🔍 Execute apenas o request problemático
```

### Objetivo: Performance

```
⚡ Meça o tempo de resposta dos endpoints
⚡ Identifique requests lentos
⚡ Compare performance com execução anterior
```

### Objetivo: Preparação

```
🎯 Valide antes do deploy
🎯 Crie mock para demo
🎯 Configure environment de staging
```

---

## 💡 Exemplos Reais de Uso

### Exemplo 1: Início do Dia

```
Copilot: Bom dia! Como posso ajudar?

Você: Valida a API JSONPlaceholder pra mim

Copilot: [executa e mostra resultados]

Você: Tudo OK?

Copilot: Sim, todos os 30 testes passaram!
```

### Exemplo 2: Debugging

```
Você: Execute a collection JSONPlaceholder e me mostre os requests que falharam

Copilot: [executa e mostra requests com falha]

Você: O que significa esse erro no request Create New Post?

Copilot: [explica o erro]

Você: Como corrijo?

Copilot: [sugere correção na collection]
```

### Exemplo 3: Preparação para Demo

```
Você: Preciso preparar uma demo. Crie um mock server público da collection JSONPlaceholder

Copilot: [cria mock e retorna URL]

Você: Perfeito! Agora teste se o mock está funcionando

Copilot: [testa o mock]
```

---

## ✅ Checklist Diário

**Copie e cole no Copilot:**

```
Por favor, me ajude com o checklist diário:
1. Validar se a API JSONPlaceholder está OK
2. Executar testes de regressão
3. Verificar se há algum endpoint com performance ruim
4. Gerar relatório do status atual
```

---

**Salve este documento e use como referência rápida!** 📌

Todos esses prompts funcionam diretamente no chat do GitHub Copilot. Experimente e adapte conforme sua necessidade! 🚀
