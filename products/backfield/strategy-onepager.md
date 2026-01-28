# Backfield - Strategy One-Pager

**Autor:** Rafael Vaz | **Data:** 2026-01-23 | **Status:** Draft

---

## The Formula

```
Product Strategy = Vision + Insights + Challenges + Approaches + Accountability
```

---

## 1. Vision (ESSENCE)

### Vision Statement

> **Para** times operacionais da Gabriel (CGS, Suprimentos, Técnicos) **que** precisam gerenciar OS's, estoque e provisionamento de forma eficiente,
> **o** Backfield **é uma** plataforma de operações de campo
> **que** integra todos os sistemas em um ecossistema unificado no Bifrost.
> **Ao contrário de** Airtable, planilhas e sistemas desconectados,
> **nosso produto** oferece integração end-to-end com automação de processos.

### What | Who | Why Now

|             |                                                                                      |
| ----------- | ------------------------------------------------------------------------------------ |
| **What**    | Operações fragmentadas em Airtable/planilhas que não escalam                         |
| **Who**     | CGS, Técnicos Parceiros, Suprimentos, Backoffice                                     |
| **Why Now** | Deadline Airtable (15/04), integração 3PL, escala (5k contratos), C3 (novo hardware), DCe (compliance) |

---

## 2. Insights (LOGIC)

### Contexto

| Métrica | Valor |
|---------|-------|
| Contratos ativos | ~5.000 |
| OS's/mês | 1.500-3.000 |
| Regiões | SP, RJ, MG |
| Meta MRR 2026 | R$ 7M |

### Tendências 2026

1. **Expansão geográfica:** Novos parceiros e locais de estoque
2. **Aumento de volume:** Mais OS's exigem mais automação
3. **Novos serviços:** Camaleão 3, novos fluxos de provisionamento
4. **Eficiência:** Pressão para fazer mais com menos

### Personas Principais

**CGS:** _"Passo metade do dia copiando dados entre sistemas."_
- Dor: Tempo em tarefas manuais

**Técnico Parceiro:** _"Fico esperando o CGS para resolver coisas simples."_
- Dor: Dependência do suporte interno

---

## 3. Challenges (ROADBLOCKS)

| Categoria | Desafio Principal |
|-----------|-------------------|
| **Técnico/Operacional** | Migração Airtable → Bifrost (dados, OS, automações) até 15/04 — se não migrar, operação para |
| **Time** | 2 engenheiros Jr; entregas complexas podem precisar de apoio |
| **Legal** | DCe obrigatória (06/04) |

---

## 4. Approaches (PATHS)

### Estratégia

**Abordagem:** Feature Parity + Migração

| Fase | Período | Foco |
|------|---------|------|
| **Migração Crítica** | Q1/2026 (até 15/04) | Estoque + OS + automações Airtable no Bifrost, integração 3PL, provisionamento C3 |
| **Evolução** | Q2-Q3/2026 | DCe, serialização de estoque, novas fases de OS |
| **Escala + Automação** | Q4/2026 | Automação end-to-end, preparação para 10k+ contratos |

### Guardrails

| Do's | Don'ts |
|------|--------|
| Priorizar migração sobre features novas | Criar features antes de migrar |
| Manter feature parity | Customizar para casos específicos |
| Documentar decisões no Linear | Acumular débito técnico |
| Comunicar mudanças proativamente | Depender de Airtable após 15/04 |

### Posicionamento

> **Backfield é PLATAFORMA que serve Operações.**
> Construímos capacidades genéricas; Operações configura e opera.

---

## 5. Accountability (MEASURE)

### North Star

| Fase | Métrica | Baseline | Target |
|------|---------|----------|--------|
| **2026 (Migração)** | % fluxos no Bifrost | ~20% | 80% (Abr/26) → 100% (Jun/26) |
| **2027+ (Escala)** | Taxa de automação | TBD | TBD |

### Métricas de Suporte

| Métrica | Target Q4/2026 |
|---------|----------------|
| Uptime dos sistemas | 99.9% |
| Taxa de OS's produtivas | +10% |
| Divergências de estoque | -50% |
| Chamados ao CGS (por OS) | -40% |

---

## Sign-off

| Stakeholder | Cargo | Aprovado |
|-------------|-------|----------|
| Matias Montangero | Líder de Operações | ☐ |
| Felipe França | Lead CGS | ☐ |
| Victor Esteves | Suprimentos | ☐ |
| [EM Plataforma] | Engineering Manager | ☐ |

---

_Full document available at: `products/backfield/strategy.md`_
