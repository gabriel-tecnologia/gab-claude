# Como Começar

Guia para implementação nas primeiras Sprints. Expectativas realistas e erros comuns.

**Responsável**: Comitê de Tecnologia

---

Se você está lendo isso, é provável que esteja implementando esse processo pela primeira vez. É normal ter dúvidas e errar. Aqui vai um guia de expectativas realistas:

---

## Primeiras 3 Sprints = Aprendizado

### Sprint 1-2: Começar a descobrir a capacidade real

- Planeje **pouco**
- Foco em **aprender o fluxo**, não em entregar muito
- É normal não entregar tudo - **está tudo bem!**
- Use a Retro para ajustar

### Sprint 3-5: Calibrar estimativas

- Começar a usar velocity (média de pontos entregues)
- Ajustar tamanho das Issues (se estão muito grandes/pequenas)
- Melhorar qualidade dos Refinamentos

### Sprint 6+: Previsibilidade

- Velocity estabiliza
- Time ganha confiança nas estimativas
- Processo começa a fluir naturalmente

---

## Erros comuns e como evitar

### ❌ Planejar Issues mal detalhadas

**Por quê acontece:** Pressão para "entregar rápido"

**Como evitar:** Seja rigoroso na DoR. Se não está pronto, não planeja.

---

### ❌ Mudar o scope da Issue no meio da Sprint

**Por quê acontece:** "Descobrimos que precisamos de mais uma coisa"

**Como evitar:** Se surgir mudança, criar Issue nova e replanejar na próxima Sprint.

---

### ❌ Pular Retrospectiva porque "está tudo bem"

**Por quê acontece:** Time cansado

**Como evitar:** Retro é obrigatória. Sempre tem o que melhorar.

---

### ❌ Não atualizar o board

**Por quê acontece:** Esquecimento

**Como evitar:** Criar hábito de mover Issues **em tempo real**, não aguardar a Daily.

---

### ❌ Acumular muitas Issues "Em Revisão"

**Por quê acontece:** Time não prioriza code review

**Como evitar:** Code review é **prioridade**. Parar de começar coisas novas e revisar primeiro.

---

## Acompanhando o Progresso e Métricas

O Linear calcula automaticamente várias métricas que ajudam o time a entender seu desempenho e identificar gargalos.

### 📊 Principais métricas no Linear

#### 1. Velocity (Velocidade)

**O que é:** Média de Story Points entregues por Sprint

**Como ver no Linear:**

- Vá em `Cycles`
- Veja o gráfico de "Completed points" por Cycle

**Para que serve:**

- Planejar a capacidade das próximas Sprints
- Identificar se o time está sobrecarregado ou subaproveitado

**Como interpretar:**

```
Sprint 1: 15 pontos
Sprint 2: 22 pontos
Sprint 3: 18 pontos
Velocity média = (15+22+18)/3 = 18 pontos

→ Planeje ~18 pontos na próxima Sprint
```

---

#### 2. Cycle Time (Tempo de Ciclo)

**O que é:** Tempo que uma Issue leva de "Em Andamento" até "Finalizada"

**Como ver no Linear:**

- Vá em `Insights` → `Issues`
- Filtre por "Cycle time"

**Para que serve:**

- Identificar Issues que travam
- Entender gargalos no processo (Ex: Issues ficam muito tempo em "Em Revisão"?)

**Como interpretar:**

```
Cycle time médio: 3 dias → BOM ✅
Cycle time médio: 10 dias → Investigar! ⚠️

Se Issues ficam muito tempo em "Em Revisão":
→ Melhorar processo de code review
```

---

#### 3. Lead Time (Tempo de Entrega Total)

**O que é:** Tempo que uma Issue leva de "Ideia" até "Finalizada"

**Como ver no Linear:**

- Vá em `Insights` → `Issues`
- Filtre por "Lead time"

**Para que serve:**

- Medir a eficiência do processo completo (Discovery + Delivery)
- Identificar se Issues ficam muito tempo no Upstream

**Como interpretar:**

```
Lead time médio: 2 semanas → BOM ✅
Lead time médio: 6 semanas → Muito longo! ⚠️

Se Issues ficam muito tempo em "Detalhamento":
→ PM precisa priorizar melhor ou ter mais clareza
```

---

#### 4. Completed vs Planned (Entregue vs Planejado)

**O que é:** % de Issues planejadas que foram realmente entregues

**Como ver no Linear:**

- Vá em `Insights` → `Cycles`
- Compare "Scope issues" vs "Completed issues"

**Para que serve:**

- Medir previsibilidade do time
- Identificar se estamos planejando demais

**Como interpretar:**

```
80-100% entregue → Excelente! ✅
50-70% entregue → Planejando demais ou subestimando? ⚠️
100% toda Sprint + folga → Planejando de menos? 🤔
```

---

### 🎯 Como usar as métricas

**Na Planning:**

- Use **Velocity** para decidir quantos pontos planejar

**Na Daily:**

- Olhe **Cycle time** das Issues em andamento
- Se uma Issue está há 5+ dias "Em Revisão", priorizem!

**Na Retrospectiva:**

- Analise **Completed vs Planned/Scope**
- Discuta: Por que não entregamos tudo?
- Olhe **Lead time**: Issues estão travando no Upstream? (futuro!)

---

### ⚠️ Cuidados com métricas

> ❌ **NÃO use métricas para cobrar pessoas individualmente**
>
> Métricas são sobre o **processo**, não sobre performance individual.

> ❌ **NÃO use métricas para comparar times**
>
> Métricas são sobre o **processo de cada time em seu determinado contexto.**

> ✅ **Use métricas para melhorar o processo**
>
> "Por que Issues travam em X?" não "Por que você é lento?"

> ✅ **Aguarde 3-5 Sprints para tirar conclusões**
>
> Primeiras Sprints são aprendizado. Métricas estabilizam depois.
