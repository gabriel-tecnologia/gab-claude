# Listar Issues de uma Pessoa

Liste todas as issues atribuídas a uma pessoa específica no Linear.

## Input

$ARGUMENTS

## Instruções

### 1. Identificar Assignee

- Se `$ARGUMENTS` estiver vazio:
  1. Use `mcp__linear__get_user` com `query: "me"` para obter o usuário atual
  2. Use o email retornado como filtro de assignee
- Se `$ARGUMENTS` fornecido, use o valor como filtro (nome ou email)

### 2. Buscar Issues

Use `mcp__linear__list_issues` com:

- `assignee`: valor identificado no passo 1
- `limit`: 50 (ou mais se necessário)

**IMPORTANTE**: Ignore issues com estado "Completed", "Done", "Canceled" ou "Cancelled". Mostre apenas issues ativas.

### 3. Ordenar e Exibir Resultado

**Ordenação das linhas** (nesta ordem de prioridade):

1. **Time** (alfabética)
2. **Status** (In Progress > In Review > Refinamento > Detalhamento > Planejado > Todo > Backlog > Ideia)
3. **Prioridade** (Urgent > High > Medium > Low > sem prioridade)
4. **Due Date** (com data primeiro, sem data depois)
5. **Título** (alfabética)

**Formato** (tabela única com issues ordenadas):

# Issues de [NOME_PESSOA]

| Time | Status      | Prioridade | Due Date   | Título                 | Labels | URL |
| ---- | ----------- | ---------- | ---------- | ---------------------- | ------ | --- |
| AAA  | In Progress | High       | 2025-01-25 | AAA-10 Título da issue | Label1 | url |
| AAA  | Todo        | Medium     | -          | AAA-20 Título da issue | Label2 | url |
| BBB  | In Progress | High       | -          | BBB-15 Título da issue | -      | url |

**Colunas:**

- Time: sigla do time
- Status: estado atual
- Prioridade: se não definida, usar `-`
- Due Date: se não definida, usar `-`
- Título: identificador + título da issue
- Labels: se não existirem, usar `-`
- URL: `[link](url)` (última coluna)

### 4. Resumo

Ao final, mostre um resumo em tabela com os status encontrados:

## Resumo

| Team      | Total  | In Progress | In Review | Detalhamento | Planejado | Ideia  |
| --------- | ------ | ----------- | --------- | ------------ | --------- | ------ |
| AAA       | X      | Y           | -         | Z            | W         | V      |
| BBB       | X      | Y           | -         | Z            | W         | V      |
| **Total** | **XX** | **YY**      | **-**     | **ZZ**       | **WW**    | **VV** |

**Nota:** Inclua apenas colunas de status que existam nas issues retornadas.

## Exemplos de Uso

- `/linear-my-issues` → lista issues ativas do usuário logado (detecta email automaticamente)
- `/linear-my-issues joao@gabriel.com.br` → issues ativas do João
- `/linear-my-issues Maria` → issues ativas da Maria
