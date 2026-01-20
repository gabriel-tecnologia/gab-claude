# Rituais Ágeis

Todos os rituais da Sprint: quando, quem participa, como funciona, e objetivos.

**Responsável**: Comitê de Tecnologia

---

Nossos rituais estruturam o trabalho e garantem alinhamento entre Produto e Engenharia.

---

## Visão Geral do Ciclo da Sprint

Nossa Sprint tem **2 semanas** e segue este cronograma típico - ajustar os dias para cada time:

### 📅 SEMANA 1

**Segunda-feira**

- 🎬 **Sprint Demo** (30min-1h) - Demonstra o valor entregue
- 🔄 **Retrospectiva** (1h) - Reflete e melhora o processo
- 🎯 **Planning** (1h30-2h) - Define o trabalho da Sprint

> No Linear, um Ciclo têm início ao meio-dia do dia configurado para cada time. Recomendado que todos os ritos de encerramento e a Planning ocorram até um dia antes, ou a manhã de início de um novo Ciclo.

**Terça a Sexta**

- 💻 **Execução** + Daily (15min/dia)

### 📅 SEMANA 2

**Segunda a Sexta**

- 💻 **Execução** + Daily (15min/dia)

> **💡 Daily acontece todos os dias úteis no mesmo horário**

---

## Refinamento Geral

### Informações Gerais

|                                |                                                                                                                                                                                          |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Quando**                     | 1x por semana (dia/horário fixo)                                                                                                                                                         |
| **Duração**                    | 1h (máximo)                                                                                                                                                                              |
| **Facilitador**                | **PM (Product Manager)**                                                                                                                                                                 |
| **Participantes obrigatórios** | PM, PD (Product Designer), Líder de Engenharia, Time de Engenharia                                                                                                                       |
| **Participantes opcionais**    | **GPM** (se a Issue for estratégica ou precisar alinhamento de roadmap), **EM** (quando contexto pedir: complexidade técnica alta, decisões de arquitetura, ou conflitos de priorização) |

### 🎯 Objetivo

Garantir que todos entendem o **"O Quê"** e o **"Por Quê"** de Histórias de Usuário antes de Engenharia investir tempo no "Como".

### 📋 Como funciona

**Preparação (antes do ritual):**
PM deve marcar a **prioridade** de cada Issue (Urgent/High/Medium/Low). Isso ajuda Engenharia a priorizar corretamente no Refinamento Técnico.

**Durante o ritual:**

1. **PM apresenta Issues** da coluna `Refinamento Geral` (máx. 3-5 Issues por sessão)
2. **PM explica para cada Issue:**
   - Contexto e problema que estamos resolvendo
   - Valor esperado (para quem? por quê?)
   - **Critérios de aceite**
3. **PD apresenta o design** (se houver)
4. **Time faz perguntas** para esclarecer dúvidas sobre produto
5. **Time identifica** riscos, dependências ou questões técnicas
6. **Decisão:**
   - ✅ Issue está clara → PM move para `Refinamento Técnico`
   - ❌ Issue não está clara → volta para `Detalhamento`

### ⚠️ Regras importantes

> ❌ **NÃO debatemos "Como" implementar aqui.** Isso é no Refinamento Técnico.

> ✅ **Foco no problema do usuário**, não na solução técnica.

---

## Refinamento Técnico

### Informações Gerais

|                                |                                                                                                                            |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| **Quando**                     | 1x por semana (dia/horário fixo)                                                                                           |
| **Duração**                    | 1h (máximo)                                                                                                                |
| **Facilitador**                | **Líder do time ou Engenheiro Sênior**                                                                                     |
| **Participantes obrigatórios** | Time de Engenharia completo                                                                                                |
| **Participantes opcionais**    | **PM** (se o time precisar esclarecer algo de produto), **EM** (se necessário para decisões estratégicas ou arquiteturais) |

### 🎯 Objetivo

Debater o **"Como"** técnico, quebrar a Issue em Sub-Issues (Tasking) e estimar.

### 📋 Como funciona

1. **Time pega Issues** da coluna `Refinamento Técnico`
   - Priorizar pelas Issues marcadas como High/Urgent pelo PM
2. **Time debate abordagem técnica:**
   - Arquitetura necessária
   - Riscos técnicos
   - Dependências (APIs, serviços, outras Issues)
3. **Time quebra a Issue em `Sub-Issues`:**
   - Cada Sub-Issue é um bloco de entregas que faça sentido
   - Sub-Issues devem ser executáveis (clareza no que fazer)
4. **Time estima a Issue usando Planning Poker:**
   - Escala: Fibonacci **1, 2, 3, 5, 8**
   - Números representam complexidade/esforço relativo (não horas!)
5. **Decisão:**
   - ✅ Issue pontuada e com Sub-Issues → move para `Pronto para Planejar`
   - ❌ Issue não está clara → volta para `Refinamento Geral` ou `Detalhamento`

### 🃏 O que é Planning Poker?

Técnica de estimativa colaborativa - apenas os Engenheiros participam:

1. **Cada pessoa vota simultaneamente** um número da escala Fibonacci (1, 2, 3, 5, 8)
2. Números representam **complexidade/esforço relativo**, não horas
3. **Se há divergência grande**, uma pessoa representando o voto maior e uma pessoa representando o voto menor explicam o raciocínio
4. **Time repete a rodada de votação** até convergir

> **💡 Para times que estão iniciando com o uso do Planning Poker**, uma sugestão é a criação de uma régua para calibragem. Time de engenharia define em conjunto qual é a tarefa de menor complexidade já realizada - esta representará 1 ou 2 pontos; e qual é a tarefa de maior complexidade já realizada - esta representará 8 pontos. A cada Issue a ser pontuada, o time relembra a régua estabelecida para poder executar a votação.
>
> **Dica de site para Planning poker** - não precisa se cadastrar: [Planning poker online | Scrum poker | We Agile You](https://planningpokeronline.com/)

### ❓ Por que Story Points e não horas?

✅ **Ensina o time a pensar junto** sobre complexidade
✅ **Remove pressão individual** sobre tempo - horas são difíceis de estimar e criam pressão desnecessária
✅ **Permite comparar velocidade** entre Sprints
✅ **Ferramenta de mentoria:** compartilhar conhecimento sobre como pensar e resolver um problema

---

## Planning (Planejamento de Sprint)

### Informações Gerais

|                                |                                                                         |
| ------------------------------ | ----------------------------------------------------------------------- |
| **Quando**                     | Dia fixo (primeiro dia da nova sprint ou último dia da sprint corrente) |
| **Duração**                    | 1h - 1h30                                                               |
| **Facilitador**                | **Liderança de Engenharia (EM ou líder do time)**                       |
| **Participantes obrigatórios** | Time de Engenharia completo + PM + PD                                   |

### 🎯 Objetivo

Definir o **compromisso** do time para a Sprint. O que vamos entregar?

### 📋 Como funciona

#### 1. Revisão da Sprint

- O que entregamos? O que não entregamos? Por quê?
- Visualizar Issues `Finalizadas` e `Para Publicar` do Cycle corrente

#### 2. Issues que não foram concluídas na Sprint

Antes de planejar coisas novas, tratar Issues que transbordaram:

| Coluna onde travou                                  | O que fazer                                                                                                                                                 |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Planejado** (não começou)                         | Volta para `Pronto para Planejar`. PM reprioriza. Pode ou não ser replanejada.                                                                              |
| **Em Andamento** (começou, não terminou)            | **REPONTUAR.** Time já aprendeu sobre a complexidade. Estimar quanto falta.                                                                                 |
| **Em Revisão** ou **Em Homologação** (quase pronto) | **Repontuar** (trabalho residual que falta). Se travou por problema técnico, estimar quanto falta. **Prioridade máxima** para concluir no início da Sprint. |

> **⚠️ Regra importante:**
>
> **Issues que já começaram** (Em Andamento, Em Revisão, Em Homologação):
>
> - Devem ser **priorizadas para conclusão** na nova Sprint
> - Ainda passam pela Planning para time revalidar e repontuar
> - Podem continuar no Cycle novo (não voltam para backlog)
>
> **Issues em Planejado** (não começaram):
>
> - Voltam para `Pronto para Planejar`
> - PM reprioriza
> - Podem ou não ser replanejadas
>
> Isso evita: Sprint virando uma "bola de neve" de trabalho inacabado.

#### 3. Definição do Objetivo da Sprint (opcional)

- PM apresenta a prioridade: qual o tema/foco desta Sprint?
- **Exemplo:** "Concluir o fluxo de checkout" ou "Estabilizar o sistema de notificações"

#### 4. Seleção de Issues

- Liderança de Engenharia apresenta Issues prioritárias de `Pronto para Planejar` na ordem de prioridade - incluindo Issues técnicas para negociação com PM
- Para cada Issue:
  - Já está pontuada? (Se não, estima agora)
  - Cabe na capacidade do time?
  - Tem alguma dependência? (Se sim, analisar se vale incluir na sprint ou deixar para a próxima)
- Time **puxa** Issues para o Cycle atual (move para coluna `Planejado`)
- Continue até atingir a capacidade do time

#### 5. Compromisso

- Time revisa tudo que foi planejado
- Time se compromete com o acordado ou solicita alterações

### 📊 Como calcular capacidade do time?

**Nas primeiras 3 Sprints:**

- Começar **conservador**
- Ex: 2-3 Issues pequenas por pessoa
- **Foco é aprender**, não entregar muito

**Após 3 Sprints:**
Usar **velocity** = média de pontos entregues nas últimas 3 Sprints

**Exemplo:**

- Sprint 1 = 21 pontos
- Sprint 2 = 18 pontos
- Sprint 3 = 24 pontos
- Velocity = (21+18+24)/3 = **21 pontos**
- Planejar ~21 pontos para próxima Sprint

**Considerar:**

- Férias, feriados
- Reuniões fora do normal
- Reservar ~20% para imprevistos (bugs, suporte)

### ⚖️ Regra de ouro

> **⚠️ Só pode planejar Issues que estão em Pronto para Planejar.**
>
> Nada de puxar Issues mal detalhadas.
> Não executar sub-tarefas que não estejam definidas na tarefa.

---

## Daily (Reunião Diária)

### Informações Gerais

|                                |                                           |
| ------------------------------ | ----------------------------------------- |
| **Quando**                     | Todo dia útil, mesmo horário              |
| **Duração**                    | 15 minutos (máximo!)                      |
| **Facilitador**                | **Rotativo** (cada dia um membro do time) |
| **Participantes obrigatórios** | Time de Engenharia completo               |
| **Participantes opcionais**    | PM (ouvinte, para acompanhamento)         |

### 🎯 Objetivo

Sincronização rápida. Identificar bloqueios e manter o time alinhado sobre o progresso da Sprint.

### 📋 Formato

Cada pessoa responde rapidamente:

1. **O que fiz ontem?** (Issue/Sub-Issue trabalhada)
2. **O que vou fazer hoje?** (próxima Issue/Sub-Issue)
3. **Tenho algum bloqueio?** (impedimento, dúvida, dependência)

### 💻 Como usar o Linear na Daily

- Facilitador abre o board do Cycle atual
- Percorrer as colunas: `Em Andamento` → `Em Revisão` → `Em Homologação`

### ⚠️ Regras importantes

> ❌ **NÃO é reunião de solução de problemas.**
>
> Se surgir debate longo, marque conversa separada depois.
> Não definir caminhos ou tirar dúvidas técnicas na daily. Caso uma dúvida técnica esteja impedindo seguir, levante como block e resolva depois da daily.

> ✅ **Stand-up literal.**
>
> Time fica de pé para manter energia e brevidade.

> ✅ **Foco no compromisso da Sprint.**
>
> Não falar de trabalho fora do Cycle.

---

## Sprint Demo (Demonstração)

### Informações Gerais

|                                |                                                                    |
| ------------------------------ | ------------------------------------------------------------------ |
| **Quando**                     | Último dia da Sprint                                               |
| **Duração**                    | 30min - 1h                                                         |
| **Facilitador**                | **PM**                                                             |
| **Participantes obrigatórios** | Time de Engenharia, PM                                             |
| **Participantes opcionais**    | CPO, GPM, **EM**, outros stakeholders, qualquer pessoa interessada |

### 🎯 Objetivo

Mostrar o **valor entregue** na Sprint. Celebrar o trabalho e coletar feedback.

### 📋 Como funciona

#### 1. PM abre o board do Linear:

- Filtra pelo Cycle que acabou
- Mostra Issues nas colunas `Finalizada` e `Para Publicar`

#### 2. Time demonstra as entregas:

Para cada Issue:

- Mostrar funcionando no ambiente de **produção** (ou staging se não foi pra prod ainda)
- Explicar brevemente: o que foi feito e **por quê é importante**
- **Demonstração AO VIVO** sempre que possível (não slides!)
- Sempre que pertinente, mostrar quais OKRs ou KPIs da empresa serão impactados

#### 3. Stakeholders fazem perguntas e dão feedback

#### 4. Reconhecimento:

- PM destaca desafios superados
- Time comemora conquistas

### ⚠️ Regra importante

> **⚠️ Só demonstra o que está realmente pronto (passou pela DoD).**
>
> Não mostrar trabalho pela metade.

---

## Retrospectiva

### Informações Gerais

|                                |                                 |
| ------------------------------ | ------------------------------- |
| **Quando**                     | Último dia da Sprint            |
| **Duração**                    | 1h                              |
| **Facilitador**                | **EM**                          |
| **Participantes obrigatórios** | Time de Engenharia completo, PM |

### 🎯 Objetivo

Refletir sobre o processo. O que funcionou? O que não funcionou? **Como melhorar?**

### 📋 Formato (Start/Stop/Continue) - sugestão/exemplo

#### 1. Check-in (5min)

Como cada um está se sentindo e revisão dos itens de ação da agenda anterior (rápido).

#### 2. Coleta de Itens (5min)

Cada pessoa pensa e escreve (post-its em ferramenta digital):

- 🟢 **Continue**: O que funcionou bem e devemos manter
- 🔴 **Stop**: O que não funcionou e devemos parar de fazer
- 🟡 **Start**: O que devemos começar a fazer

#### 3. Discussão (10min)

- Facilitador agrupa itens similares
- Time discute os principais pontos
- Priorizar: **Qual o problema mais importante para atacar?**

#### 4. Ações (10min)

- Definir **1-3 ações concretas** para a próxima Sprint
- Cada ação tem um **responsável** e um **prazo**

**Exemplo de ação BOA:**
✅ "Ana vai criar um template de PR description até quarta-feira"

**Exemplo de ação RUIM:**
❌ "Vamos nos comunicar melhor"

#### 5. Check-out (5min)

Como foi a Retro? Fechamento rápido.

### ⚠️ Regras importantes

> **💚 Espaço seguro.**
>
> Foco em melhorar o processo, não culpar pessoas.

> **✅ Ações práticas.**
>
> Nada de "vamos nos comunicar melhor" sem definir COMO.

> **📋 Acompanhamento.**
>
> Na próxima Retro, revisar se as ações foram feitas.
