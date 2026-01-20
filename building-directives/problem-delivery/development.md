# Development

Padrões de desenvolvimento, branches e pull requests.

**Responsável**: _preencher_

---

## Git Flow

### Branches

| Branch      | Propósito                  | Proteção             |
| ----------- | -------------------------- | -------------------- |
| `main`      | Código em produção         | Protegida, requer PR |
| `develop`   | Integração (se usado)      | Protegida, requer PR |
| `feature/*` | Novas funcionalidades      | Não protegida        |
| `bugfix/*`  | Correções de bugs          | Não protegida        |
| `hotfix/*`  | Correções urgentes em prod | Não protegida        |

### Nomenclatura de Branch

```
<tipo>/LIN-<numero>-<descricao-curta>
```

**Exemplos**:

```
feature/LIN-123-adicionar-login-social
bugfix/LIN-456-corrigir-crash-checkout
hotfix/LIN-789-fix-critical-payment-bug
```

---

## Commits

### Formato

```
<tipo>(<escopo>): <descrição>

[corpo opcional]

[footer opcional]
```

### Tipos

| Tipo       | Quando usar                       |
| ---------- | --------------------------------- |
| `feat`     | Nova funcionalidade               |
| `fix`      | Correção de bug                   |
| `docs`     | Documentação                      |
| `style`    | Formatação, sem mudança de lógica |
| `refactor` | Refatoração                       |
| `test`     | Adição/correção de testes         |
| `chore`    | Manutenção, configs               |

### Exemplos

```
feat(auth): adicionar login com Google

fix(checkout): corrigir cálculo de frete para SP

docs(readme): atualizar instruções de setup

refactor(api): extrair validação para middleware
```

---

## Pull Requests

### Checklist Antes de Abrir PR

- [ ] Código compila sem erros
- [ ] Testes passando localmente
- [ ] Linter sem warnings
- [ ] Testei manualmente o happy path
- [ ] Atualizei documentação (se aplicável)

### Template de PR

```markdown
## Descrição

[O que esse PR faz?]

## Ticket

LIN-XXX

## Tipo de mudança

- [ ] Feature
- [ ] Bugfix
- [ ] Refactor
- [ ] Docs

## Como testar

1. [Passo 1]
2. [Passo 2]
3. [Resultado esperado]

## Screenshots (se aplicável)

[Anexar imagens]

## Checklist

- [ ] Testes adicionados/atualizados
- [ ] Documentação atualizada
- [ ] Self-review feito
```

### Tamanho do PR

| Linhas  | Classificação | Ação                       |
| ------- | ------------- | -------------------------- |
| < 100   | Pequeno       | ✅ Ideal                   |
| 100-300 | Médio         | ⚠️ OK, mas prefira menor   |
| 300-500 | Grande        | ⚠️ Considere dividir       |
| > 500   | Muito grande  | 🔴 Divida obrigatoriamente |

---

## Code Review

### Responsabilidades do Autor

- Descrever claramente o PR
- Responder comentários em < 24h
- Não fazer merge sem aprovação

### Responsabilidades do Reviewer

- Revisar em < 24h (ou comunicar delay)
- Ser construtivo, não destrutivo
- Aprovar ou pedir mudanças (não deixar em limbo)

### O que Verificar

| Aspecto          | Perguntas                    |
| ---------------- | ---------------------------- |
| **Correção**     | O código faz o que deveria?  |
| **Design**       | A solução é adequada?        |
| **Legibilidade** | Consigo entender facilmente? |
| **Testes**       | Tem cobertura adequada?      |
| **Performance**  | Tem problemas óbvios?        |
| **Segurança**    | Tem vulnerabilidades?        |

### Linguagem

**Evite:**

```
"Isso está errado"
"Você deveria fazer X"
"Por que você fez isso?"
```

**Prefira:**

```
"Considere fazer X porque..."
"Uma alternativa seria..."
"Não entendi essa parte, pode explicar?"
```

### Aprovação

- **Mínimo**: 1 aprovação
- **Features críticas**: 2 aprovações
- **Quem pode aprovar**: Qualquer dev do squad

---

## Testes

### Pirâmide de Testes

```
        /\
       /  \     E2E (poucos)
      /────\
     /      \   Integração (alguns)
    /────────\
   /          \ Unitários (muitos)
  /────────────\
```

### Cobertura Mínima

| Tipo de código    | Cobertura      |
| ----------------- | -------------- |
| Lógica de negócio | > 80%          |
| Utils/helpers     | > 90%          |
| UI components     | > 60%          |
| Configs           | Não necessário |

### Quando Escrever Testes

- **Sempre**: Bugs (teste que reproduz antes de fixar)
- **Sempre**: Lógica de negócio crítica
- **Geralmente**: Features novas
- **Opcional**: Refactors pequenos (se já tem teste)

---

## Ambiente Local

### Setup

```bash
# Clone
git clone <repo>
cd <repo>

# Dependências
npm install  # ou yarn, pnpm, etc

# Variáveis de ambiente
cp .env.example .env
# Editar .env com valores locais

# Rodar
npm run dev
```

### Ferramentas Recomendadas

| Ferramenta | Uso             |
| ---------- | --------------- |
| VSCode     | Editor          |
| ESLint     | Linting         |
| Prettier   | Formatação      |
| Docker     | Serviços locais |
