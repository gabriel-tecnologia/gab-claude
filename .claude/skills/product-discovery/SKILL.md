---
name: product-discovery
description: Conducts discovery sessions for features/products. Explores concept definition, business model, user journeys, competitive analysis, scoping decisions, and data modeling. Use when you need to explore "what is X", "let's understand", "discovery for", or the /discovery command.
---

# Skill de Discovery

Conduzir sessões de discovery estruturadas para features e produtos. Esta skill ajuda PMs a explorar e documentar um espaço de problema antes de escrever PRDs ou criar user stories.

## Triggers

**Comando explícito:**

- `/discovery [nome-da-feature]`

**Padrões de auto-detecção:**

- "o que é [X]"
- "vamos explorar [X]"
- "discovery para [X]"
- "quero entender [X]"
- "vamos debater sobre [X]"

---

## Visão Geral do Workflow

O processo de discovery tem **7 fases flexíveis**. Todas as fases são opcionais - pergunte ao usuário quais aspectos ele quer explorar no início.

```
Fase 1: Definição de Conceito   → O que é?
Fase 2: Modelo de Negócio       → Quem gerencia, para quem, como monetiza?
Fase 3: Mapeamento de Jornada   → Como as personas interagem?
Fase 4: Análise Competitiva     → Como concorrentes resolvem isso? (OPCIONAL)
Fase 5: Decisões de Escopo      → O que entra no v1 vs depois?
Fase 6: Modelo de Dados         → Quais entidades e comportamentos? (OPCIONAL)
Fase 7: Documentação            → Compilar em documento de pesquisa
```

---

## Fase 1: Definição de Conceito

**Objetivo:** Estabelecer entendimento compartilhado do que é o conceito/feature.

**Abordagem:** Perguntas abertas primeiro, depois estruturar.

### Passos

```
1.1 Pergunta inicial aberta
    └── "O que você entende por [X]?"
    └── "Me conta mais sobre [X]"

1.2 Escuta ativa + síntese
    └── Reformular o que o usuário disse
    └── "Então [X] é [minha interpretação]. Está correto?"

1.3 Iterar até alinhamento
    └── Quantas perguntas forem necessárias
    └── Não prosseguir com dúvidas

1.4 Checkpoint de conceito
    └── Resumir definição acordada
    └── "Antes de seguir, confirmo: [X] é [definição final]"
```

### Exemplo 1: Hotlist (Segurança Pública)

```
Claude: "O que você sabe sobre hotlists no seu contexto?"
→ Propõe hipótese: "listas de vigilância de placas de veículos"
Usuário: "Vamos debater para enriquecer esse contexto"
→ Série de perguntas sobre tipos de entidade, propriedade, ações de match
→ Resultado: "Hotlist = listas de vigilância de placas de veículos que disparam
   alertas em tempo real quando detectadas por câmeras LPR"
```

### Exemplo 2: Tag de Urgência (Marketplace)

```
Claude: "O que você quer dizer com feature de 'tag de urgência'?"
Usuário: "Uma forma de vendedores marcarem itens que precisam vender rápido"
Claude: "Então compradores poderiam filtrar por urgência, e vendedores pagam premium
   por visibilidade. É sobre monetização do vendedor ou UX do comprador?"
Usuário: "Ambos - vendedores pagam, compradores encontram ofertas urgentes mais rápido"
→ Resultado: "Tag de urgência = feature paga para vendedores destacarem
   listagens sensíveis ao tempo, melhorando descoberta para compradores"
```

### Exemplo 3: Configurações de Customização (SaaS)

```
Usuário: "Usuários querem mais opções de customização"
Claude: "O que eles querem customizar especificamente?"
Usuário: "Layout do dashboard, preferências de notificação, integrações"
Claude: "Analytics mostra que 80% nunca mudam os padrões. O problema real
   é que os padrões não combinam com as necessidades do workflow deles?"
→ Resultado: "O problema não é falta de customização - é que os padrões
   não servem os principais casos de uso. Focar em padrões mais inteligentes,
   não mais opções."
```

---

## Fase 2: Modelo de Negócio

**Objetivo:** Entender quem gerencia, para quem, e impacto no negócio.

**Abordagem:** Perguntas emergem do contexto (não fixas). SEMPRE distinguir segmentos primários vs futuros.

### Passos

```
2.1 Propriedade
    └── "Quem cria/gerencia [X]?"
    └── Opções típicas: empresa, cliente, usuário final, híbrido

2.2 Segmentos (SEMPRE distinguir timing)
    └── "Quem é o cliente primário agora?"
    └── "Há potencial expansão para outros segmentos?"

2.3 Perguntas contextuais (exemplos)
    ├── Se envolve dados: "Quem é dono dos dados?"
    ├── Se envolve pagamento: "Como é monetizado?"
    ├── Se envolve terceiros: "Quem paga quem?"
    └── Se envolve compliance: "Quais regulamentações se aplicam?"

2.4 Checkpoint
    └── Resumir modelo em tabela: | Dimensão | Primário | Futuro |
```

### Exemplo 1: Hotlist (Segurança Pública)

```
| Dimensão     | Primário           | Futuro               |
|--------------|--------------------|----------------------|
| Propriedade  | Admin Gabriel      | Self-service B2B     |
| Segmento     | Polícia/GCM        | Estacionamento, Seg. |
| Monetização  | Incluído no produto| Nova fonte de receita|
```

### Exemplo 2: Features Premium de Vendedor (Marketplace)

```
| Dimensão     | Primário             | Futuro                  |
|--------------|----------------------|-------------------------|
| Propriedade  | Vendedor compra      | Pacotes de assinatura   |
| Segmento     | Power sellers        | Todos os vendedores     |
| Monetização  | Taxa por listagem    | Assinatura mensal       |
```

### Exemplo 3: Sistema de Notificações (SaaS)

```
| Dimensão     | Primário             | Futuro                   |
|--------------|----------------------|--------------------------|
| Propriedade  | Empresa define regras| Regras configuráveis     |
| Segmento     | Clientes enterprise  | SMB self-service         |
| Monetização  | Incluído no plano    | Add-on por uso           |
```

---

## Fase 3: Mapeamento de Jornada do Usuário

**Objetivo:** Mapear como personas interagem com a feature.

**Abordagem:** Focar em 2-3 personas, fluxo em texto simples.

### Passos

```
3.1 Identificar personas (focar em 2-3, permitir mais)
    └── "Quem são os principais usuários de [X]?"
    └── Sugerir opções baseadas no contexto
    └── Permitir usuário adicionar outras

3.2 Escolher estágio da jornada
    ├── Setup/Onboarding - configuração inicial
    ├── Uso principal - fluxo core
    └── Pós-ação - o que acontece depois

3.3 Mapear fluxo (texto simples)
    └── Passos numerados ou bullets
    └── Distinguir ações por persona se relevante

3.4 Permissões (se aplicável)
    └── "O que cada persona pode fazer?"
    └── Tabela: Persona | Pode criar? | Pode editar? | Pode deletar?

3.5 Checkpoint
    └── Validar fluxo com usuário antes de prosseguir
```

### Exemplo 1: Jornada de Setup de Hotlist

```
Personas: Operador de Polícia, Comandante de Polícia

Jornada de Setup:
1. Admin Gabriel cria tipos de hotlist para cliente
2. Admin Gabriel configura webhooks por tipo
3. Operador/Comandante visualiza hotlists disponíveis
4. Operador/Comandante adiciona placa + motivo
5. Sistema registra trilha de auditoria (quem adicionou)

Permissões:
| Persona    | Adicionar placa | Ver lista | Remover placa |
|------------|-----------------|-----------|---------------|
| Operador   | Sim             | Sim       | Sim           |
| Comandante | Sim             | Sim       | Sim           |
```

### Exemplo 2: Jornada de Otimização de Checkout

```
Personas: Comprador Convidado, Cliente Recorrente

Jornada de Compra:
1. Comprador adiciona itens ao carrinho
2. Comprador vai para checkout
3. Convidado: Insere info de entrega OU Recorrente: Usa endereço salvo
4. Convidado: Insere pagamento OU Recorrente: Usa pagamento salvo
5. Sistema calcula impostos/frete
6. Comprador revisa resumo do pedido
7. Comprador confirma compra
8. Sistema envia email de confirmação

Pontos de abandono a investigar:
- Passo 3: Abandono de convidado (fricção)
- Passo 6: Choque de preço (taxas inesperadas)
```

### Exemplo 3: Jornada de Gestão de Leads no CRM

```
Personas: Rep de Vendas, Gerente de Vendas

Processamento de Lead:
1. Marketing cria lead de submissão de formulário
2. Sistema auto-atribui para Rep baseado em território
3. Rep qualifica lead (critérios BANT)
4. Rep registra touchpoints na timeline
5. Gerente revisa pipeline no dashboard
6. Rep converte para oportunidade ou arquiva

Permissões:
| Persona   | Criar lead | Editar lead | Deletar lead | Ver relatórios |
|-----------|------------|-------------|--------------|----------------|
| Rep       | Não (auto) | Sim         | Não          | Só próprios    |
| Gerente   | Sim        | Sim         | Sim          | Time todo      |
```

---

## Fase 4: Análise Competitiva (OPCIONAL)

**Objetivo:** Entender como concorrentes resolvem o mesmo problema.

**Abordagem:** 2-3 principais concorrentes, tabela + destaques qualitativos.

### Passos

```
4.1 Perguntar se usuário quer incluir
    └── "Quer incluir análise competitiva?"
    └── Se não, pular para Fase 5

4.2 Identificar concorrentes (2-3 principais)
    └── "Você conhece concorrentes para analisar?"
    └── Se não: fazer web search para o domínio

4.3 Pesquisar cada concorrente
    └── WebSearch: "[concorrente] + [feature] + features"
    └── WebFetch: documentação se disponível
    └── G2/Capterra: tabelas de comparação de features

4.4 Criar tabela de comparação
    └── Features identificadas vs cada concorrente
    └── Coluna: Nossa decisão + justificativa

4.5 Destaques qualitativos
    └── Diferenciais de cada concorrente
    └── Gaps/oportunidades para nós

4.6 Salvar referências com links
    └── URLs das fontes pesquisadas
```

### Exemplo 1: Análise Competitiva de Hotlist

```
Concorrentes analisados: Flock Safety, Genetec AutoVu, Vigilant

| Feature       | Gabriel v1 | Flock           | Justificativa           |
|---------------|------------|-----------------|-------------------------|
| Metadados     | Mínimos    | Ricos (cor,tipo)| Clonagem invalida dados |
| Canal alerta  | Webhooks   | Mobile+RTCC     | Simplicidade v1         |
| TTL           | Por hotlist| Por placa       | Simples, extensível     |

Diferenciais Flock:
- Modo de turno (alertas apenas quando em serviço)
- Alertas por raio (baseado em distância)
- Fingerprinting de veículo além de placas
```

### Exemplo 2: Análise Competitiva de CRM

```
Concorrentes analisados: Salesforce, HubSpot, Pipedrive

| Feature          | Nosso CRM | Salesforce | HubSpot   | Justificativa         |
|------------------|-----------|------------|-----------|----------------------|
| Modelo de preço  | Por seat  | Por seat   | Freemium  | SMB precisa + simples|
| Customização     | Templates | Full custom| Limitado  | Balancear flexibil.  |
| App mobile       | Básico    | Completo   | Completo  | Prioridade para v2   |
| Features de IA   | Nenhuma   | Einstein   | Preditivo | Item de roadmap      |

Diferenciais HubSpot:
- Tier gratuito impulsiona adoção
- Integração seamless com marketing
- Melhor gestão de conteúdo

Diferenciais Salesforce:
- Customização enterprise-grade
- Ecossistema massivo de apps
- Clouds específicos por indústria
```

### Exemplo 3: Análise Competitiva de Gestão de Projetos

```
Concorrentes analisados: Asana, Monday.com, Notion

| Feature       | Nossa Tool | Asana      | Monday     | Notion     |
|---------------|------------|------------|------------|------------|
| Views         | Só lista   | Lista,Board| 8+ views   | Flexível   |
| Automações    | Básico     | Avançado   | Extensivo  | Limitado   |
| Docs          | Separado   | Mínimo     | Mínimo     | Nativo     |
| Preço         | Simples    | Em tiers   | Por seat   | Generoso   |

Insight chave:
- Monday ganha em apelo visual e templates
- Asana ganha em automação de workflow
- Notion ganha em flexibilidade mas perde em estrutura
- Nossa oportunidade: Simplicidade opinativa para times pequenos
```

---

## Fase 5: Decisões de Escopo

**Objetivo:** Definir o que entra no v1 e o que vem depois.

**Abordagem:** Listar features da competição + jornada, decidir cada uma.

### Passos

```
5.1 Compilar lista de features
    └── Extrair da análise competitiva (se feita)
    └── Derivar da jornada do usuário
    └── Consolidar em lista única

5.2 Perguntar nível de análise
    └── "Quer analisar linha a linha ou decisão geral?"
    └── Se linha a linha: discutir cada feature individualmente
    └── Se geral: resumir decisões em tabela

5.3 Para cada feature (se linha a linha)
    └── "Por que [decisão]? Qual a justificativa?"
    └── Capturar raciocínio do usuário
    └── Documentar trade-off

5.4 Documentar em tabela
    └── | # | Feature | Decisão v1 | Justificativa |
    └── Adicionar coluna "Futuro" se relevante

5.5 Checkpoint
    └── Validar tabela completa antes de prosseguir
```

### Exemplo 1: Escopo de Features de Hotlist

```
| # | Feature          | Gabriel v1       | Concorrente   | Justificativa          |
|---|------------------|------------------|---------------|------------------------|
| 1 | Criação hotlist  | Só admin         | Self-service  | API core flexível      |
| 2 | Metadados placa  | Mínimos          | Ricos         | Clonagem invalida      |
| 3 | Canal alerta     | Só webhooks      | Multi-canal   | Simplicidade v1        |
| 4 | Import em lote   | Só API           | CSV + API     | CSV no roadmap         |
| 5 | Compartilhar org | Não no v1        | Federação     | Baixa demanda + LGPD   |
```

### Exemplo 2: Escopo de Sistema de Notificações

```
| # | Feature          | Decisão v1        | Justificativa                    |
|---|------------------|-------------------|----------------------------------|
| 1 | Canais entrega   | Só email          | Menor fricção para começar       |
| 2 | Controle freq.   | Digest diário     | Prevenir fadiga de notificação   |
| 3 | Triggers custom  | Só pré-definidos  | Regras de usuário adicionam compl|
| 4 | UI preferências  | Toggles simples   | Prefs avançadas v2               |
| 5 | Analytics        | Taxas de abertura | Analytics profundo precisa dados |

Roadmap futuro:
- Push notifications (mobile)
- Integração Slack/Teams
- Regras de trigger definidas pelo usuário
- Teste A/B para copy de notificação
```

### Exemplo 3: Escopo de Otimização de Checkout

```
| # | Feature           | Decisão v1       | Impacto  | Justificativa          |
|---|-------------------|------------------|----------|------------------------|
| 1 | Checkout guest    | Sim              | +30% CR  | Reduz fricção          |
| 2 | Pagamento salvo   | Sim              | +15% CR  | Velocidade usuário rec.|
| 3 | Indicador progr.  | Sim              | +5% CR   | Reduz incerteza        |
| 4 | Compre agora pague| Não no v1        | Desconh. | Precisa parceiro vendor|
| 5 | Login social      | Não no v1        | +10% CR  | Preocupações privacidade|
| 6 | Autocomplete end. | Sim              | +8% CR   | API Google disponível  |

Decisão: Focar em #1, #2, #3, #6 para v1 (melhoria esperada de +58% CR)
```

---

## Fase 6: Modelo de Dados (OPCIONAL)

**Objetivo:** Definir entidades, atributos e comportamentos.

**Abordagem:** Perspectiva de PM (não técnica), perguntar sobre cada comportamento.

### Passos

```
6.1 Perguntar se usuário quer definir modelo
    └── "Quer definir o modelo de dados agora?"
    └── Se não, pular para Fase 7

6.2 Identificar entidades principais
    └── "Quais são os principais 'objetos' de [X]?"
    └── Derivar da jornada e features

6.3 Para cada entidade
    ├── Atributos (linguagem de PM)
    │   └── "O que precisa ser armazenado sobre [entidade]?"
    │   └── Evitar jargão: "campo de texto" não "string"
    ├── Comportamentos (perguntar cada um)
    │   └── "Pode criar? Pode editar? Pode deletar?"
    │   └── "O que acontece quando [ação]?"
    │   └── "Há regras especiais?" (TTL, validações)
    └── Relacionamentos
        └── "Como [A] se relaciona com [B]?"
        └── Linguagem simples: "pertence a", "tem muitos"

6.4 Checkpoint
    └── Resumir modelo em formato visual simples
```

### Exemplo 1: Modelo de Dados de Hotlist (linguagem de PM)

```
HOTLIST:
- Nome, descrição, status ativo/inativo
- Regra de expiração para placas (TTL)
- Lista de webhooks para alertas
- Organização proprietária
- Pode criar, editar todos os campos, deletar
- Deletar apenas se não houver placas

ENTRADA DE PLACA:
- Placa (normalizada maiúscula), motivo
- Fonte: manual, API, ou import
- Expira automaticamente pela regra da hotlist
- Pode criar e deletar, NÃO PODE editar (deletar + re-adicionar)
- Mesma placa pode estar em múltiplas hotlists

LOG DE AUDITORIA:
- Registro de quem adicionou/removeu cada placa
- Mantido mesmo após remoção da placa
- Somente leitura (não pode alterar histórico)
```

### Exemplo 2: Modelo de Dados de Notificação (linguagem de PM)

```
TEMPLATE DE NOTIFICAÇÃO:
- Nome, linha de assunto, conteúdo do corpo
- Evento trigger (o que causa)
- Status ativo/inativo
- Pode criar, editar, deletar

LOG DE NOTIFICAÇÃO:
- Qual usuário, qual template, quando enviado
- Status de entrega (enviado, entregue, aberto, clicado)
- Somente leitura após criação
- Retido por 90 dias

PREFERÊNCIAS DO USUÁRIO:
- Quais tipos de notificação habilitados
- Frequência preferida (imediata, diária, semanal)
- Pode editar, não pode deletar (apenas desabilitar)
```

### Exemplo 3: Modelo de Dados de Lead (linguagem de PM)

```
LEAD:
- Info de contato (nome, email, empresa)
- Fonte (formulário, indicação, import)
- Status (novo, contatado, qualificado, convertido, arquivado)
- Rep de vendas atribuído
- Pode criar, editar status/atribuição, apenas soft-delete

TOUCHPOINT:
- Tipo (email, ligação, reunião, nota)
- Resumo, timestamp
- Lead associado
- Pode criar, não pode editar ou deletar (trilha de auditoria)

SCORE DO LEAD:
- Valor calculado baseado em engajamento
- Auto-atualizado pelo sistema
- Somente leitura para usuários
```

---

## Fase 7: Documentação

**Objetivo:** Compilar tudo em documento de pesquisa.

**Abordagem:** Preview antes de salvar, documento salva na pasta de pesquisa do squad.

### Passos

```
7.1 Compilar documento
    └── Estrutura padrão baseada nas fases completadas
    └── Incluir apenas seções que foram exploradas

7.2 Mostrar preview para usuário
    └── Exibir documento formatado
    └── Perguntar: "Algo para ajustar antes de salvar?"

7.3 Salvar documento
    └── Local: {squad}/{produto}/research/research-{feature}.md
    └── Confirmar salvamento com caminho completo

7.4 Finalizar
    └── "Discovery completo. Documento salvo em [caminho]."
```

### Estrutura do Documento

```markdown
# [Feature] - Pesquisa & Discovery

**Autor:** [usuário]
**Data:** [hoje]
**Status:** Discovery completo

## 1. Contexto

(da Fase 1 + 2)

## 2. Decisões de Produto

(da Fase 5 - tabela)

## 3. Jornadas do Usuário

(da Fase 3)

## 4. Modelo de Dados

(da Fase 6, se feito)

## 5. Análise Competitiva

(da Fase 4, se feito)

## 6. Próximos Passos

- [ ] Checklist de ações identificadas
```

---

## Integrações

**Slack:** Buscar discussões existentes sobre o tópico antes de iniciar
**Web Search:** Para análise competitiva na Fase 4
**Linear:** Verificar se projeto/issues relacionados já existem

---

## Dicas para PMs

### Antes de Iniciar Discovery

1. **Reunir contexto existente** - Verificar Slack, docs, discussões anteriores
2. **Conhecer seus stakeholders** - Quem precisa estar envolvido?
3. **Definir expectativas de tempo** - Discovery completo pode levar 30-60 min

### Durante o Discovery

1. **Seja paciente com iteração** - Boas definições levam múltiplas passagens
2. **Desafie suposições** - "Por que achamos que usuários precisam disso?"
3. **Documente trade-offs** - Você do futuro agradecerá ao você do presente
4. **Pense em segmentos** - Primário vs futuro ajuda a priorizar

### Após o Discovery

1. **Compartilhe o documento** - Alinhamento requer visibilidade
2. **Revisite conforme aprende** - Discovery não é evento único
3. **Use para PRD** - Doc de pesquisa é input do PRD

---

## Referências

### Frameworks de Product Discovery

- [Teresa Torres' Opportunity Solution Tree](https://www.producttalk.org/)
- [Dual-Track Development](https://www.productboard.com/blog/step-by-step-framework-for-better-product-discovery/)
- [7 Product Discovery Examples - Zeda.io](https://zeda.io/blog/product-discovery-examples)

### Melhores Práticas de Análise Competitiva

- [B2B SaaS Competitive Analysis Guide](https://rampiq.agency/blog/saas-competitive-analysis/)
- [Competitor Research Template - Kalungi](https://www.kalungi.com/blog/b2b-saas-competitor-research)

### Estatísticas

- Microsoft: 70% das features raramente ou nunca são usadas
- Subito.it Premium Features: +3% CR, +5% receita de abordagem guiada por discovery
