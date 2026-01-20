# Engineering Requirements Document (ERD)

> **Copie este template** para criar um novo ERD.

---

## Visão Geral

Dois modelos de ERD, divididos em dois níveis (Projeto e Tarefa):

| Nível   | Template                        | Uso                                     |
| ------- | ------------------------------- | --------------------------------------- |
| Projeto | [erd-projeto.md](erd-projeto.md) | Arquitetura, decisões de alto nível    |
| Tarefa  | [erd-tarefa.md](erd-tarefa.md)   | Implementação, contratos, low-level    |

---

## Princípios

1. **Todo Projeto e toda Tarefa deve ter ERD**. Projetos acompanham PRD; Tarefas acompanham descrição (user story, bug, spike).

2. **Engenharia pode criar itens em upstream** e justificar decisões exclusivamente no ERD.

3. **Uma página, aberto a anexos** — diagramas, PoCs, decisões profundas vão como anexos.

4. **Artefato vivo durante upstream**, congela ao entrar em execução.

5. **Campo explícito para impacto em outros times** — criar previsibilidade e antecipar dependências.

6. **Rápido de escrever, claro para sustentar decisões**. Se virar gargalo, revisitar abordagem.

---

## Integração com Linear

- Ambos ERDs devem ser anexados como **resources** do tipo `document` em Projects e Issues.
- Documentações técnicas finais devem morar em lugares mais perenes (documentos no Linear têm busca fraca).

---

## Quando usar qual?

```
PRD (Product) ──► ERD-P (Projeto) ──► ERD-T (Tarefa) ──► Código
```

- **ERD-P**: Inicia com o projeto, define arquitetura e decisões macro
- **ERD-T**: Uma por tarefa/issue, detalha implementação específica
