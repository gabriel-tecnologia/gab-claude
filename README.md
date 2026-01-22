# Gabriel Claude

> ⚠️ **Proposta Inicial de Framework de Trabalho com AI**
>
> Este repositório é uma proposta inicial de framework para organização e trabalho da área de tecnologia da Gabriel com AI. Não existe hoje um padrão de mercado consolidado sobre como estruturar uma área corporativa em conjunto com AI — por isso, esta é uma proposta que precisa ser amadurecida coletivamente até chegarmos em um bom lugar, ou até que o mercado estabeleça um framework padrão que possamos adotar.
>
> Contribuições, críticas e sugestões são bem-vindas.

## Diretrizes de Uso

> 🧠 **Use e abuse do Plan Mode!** O sucesso do uso da ferramento DEPENDE de um bom plano. Aperte Shift+Tab duas vezes, entre no plan mode e escope sua tarefa muito bem antes da execução
>
> 🧪 **Antes de mais nada: experimente!** Teste comandos, edite workflows, quebre coisas. Só assim você descobre como AI pode turbinar seu dia.

- **Supervisão humana é inegociável** — AI constrói rápido, mas você assina embaixo. Revise sempre.
- **Itere sem dó** — Primeira resposta raramente é a melhor. Refine, questione, peça de novo.
- **AI é par, não oráculo** — Você traz contexto e julgamento. Ela traz velocidade e padrões.
- **Comece pelo simples** — Domine tarefas pequenas antes de entregar o mundo.
- **Compartilhe descobertas** — Achou um prompt matador? Joga no canal. A equipe agradece.
- **Desconfie de dados específicos** — Nomes, métricas, datas... AI pode inventar com convicção impressionante.

Repositório central de documentação da área de tecnologia. Código fica em repositórios separados.

## Recursos Disponíveis

### 🏠 Nativos do Claude Code

#### Agents Nativos

| Agent               | O que faz                                                                               |
| ------------------- | --------------------------------------------------------------------------------------- |
| `Explore`           | Vasculha o codebase em segundos — encontra arquivos, patterns e responde "onde fica X?" |
| `Plan`              | Arquiteto de software que planeja antes de sair codando                                 |
| `Bash`              | Executa comandos de terminal — git, npm, docker, o que precisar                         |
| `claude-code-guide` | Tira dúvidas sobre Claude Code, SDK e API — o manual ambulante                          |

---

### 🏗️ Construídos Internamente

#### Skills de Engenharia

| Comando/Agent                       | O que faz                                                                      |
| ----------------------------------- | ------------------------------------------------------------------------------ |
| `/engineering-code-review`          | Code review com olhar de engenharia — arquitetura, patterns, o pacote completo |
| `/engineering-backend-patterns`     | Consultor de API, banco e Node.js que não cobra por hora                       |
| `/engineering-frontend-patterns`    | Patterns de React/Next.js pra não reinventar a roda quadrada                   |
| `/engineering-security-review`      | Acha as vulnerabilidades antes do hacker achar                                 |
| `/engineering-interface-guidelines` | Checa acessibilidade e boas práticas de UI                                     |
| `engineering-error-resolver`        | Resolve erros de build/TypeScript com mínimo de drama                          |
| `engineering-refactor-cleaner`      | Caça código morto e duplicado — Marie Kondo do codebase                        |
| `engineering-code-simplifier`       | Simplifica código complexo mantendo funcionalidade                             |
| `engineering-technical-refinement`  | Refina tarefas técnicas com contexto de issue/projeto                          |

#### Skills de Produto

| Comando              | O que faz                                                       |
| -------------------- | --------------------------------------------------------------- |
| `/product-prd`       | Gera PRD completo — ideal pra quando o PM tá de férias          |
| `/product-story`     | Transforma ideias vagas em user stories que o dev entende       |
| `/product-strategy`  | Monta estratégia de produto com visão e direção                 |
| `/product-discovery` | Sessão de discovery guiada — explora conceito, modelo, jornadas |

#### Skills de Linear

| Comando                | O que faz                                         |
| ---------------------- | ------------------------------------------------- |
| `/linear-create-issue` | Cria issue no Linear sem sair do terminal         |
| `/linear-my-issues`    | Lista suas issues do Linear (spoiler: são muitas) |

#### Custom Commands

| Comando                     | O que faz                                              |
| --------------------------- | ------------------------------------------------------ |
| `/rams`                     | Review de acessibilidade e design visual               |
| `/web-interface-guidelines` | Checa código UI contra Vercel Web Interface Guidelines |

---

### 🧩 Plugins Externos

#### `commit-commands`

| Comando           | O que faz                                                                           |
| ----------------- | ----------------------------------------------------------------------------------- |
| `/commit`         | Cria commit com mensagem decente sem pensar em conventional commits às 18h de sexta |
| `/commit-push-pr` | Commit + push + PR num comando só — pra quem não tem tempo pra três enters          |
| `/clean_gone`     | Limpa branches mortas que o remote já esqueceu mas seu PC ainda guarda              |

#### `code-review`

| Comando        | O que faz                                                                     |
| -------------- | ----------------------------------------------------------------------------- |
| `/code-review` | Revisa seu PR como aquele colega detalhista (mas sem a passivo-agressividade) |

#### `frontend-design`

| Comando            | O que faz                                                                 |
| ------------------ | ------------------------------------------------------------------------- |
| `/frontend-design` | Cria interfaces bonitas de verdade, não aquele Bootstrap genérico de 2015 |

#### `ralph-loop`

| Comando         | O que faz                                                      |
| --------------- | -------------------------------------------------------------- |
| `/ralph-loop`   | Inicia loop de execução autônoma — Claude no piloto automático |
| `/cancel-ralph` | Para o Ralph Loop antes que ele domine o mundo                 |
| `/help`         | Explica o que é o Ralph Loop e seus comandos                   |

---

### 🔌 Integrações MCP

| Integração  | O que faz                                                             |
| ----------- | --------------------------------------------------------------------- |
| **GitHub**  | PRs, issues, repos, reviews — tudo sem abrir o navegador              |
| **Slack**   | Lê canais, posta mensagens, reage com emoji — networking automatizado |
| **Linear**  | Issues, projetos, sprints — seu backlog na ponta dos dedos            |
| **Datadog** | Logs, métricas, monitors, incidents — debug em produção sem pânico    |
| **n8n**     | Cria e gerencia workflows de automação — Zapier com esteroides        |
| **Chrome**  | Controla o navegador — clica, navega, preenche forms, tira screenshot |

## Estrutura

| Diretório              | Conteúdo                                            |
| ---------------------- | --------------------------------------------------- |
| `business-context/`    | Contexto da empresa, produtos e área de tecnologia  |
| `products/`            | Catálogo de produtos (visão de negócio, roadmaps)   |
| `building-directives/` | Processos de engenharia (handbook, discovery, etc.) |
| `incidents/`           | Severidade, resolução, postmortems                  |
| `templates/`           | Templates reutilizáveis (ERD, PRD, squads)          |

## Quick Links

- **Contexto Gabriel** → [Empresa](./business-context/company-context.md) · [Produtos](./business-context/products-overview.md) · [Área Tech](./business-context/technology-area.md)
- **Incidente?** → [Processo](./incidents/README.md)
- **Templates** → [Ver todos](./templates/)

## Contribuindo

1. Crie uma branch a partir de `main`
2. Faça suas alterações
3. Abra um PR com descrição clara
4. Solicite review de pelo menos 1 pessoa

## Integrações com AI

Configurações para AI assistants em [.claude/](./.claude/) e [CLAUDE.md](./CLAUDE.md).

## Convenções

- **Linguagem**: Português
- **Formato**: Markdown
- **Nomes de arquivo**: lowercase com hífens (`meu-documento.md`)

## Dúvidas?

Abra uma issue ou pergunte no canal #engenharia no Slack.
