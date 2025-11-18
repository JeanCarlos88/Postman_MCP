# Exemplos Práticos: Postman MCP no GitHub Copilot

## 📋 Sobre Este Documento

Este guia apresenta **workflows práticos** usando o GitHub Copilot e Postman MCP para testar a API JSONPlaceholder. Todos os exemplos são baseados em conversas naturais com o Copilot.

## ⚠️ Importante: Funcionalidades Suportadas

O Postman MCP **APENAS** suporta:
- ✅ Executar collections completas
- ✅ Gerenciar environments (criar, atualizar, listar)
- ✅ Gerenciar workspaces
- ✅ Criar e gerenciar mock servers
- ✅ Gerar especificações OpenAPI
- ✅ Ver detalhes de collections

O Postman MCP **NÃO** suporta:
- ❌ Executar requests individuais
- ❌ Executar pastas específicas
- ❌ Editar requests existentes via código

---

## 🎯 Cenário 1: Validação Automatizada de API

### Objetivo
Validar que todos os endpoints da JSONPlaceholder estão respondendo corretamente.

### Workflow no Copilot

**Passo 1: Executar a collection**
```
Execute a collection JSONPlaceholder API
```

**Passo 2: Analisar resultados**
```
Me dê um resumo detalhado dos resultados:
- Total de requisições
- Requisições com falha
- Taxa de sucesso
- Lista de testes que falharam
```

**Passo 3: Verificar qualidade**
```
A taxa de sucesso está acima de 95%? Se não, me mostre quais endpoints estão problemáticos
```

### Resultado Esperado

O Copilot irá:
- ✅ Executar todos os requests da collection
- ✅ Calcular estatísticas de sucesso/falha
- ✅ Identificar endpoints problemáticos
- ✅ Fornecer relatório detalhado

---

## 🎯 Cenário 2: Testes de Performance

### Objetivo
Medir o tempo de resposta e performance dos endpoints.

### Workflow no Copilot

**Execução múltipla:**
```
Execute a collection JSONPlaceholder 5 vezes e para cada execução me mostre:
- Duração total
- Número de requests
- Tempo médio de resposta
```

**Análise comparativa:**
```
Das 5 execuções anteriores, me dê:
- Tempo médio total
- Execução mais rápida
- Execução mais lenta
- Qual foi a variação de performance?
```

**Identificar gargalos:**
```
Quais requests tiveram os tempos de resposta mais altos?
```

### Resultado Esperado

O Copilot irá:
- ✅ Executar múltiplas iterações
- ✅ Coletar métricas de cada execução
- ✅ Calcular médias e variações
- ✅ Identificar requests lentos

---

## 🎯 Cenário 3: Comparação Entre Environments

### Objetivo
Comparar o comportamento da API em diferentes environments.

### Workflow no Copilot

**Passo 1: Criar environments**
```
Crie dois environments:
1. "Production" com baseUrl: https://jsonplaceholder.typicode.com
2. "Mock" com baseUrl: [URL do seu mock server]
```

**Passo 2: Executar em Production**
```
Execute a collection JSONPlaceholder usando o environment "Production"
```

**Passo 3: Executar em Mock**
```
Execute a collection JSONPlaceholder usando o environment "Mock"
```

**Passo 4: Comparar resultados**
```
Compare os resultados das duas execuções:
- Taxa de sucesso de cada um
- Tempo de resposta médio
- Quais requests falharam em cada environment
```

### Resultado Esperado

O Copilot irá:
- ✅ Criar environments configurados
- ✅ Executar collection em cada environment
- ✅ Comparar métricas entre execuções
- ✅ Identificar diferenças de comportamento

---

## 🎯 Cenário 4: Validação Pré-Deploy

### Objetivo
Validar que a API está pronta para deploy.

### Workflow no Copilot

```
Execute um checklist de validação:
1. Execute a collection JSONPlaceholder completa
2. Verifique se a taxa de sucesso é 100%
3. Verifique se todos os requests responderam em menos de 2 segundos
4. Me dê um relatório GO/NO-GO para deploy
```

### Resultado Esperado

O Copilot irá:
- ✅ Executar todos os testes
- ✅ Validar critérios de qualidade
- ✅ Fornecer decisão clara (GO ou NO-GO)
- ✅ Listar problemas bloqueadores (se houver)

---

## 🎯 Cenário 5: Criação de Mock Server para Demo

### Objetivo
Criar um mock server para usar em demonstrações.

### Workflow no Copilot

```
Preciso criar uma demo:
1. Crie um mock server público chamado "JSONPlaceholder Demo" para a collection JSONPlaceholder API
2. Me dê a URL do mock
3. Teste o mock executando a collection usando essa URL
```

### Resultado Esperado

O Copilot irá:
- ✅ Criar mock server público
- ✅ Fornecer URL acessível
- ✅ Validar que o mock está funcionando
- ✅ Confirmar que pode ser usado em demo

---

**Todos os exemplos usam apenas funcionalidades suportadas pelo Postman MCP!** 🚀
