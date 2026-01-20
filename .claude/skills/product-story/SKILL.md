---
name: product-story
description: Gera user stories, spikes e bugs a partir de um PRD ou perguntas. Planeja as histórias, refina uma a uma com o usuário, e cria diretamente no Linear. Use quando precisar quebrar requisitos em histórias, criar itens de backlog, ou quando o usuário mencionar "user story", "spike", "bug", "história", "backlog".
---

# Story Writer - Gerador de Histórias para Linear

Este skill gera user stories, spikes e bugs a partir de um PRD (ou perguntas), valida o plano com o usuário, e depois refina e cria cada história diretamente no Linear.

## Princípios Fundamentais

1. **INVEST** - Histórias devem ser Independent, Negotiable, Valuable, Estimable, Small, Testable
2. **Critérios rule-oriented** - Formato checklist, não Given/When/Then
3. **Uma história por vez** - Refinar e validar antes de criar
4. **Buscar antes de criar** - Evitar duplicatas no Linear
5. **Spike para incerteza** - Quando há risco técnico alto, spike primeiro

---

## Fluxo de Conversa (4 Fases)

### Fase 1: Entrada de Dados

**1.1 Perguntar pela fonte:**

> "Você tem um PRD para essa feature?"

- **Se sim**: Ler o arquivo PRD, extrair requisitos das seções P0/P1/P2
- **Se não**: Fazer perguntas de discovery:
  - Qual problema estamos resolvendo?
  - Quem é o usuário?
  - Quais funcionalidades são necessárias?

**1.2 Identificar o squad:**

> "Qual squad? (app-mobile / gabriel-os / integrations)"

**1.3 Identificar projeto no Linear:**

> "Há um projeto no Linear para vincular estas histórias?"

- Se mencionado, usar esse projeto
- Se não mencionado, buscar projetos relacionados no Linear:
  - Usar `mcp__linear__list_projects` com query do nome da feature
  - **Excluir projetos com state Completed ou Cancelled**
  - Mostrar opções encontradas ao usuário

- **Se nenhum projeto encontrado**, prosseguir sem projeto mas avisar:
  > "Não encontrei um projeto relacionado. Posso criar as histórias sem projeto, mas recomendo criar um no Linear para organizar melhor o trabalho. Deseja continuar assim mesmo?"

---

### Fase 2: Planejamento das Histórias

**2.1 Analisar requisitos e gerar um mapa de histórias:**

- Listar todas as histórias propostas com tipo (User Story / Spike / Bug)
- Aplicar princípio INVEST - quebrar requisitos grandes em histórias menores
- Identificar dependências entre histórias
- Sugerir spikes para áreas de incerteza técnica

**2.2 Apresentar o plano ao usuário:**

```
📋 Plano de Stories para [Feature]:

1. [Spike] Investigar viabilidade técnica - avaliar API/integração
2. [US] Funcionalidade principal - descrição breve
3. [US] Feedback visual ao usuário - descrição breve
4. [US] Tratamento de erros - descrição breve
5. [Bug] Correção de problema conhecido - descrição breve

Faz sentido? Quer adicionar, remover ou ajustar algo?
```

**2.3 Aguardar validação do usuário antes de prosseguir**

---

### Fase 3: Refinamento das Histórias (Uma por Uma)

Para cada história no plano:

**3.1 Buscar no Linear por histórias similares:**

- Usar `mcp__linear__list_issues` com query
- **Excluir issues com status type Completed ou Cancelled**
- Se encontrar similar, perguntar:
  > "Encontrei uma issue similar: '[título]'. Quer usar essa existente ou criar uma nova?"

**3.2 Buscar contexto no Slack:**

- Buscar mensagens relacionadas ao tópico da história
- Encontrar discussões, decisões, feedback que enriqueçam o entendimento
- Mostrar achados relevantes ao usuário antes de gerar

**3.3 Pedir mais contexto ao usuário:**

> "Vamos refinar a história '[título]'. Quanto mais contexto você puder fornecer, melhor ficará a história."

Perguntar conforme o tipo:

- **Para User Story**: cenários específicos, edge cases, integrações, comportamentos esperados
- **Para Spike**: hipóteses a validar, riscos conhecidos, abordagens consideradas
- **Para Bug**: logs, screenshots, frequência de ocorrência, impacto no usuário

**3.4 Gerar conteúdo usando o template apropriado:**

> **IMPORTANTE**: Templates são a fonte da verdade. Sempre ler dinamicamente para obter a estrutura mais atual.

- **Para User Story**: Ler e seguir `templates/user-story.md`
- **Para Spike**: Ler e seguir `templates/spike.md`
- **Para Bug**: Ler e seguir `templates/bug.md`

**3.5 Mostrar ao usuário para refinamento:**

- Apresentar o conteúdo gerado
- Perguntar:
  > "Algo a ajustar antes de criar no Linear?"

**3.6 Criar no Linear após aprovação:**

- Usar `mcp__linear__create_issue`
- Configurar:
  - **title**: título da história
  - **description**: conteúdo completo em markdown
  - **team**: squad identificado na Fase 1
  - **project**: ID do projeto (se disponível)
  - **state**: "Refinamento Geral" (este é o nome do status)
  - **labels**: adicionar se alguma label existente fizer sentido

- Para verificar labels disponíveis, usar `mcp__linear__list_issue_labels`
- Mostrar link da issue criada ao usuário

**3.7 Avançar para próxima história no plano**

---

### Fase 4: Resumo Final

Após criar todas as histórias:

**4.1 Mostrar resumo de todas as issues criadas com links do Linear**

```
✅ Histórias criadas com sucesso!

| # | Tipo | Título | Link |
|---|------|--------|------|
| 1 | Spike | Investigar API | [INT-123](link) |
| 2 | US | Upload de vídeo | [INT-124](link) |
| 3 | US | Preview do vídeo | [INT-125](link) |
```

**4.2 Sugerir próximos passos:**

- Agendar refinement com o squad
- Priorizar no backlog
- Atribuir responsáveis

---

## Integração com Linear

### Buscar issues similares

```
mcp__linear__list_issues com:
- query: palavras-chave do título
- team: squad team
- includeArchived: false
- Filtrar: excluir status type "Completed" ou "Cancelled"
```

### Buscar projetos relacionados

```
mcp__linear__list_projects com:
- query: nome da feature
- team: squad team
- Filtrar: excluir state "Completed" ou "Cancelled"
```

### Criar issue

```
mcp__linear__create_issue com:
- title: título da história
- description: conteúdo completo (markdown)
- team: squad team
- project: ID do projeto (se disponível)
- state: "Refinamento Geral"
- labels: [se aplicável]
```

### Obter labels disponíveis

```
mcp__linear__list_issue_labels com:
- team: squad team
```

---

## Integração com Slack

### Buscar contexto

- Buscar mensagens relacionadas ao tópico da história
- Encontrar discussões, decisões, feedback de usuários
- Enriquecer entendimento do problema com conversas reais

---

## Exemplos de Ativação

O usuário pode iniciar com:

- "Quero criar as histórias para o PRD de [feature]"
- "Me ajuda a quebrar esse PRD em user stories"
- "Preciso criar histórias para [funcionalidade]"
- "Vamos criar as stories para [feature]"
- "Tenho um bug para reportar sobre [problema]"
- "Preciso criar um spike para investigar [incerteza]"

---

## Dicas para o PM

- **Quanto mais contexto, melhor** - Forneça detalhes sobre cenários, edge cases, integrações
- **Não pule o planejamento** - Valide o mapa de histórias antes de refinar
- **Spikes primeiro** - Se há incerteza técnica, crie spike antes de user stories
- **Uma história por vez** - Refine e aprove cada história antes de avançar
- **Revise os templates** - Os templates em `templates/` são a fonte da verdade
