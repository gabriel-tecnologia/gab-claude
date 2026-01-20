# Criar Issues no Linear

Crie issues no Linear a partir da descrição fornecida.

## Input

$ARGUMENTS

## Instruções

### 1. Validar Input

Se `$ARGUMENTS` estiver vazio, pergunte ao usuário quais tarefas deseja criar.

### 2. Selecionar Team

Use `mcp__linear__list_teams` para listar os times disponíveis.

Pergunte ao usuário qual team usar (a menos que já tenha sido especificado no input).

### 3. Parsear Issues

Analise o input e extraia as issues a serem criadas. O input pode ser:
- Texto livre descrevendo múltiplas tarefas
- Lista com bullets ou números
- Uma única tarefa

Para cada issue identificada, extraia ou infira:
- **title** (obrigatório): Título conciso da tarefa
- **description** (opcional): Detalhes adicionais em Markdown
- **priority** (opcional): 0=Sem prioridade, 1=Urgente, 2=Alta, 3=Normal, 4=Baixa
- **labels** (opcional): Labels existentes no Linear
- **assignee** (opcional): Usuário para atribuir (use "me" para o próprio usuário)
- **dueDate** (opcional): Data de entrega no formato ISO

### 4. Confirmar com Usuário

Antes de criar, mostre um resumo das issues que serão criadas:

```
## Issues a criar no team [TEAM_NAME]:

1. **[Título 1]**
   - Prioridade: [X]
   - Labels: [X, Y]

2. **[Título 2]**
   - Descrição: [resumo]
```

Peça confirmação antes de prosseguir.

### 5. Criar Issues

Para cada issue confirmada, use `mcp__linear__create_issue` com os campos extraídos.

### 6. Retornar Resultado

Após criar todas as issues, retorne uma lista com:
- Identificador (ex: `TEAM-123`)
- Título
- URL da issue

Exemplo de output:
```
## Issues criadas:

- [TEAM-123](url): Título da issue 1
- [TEAM-124](url): Título da issue 2
```

## Exemplos de Uso

- `/linear-create-issue criar endpoint de health check e adicionar testes unitários`
- `/linear-create-issue 1. Refatorar módulo X 2. Documentar API Y`
- `/linear-create-issue` (sem argumentos - vai perguntar)
