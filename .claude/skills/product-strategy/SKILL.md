---
name: product-strategy
description: Criar Product Strategies seguindo a fórmula Product School. Use quando usuários pedirem "product strategy", "estratégia de produto", "strategy document", ou precisarem definir visão e direção estratégica de um produto.
---

# Gerador de Product Strategy

## Visão Geral

Guiar usuários na criação de Product Strategies completas seguindo a fórmula Product School:

```
Product Strategy = Vision + Insights + Challenges + Approaches + Accountability
```

Esta skill ajuda product managers a criar documentos estratégicos que alinham stakeholders, definem direção clara e estabelecem métricas de accountability.

## Workflow Principal

Quando um usuário solicitar criar uma Product Strategy (ex: "crie uma product strategy para o App Gabriel"), siga este workflow de 5 fases.

### Fase 1: Product Vision (ESSENCE)

**Objetivo:** Definir a essência do produto - o que, para quem, e por que agora.

**Perguntas de Discovery:**

```
1. Qual problema você está resolvendo? (WHAT)
2. Para quem você está resolvendo? (WHO)
3. Por que agora é o momento certo? (WHY)
```

**Gerar Vision Statement usando o formato:**

| Campo           | Descrição                                                         |
| --------------- | ----------------------------------------------------------------- |
| **For**         | (Cliente alvo)                                                    |
| **Who**         | (Necessidade ou oportunidade) - Qual problema estamos resolvendo? |
| **The**         | (Nome do produto) é um (categoria de produto)                     |
| **That**        | (Benefício chave, razão para comprar)                             |
| **Unlike**      | (Alternativa competitiva principal)                               |
| **Our Product** | (Declaração de diferenciação primária)                            |

**Características da Vision:**

- Conecta com a visão da empresa
- Aspiracional, meta de longo prazo
- Relativamente estável, pivota menos que a estratégia

### Fase 2: Product Insights (LOGIC)

**Objetivo:** Coletar dados e lógica que fundamentam a estratégia.

**Componentes:**

**1. Competitors (Análise Competitiva)**

- Usar WebSearch para pesquisar concorrentes
- Documentar diferenciadores e similaridades
- Incluir dados quantitativos quando disponíveis

**2. Market Insight (TAM, audiência, oportunidade)**

- Definir audience e target market
- Identificar oportunidades de mercado
- Estimar tamanho do mercado se possível

**3. Market Trends**

- Identificar tendências relevantes
- Usar WebSearch para dados atualizados
- Conectar tendências com timing do produto

**4. Customer Insights (Personas)**

- Definir 2-3 personas principais
- Incluir comportamentos, necessidades, pain points
- Buscar no Slack discussões sobre feedback de usuários

**Estratégia de Pesquisa:**

```
1. Buscar no Slack por discussões sobre o produto/problema
2. Usar WebSearch para análise competitiva
3. Verificar Linear por projetos/issues relacionados
4. Consolidar insights de todas as fontes
```

### Fase 3: Challenges (ROADBLOCKS)

**Objetivo:** Identificar obstáculos e riscos antecipados.

**Categorias de Desafios:**

| Categoria                | Pergunta Guia                                                                      |
| ------------------------ | ---------------------------------------------------------------------------------- |
| **Technical**            | Quais hurdles técnicos antecipamos?                                                |
| **Customer Pain Points** | Quais problemas do cliente enfrentaremos? Incluir desafios emocionais/psicológicos |
| **GTM Risks**            | Quais riscos de go-to-market existem? Por que agora?                               |
| **Legal**                | Quais requisitos regulatórios precisamos mitigar?                                  |

**Dicas:**

- Ser realista mas não pessimista
- Conectar desafios com mitigações na próxima fase
- Considerar desafios internos (equipe, recursos) e externos (mercado, regulação)

### Fase 4: Approaches (PATHS)

**Objetivo:** Definir o caminho estratégico para alcançar a visão.

**Componentes:**

**1. Approach (Estratégia escolhida)**

- Single approach ou multi-prong approach
- Pode variar para diferentes segmentos de clientes
- Justificar a escolha da abordagem

**2. Overcome Challenges**

- Plano de alto nível para superar cada desafio da Fase 3
- Ser específico mas não excessivamente detalhado
- Priorizar desafios críticos

**3. Do's & Don'ts (Guardrails)**

- O que FAREMOS ao longo do caminho
- O que NÃO FAREMOS ao longo do caminho
- Manter foco e evitar scope creep

**Exemplo de Estrutura:**

```markdown
**Approach:** Multi-prong approach focado em:

1. [Abordagem 1]
2. [Abordagem 2]
3. [Abordagem 3]

**Overcome Challenges:**

- Technical: [plano de mitigação]
- Customer: [plano de mitigação]
- GTM: [plano de mitigação]

**Do's:**

- [Ação permitida 1]
- [Ação permitida 2]

**Don'ts:**

- [Ação proibida 1]
- [Ação proibida 2]
```

### Fase 5: Accountability (MEASURE)

**Objetivo:** Definir como medir sucesso e manter accountability.

**Componentes:**

**1. North Star Metric**

- Métrica estratégica e visionária única
- Representa o valor core entregue ao cliente
- Alinhada com a vision

**2. Supporting Metrics**

- Métricas perceptuais: engagement, satisfaction, happiness
- Métricas de valor: sales, leads, ROI
- Mix de leading e lagging indicators

**3. Targets (Metas Específicas)**

- Baseline atual
- Meta de curto prazo (3-6 meses)
- Meta de longo prazo (12+ meses)

**4. Progress Tracking**

- Como e quando revisar progresso
- Quem é responsável pelo tracking
- Rituais de review

**Framework de Métricas Sugerido:**

| Tipo           | Exemplos                    |
| -------------- | --------------------------- |
| **North Star** | MAU, Revenue, NPS           |
| **Perceptual** | CSAT, Feature adoption rate |
| **Value**      | Conversion rate, LTV, Churn |

## Modos Suportados

### Modo Completo (~5 páginas)

**Quando usar:** Novos produtos, pivots significativos, estratégias anuais

**Output:** Documento markdown completo com todas as 5 fases detalhadas

**Comando:** "product strategy" ou "criar product strategy completa"

### Modo Rápido / One-Pager (~1 página)

**Quando usar:** Iteração inicial, alinhamento rápido, features específicas

**Output:** One-pager resumido com pontos essenciais de cada fase

**Comando:** "product strategy rápida", "one-pager strategy", "strategy resumida"

## Output e Salvamento

### Estrutura do Documento Final

```markdown
# Product Strategy: [Nome do Produto]

**Status:** [Draft | In Review | Approved]
**Autor:** [Nome]
**Data:** [YYYY-MM-DD]
**Versão:** [1.0]

---

## 1. Product Vision

[Conteúdo da Fase 1]

## 2. Product Insights

[Conteúdo da Fase 2]

## 3. Challenges

[Conteúdo da Fase 3]

## 4. Approaches

[Conteúdo da Fase 4]

## 5. Accountability

[Conteúdo da Fase 5]

---

## Sign-off

| Stakeholder | Cargo               | Aprovação | Data |
| ----------- | ------------------- | --------- | ---- |
| [Nome]      | CPTO                | ☐         | -    |
| [Nome]      | Engineering Manager | ☐         | -    |
| [Nome]      | GPM                 | ☐         | -    |
```

### Local de Salvamento

Salvar em: `products/{produto}/strategy.md`

Se o produto não existir, criar a estrutura:

```
products/
└── {produto}/
    └── strategy.md
```

## Integrações

### Slack

Buscar discussões existentes sobre:

- Nome do produto/feature
- Problemas relacionados
- Feedback de usuários
- Decisões já tomadas

### Linear

Verificar:

- Projetos relacionados ao produto
- Issues que informam a estratégia
- Roadmap existente

### WebSearch

Usar para:

- Análise competitiva
- Tendências de mercado
- Dados de mercado (TAM, growth rates)
- Benchmarks da indústria

## Padrões de Uso

### Padrão 1: Nova Product Strategy

**Solicitação:** "Crie uma product strategy para o App Gabriel"

**Execução:**

1. Perguntar sobre What/Who/Why
2. Buscar contexto no Slack e Linear
3. Pesquisar concorrentes via WebSearch
4. Guiar pelas 5 fases sequencialmente
5. Gerar documento completo
6. Salvar em products/app-gabriel/strategy.md

### Padrão 2: Atualização de Strategy

**Solicitação:** "Atualize a strategy do produto X com novos insights"

**Execução:**

1. Ler strategy existente
2. Identificar seções a atualizar
3. Coletar novos insights
4. Mesclar com conteúdo existente
5. Manter histórico de versões

### Padrão 3: Strategy One-Pager

**Solicitação:** "Crie um one-pager da strategy para apresentação"

**Execução:**

1. Usar template one-pager em references/strategy_onepager.md
2. Resumir cada fase em 2-3 bullets
3. Focar em vision statement e métricas principais
4. Incluir visual da fórmula

## Melhores Práticas

### Escrevendo Product Strategy

**FAÇA:**

- Pense profundamente antes de escrever
- Colabore com stakeholders 1:1 durante criação
- Compartilhe rascunhos cedo e frequentemente
- Referencie a strategy em discussões e decisões
- Atualize conforme aprendizados surgem

**NÃO FAÇA:**

- Espere ter todas as respostas para começar
- Trabalhe isoladamente
- Trate como documento estático
- Ignore quando stakeholders perdem confiança
- Continue com strategy falha por sunk cost

### Quando Pivotar a Strategy

Sinais de que precisa revisar:

- Necessidades/comportamentos dos clientes mudaram
- Novos competidores alteraram expectativas
- Desafios inesperados surgiram
- Novos insights são mais importantes que os anteriores
- Métricas não demonstram progresso

## Recursos

### references/

- **strategy_template.md** - Template completo para product strategy
- **strategy_onepager.md** - Template resumido one-pager

## Exemplos

### Exemplo 1: Strategy de Produto Existente

```
Usuário: "Crie uma product strategy para melhorar o checkout do e-commerce"

Assistente:
1. Discovery sobre problemas atuais e metas
2. Busca no Slack por discussões sobre checkout
3. Pesquisa de benchmarks de conversão via WebSearch
4. Guia pelas 5 fases:
   - Vision: Para compradores que abandonam carrinho...
   - Insights: Taxa de conversão atual 2.3%, benchmark 3.5%...
   - Challenges: Fricção no pagamento, confiança, velocidade...
   - Approaches: Guest checkout, salvar pagamento, progress indicator...
   - Accountability: North Star = Conversion rate, meta 3.5%
5. Gera documento e salva em products/ecommerce/strategy.md
```

### Exemplo 2: Strategy One-Pager

```
Usuário: "Preciso de um one-pager da strategy de notificações"

Assistente:
1. Coleta informações essenciais de cada fase
2. Usa template one-pager
3. Gera documento de ~1 página com:
   - Vision statement em 2 linhas
   - 3 key insights
   - Top 3 challenges
   - Approach principal
   - North Star + 2 métricas secundárias
```

## Validação

Antes de finalizar, verificar:

- [ ] Vision statement está claro e inspirador
- [ ] Insights são baseados em dados/pesquisa
- [ ] Challenges são realistas e endereçados
- [ ] Approaches conectam challenges com vision
- [ ] Métricas são mensuráveis e têm targets
- [ ] Stakeholders relevantes estão na lista de sign-off
- [ ] Documento está salvo no local correto

## Troubleshooting

**Problema: Usuário não sabe responder What/Who/Why**

Solução: Fazer perguntas mais específicas, sugerir exemplos, buscar contexto existente no Slack/Linear.

**Problema: Muitos desafios identificados**

Solução: Priorizar top 3-5 desafios críticos, mover outros para "monitorar".

**Problema: Métricas difíceis de definir**

Solução: Começar com métricas aproximadas, refinar após primeira iteração, usar proxies quando necessário.

**Problema: Stakeholders não alinhados**

Solução: Compartilhar rascunho cedo, incorporar feedback, agendar sessão de alinhamento antes de finalizar.
