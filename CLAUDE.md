# CLAUDE.md

Instruções para AI assistants trabalhando neste repositório.

## Contexto

Repositório central de documentação da área de tecnologia da Gabriel. Docs-only (código em repos separados).

## Estrutura do Repositório

| Diretório              | Função                                                          |
| ---------------------- | --------------------------------------------------------------- |
| `products/`            | Documentação de produtos (visão de negócio, roadmap)            |
| `tribes/`              | Estrutura organizacional (tribes, squads, decisões)             |
| `building-directives/` | Processos de engenharia (handbook, discovery, design, delivery) |
| `people/`              | Gestão de pessoas (onboarding, 1:1s, hiring)                    |
| `incidents/`           | Gestão de incidentes (severidade, postmortems)                  |
| `templates/`           | Templates reutilizáveis (ERD, PRD, product, squad)              |

## Relacionamentos

- **1 Tribe → N Products**: Tribe Borda é dona de 4 produtos, Produtos Digitais de 3
- **Squads operam assets**: Squad App Gabriel opera os repos do app mobile

## Estrutura Organizacional

- **Org**: ~40-60 pessoas
- **Tribes**: Borda, Produtos Digitais, Plataforma
- **Metodologia**: Scrum/Kanban

## Diretrizes de Decisão

### Ao tomar decisões técnicas:

1. **Documente primeiro** - Antes de implementar, documente
2. **Consulte stakeholders** - Liste quem precisa ser consultado
3. **Considere trade-offs** - Explique prós e contras
4. **Defina critérios de sucesso** - Como saberemos se funcionou?

### Níveis de decisão:

| Nível | Escopo                 | Quem decide               | Documentação           |
| ----- | ---------------------- | ------------------------- | ---------------------- |
| Squad | Implementação local    | Squad                     | Comentário no Linear   |
| Tribe | Afeta múltiplos squads | Engineering Manager + GPM | ERD + PRD ou Diretivas |
| Org   | Afeta múltiplas tribes | CPTO                      | Product Decision       |

### Princípios:

- **Simplicidade** - Prefira soluções simples
- **Reversibilidade** - Prefira decisões reversíveis
- **Dados** - Baseie decisões em dados quando possível
- **Documentação** - Se não está documentado, não existe

## Convenções deste Repo

- Documentos em Português
- Markdown para tudo
- Nomes de arquivo: lowercase com hífens
- Templates em `templates/` para produtos e squads

## Integrações

- **Linear**: Gestão de projetos
- **GitHub**: Código e PRs (assets descobertos via org, não listados aqui)
- **DataDog**: Observabilidade técnica e de produto (analytics)
- **Slack**: Comunicação
- **n8n**: Automações
- **Notion**: Docs legados (migrar para cá)

## Plan mode

- Faça o plano extremamente conciso. Sacrifique a gramática em prol da concisão.
- Ao final de cada plano, forneça-me uma lista de perguntas não resolvidas que preciso responder, se houver.
