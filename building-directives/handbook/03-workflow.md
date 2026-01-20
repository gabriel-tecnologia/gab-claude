# Workflow e Processo

O fluxo completo de uma Issue: Upstream (Discovery) → Delivery → Produção.

**Responsável**: Comitê de Tecnologia

---

O workflow é o nosso processo visual. Ele garante que as Issues passem por todas as etapas necessárias de maturação (Upstream/Discovery) e construção (Delivery) antes de chegarem ao cliente final.

---

## Visão Geral

```
UPSTREAM (Backlog)                    DELIVERY (Active)
──────────────────                    ─────────────────

Ideia                                  Planejado
  ↓                                       ↓
Detalhamento                           Em Andamento
  ↓                                       ↓
Refinamento Geral                      Em Revisão
  ↓                                       ↓
Refinamento Técnico                    Em Homologação
  ↓                                       ↓
Pronto para Planejar                   Para Publicar
                                          ↓
                                       Finalizada
```

> **📌 Regra fundamental:** Issues só avançam se atenderem os critérios de cada fase.

---

## Fase Upstream (Backlog)

Esta fase acontece nas colunas da categoria `Backlog` no Linear.

**Objetivo:** Transformar uma Ideia em uma `Issue` **100% pronta para desenvolvimento**.

### Colunas do Upstream

| Coluna (Status)          | Dono Principal                              | Propósito                                                                                                                                                              |
| ------------------------ | ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ideia**                | Todos                                       | Rascunho. Qualquer pessoa pode criar uma ideia de `Issue`.                                                                                                             |
| **Detalhamento**         | Produto (PM, GPM) ou Engenharia (Líder, EM) | Detalhamento feito pelo responsável da demanda. **Se Produto:** escrever o "O Quê" e o "Por Quê". **Se Engenharia:** escrever o "O Quê" técnico.                       |
| **Refinamento Geral**    | Produto (PM)                                | **Ritual do Time (PM + PD + Eng).** PM apresenta a história. Objetivo: garantir que o "O Quê" e o "Por Quê" estão claros antes de Engenharia investir tempo no "Como". |
| **Refinamento Técnico**  | Engenharia (Time)                           | **Ritual do Time (Eng).** Time debate o "Como", identifica riscos e quebra a `Issue` em `Sub-Issues`. Estima a Issue.                                                  |
| **Pronto para Planejar** | Produto (PM, GPM) ou Engenharia (Líder, EM) | **A "Definition of Ready" (DoR).** A `Issue` está 100% pronta (detalhada, refinada, com design se aplicável, pontuada) para ser puxada na Planning.                    |

> **💡 Sobre customização de colunas:** As colunas acima são o padrão mínimo obrigatório. Cada time pode customizar, adicionando novas colunas, conforme sua realidade, mas sempre respeitando o fluxo básico: **Ideia → Detalhamento → Refinamento → Pronto**. Qualquer mudança nas colunas deve ser discutida com EM/GPM e documentada no board do time.

---

## Definition of Ready (DoR)

Uma `Issue` só pode ser movida para **"Pronto para Planejar"** se atender TODOS os critérios estabelecidos pelo time:

### ✅ Para Histórias de Usuário - exemplo:

- [ ] Descrição clara do "O Quê" e "Por Quê" (contexto, problema, valor esperado)
- [ ] Critérios de Aceite escritos (como saberemos que está pronto?)
- [ ] Design pronto, se aplicável (mockups, fluxos, specs visuais)
- [ ] Refinada com o time (Refinamento Geral feito)
- [ ] Refinada tecnicamente (plano de execução)
- [ ] Pontuada (estimativa de esforço definida)
- [ ] Sem dependências bloqueadoras (ou dependências mapeadas e resolvidas)
- [ ] **Prioridade definida** (Urgent/High/Medium/Low)

### ✅ Para Histórias Técnicas - exemplo:

- [ ] Descrição clara do problema técnico e motivação
- [ ] Abordagem técnica discutida e acordada
- [ ] Refinada tecnicamente (plano de execução)
- [ ] Pontuada (estimativa de esforço definida)
- [ ] Impacto/riscos avaliados
- [ ] **Prioridade definida** (Urgent/High/Medium/Low)

> **⚠️ Importante:** Se uma Issue não atende todos os critérios da DoR, ela **não deve** ser planejada na Sprint. Volte para a coluna apropriada (Detalhamento ou Refinamento). O DoR pode ser customizado para se adequar ao contexto do time.

---

## Fase Delivery (Active)

Esta fase acontece nas colunas da categoria `Active`.

**Objetivo:** Planejar e executar a entrega para uma Sprint (`Cycle`).

### Colunas do Delivery

| Coluna (Status)    | Responsável Principal | Propósito                                                                                                                                |
| ------------------ | --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Planejado**      | Time de Engenharia    | O **Backlog da Sprint**. O que o time se comprometeu a fazer na Planning.                                                                |
| **Em Andamento**   | Engenheiro            | Engenheiro puxa uma `Issue` e está ativamente trabalhando nela. **⚠️ WIP Limit: máximo 1 Issue e/ou Sub-Issue por pessoa nesta coluna.** |
| **Em Revisão**     | Engenheiro            | Engenheiro terminou de codar, abriu um Pull Request (PR) e aguarda o Code Review de um par.                                              |
| **Em Homologação** | PM (Produto)          | PR foi aprovado e "mergeado" para o ambiente de homologação (Staging). PM valida a entrega.                                              |
| **Para Publicar**  | Time de Engenharia    | PM validou. A `Issue` está na "fila" para deploy em produção.                                                                            |
| **Finalizada**     | Time de Engenharia    | A `Issue` está em produção e o valor foi entregue. ✅                                                                                    |

> **💡 Sobre customização de colunas:** As colunas acima são o padrão mínimo obrigatório. Cada time pode customizar, adicionando novas colunas, conforme sua realidade, mas sempre respeitando o fluxo básico: **Planejado → Em andamento → Em Revisão → Em Homologação → Para Publicar → Finalizada**. Qualquer mudança nas colunas deve ser discutida com EM/GPM e documentada no board do time.

---

## Definition of Done (DoD)

Uma `Issue` só pode ser marcada como **"Finalizada"** se atender TODOS estes critérios estabelecidos pelo time:

### ✅ Checklist obrigatória - exemplo:

- [ ] Código desenvolvido e atende todos os Critérios de Aceite
- [ ] Code Review aprovado por pelo menos 1 par
- [ ] Testes escritos (unitários, integração - conforme padrão do time)
- [ ] PR mergeado na branch principal
- [ ] Deploy feito em Staging
- [ ] Validado pelo PM em Staging (homologação passou)
- [ ] Deploy feito em Produção
- [ ] Sem bugs conhecidos (ou bugs documentados como Issues novas)
- [ ] Documentação atualizada, se necessário (README, Wiki, etc.)
- [ ] **Todas as Sub-Issues estão finalizadas**

> **⚠️ Importante:** Não demonstre na Sprint Demo ou marque como "Finalizada" trabalho que não passou por TODA a DoD. O DoD pode ser customizado para se adequar ao contexto do time.
