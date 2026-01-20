---
name: product-prd
description: Generate comprehensive Product Requirements Documents (PRDs) for product managers. Use this skill when users ask to "create a PRD", "write product requirements", "document a feature", or need help structuring product specifications.
---

# Gerador de PRD

## Visão Geral

Gerar Product Requirements Documents (PRDs) abrangentes e bem estruturados que seguem as melhores práticas da indústria. Esta skill ajuda product managers a criar documentos de requisitos claros e acionáveis que alinham stakeholders e guiam times de desenvolvimento.

## Workflow Principal

Quando um usuário solicitar criar um PRD (ex: "crie um PRD para uma feature de autenticação de usuário"), siga este workflow:

### Passo 1: Coletar Contexto

Antes de gerar o PRD, colete informações essenciais através de uma conversa de discovery:

**Informações Necessárias:**

- **Nome da Feature/Produto**: O que estamos construindo?
- **Declaração do Problema**: Qual problema isso resolve?
- **Usuários Alvo**: Para quem é isso?
- **Objetivos de Negócio**: O que estamos tentando alcançar?
- **Métricas de Sucesso**: Como mediremos sucesso?
- **Timeline/Restrições**: Algum prazo ou limitação?

**Perguntas de Discovery a Fazer:**

```
1. Qual problema você está tentando resolver?
2. Quem é o usuário/público primário para esta feature?
3. Quais são os principais objetivos de negócio?
4. Há restrições técnicas que devemos conhecer?
5. Como é o sucesso? Como você vai medir?
6. Qual é o timeline para esta feature?
7. O que está explicitamente fora do escopo?
```

**Nota:** Se o usuário fornecer um brief detalhado ou requisitos de antemão, você pode pular algumas perguntas. Sempre peça esclarecimento sobre informações críticas faltantes.

### Passo 2: Coletar Contexto do Slack

Use a integração MCP do Slack para buscar discussões relevantes sobre a feature ou problema em todos os canais acessíveis. Isso enriquece o PRD com conhecimento e decisões existentes do time.

**Estratégia de Busca:**

1. **Buscar por nome da feature/produto**: Encontrar discussões mencionando a feature
2. **Buscar por palavras-chave do problema**: Identificar conversas sobre os pain points
3. **Buscar por termos relacionados**: Ampliar contexto com tópicos relacionados

**O que Procurar:**

- Discussões anteriores sobre a feature ou problema
- Decisões já tomadas pelo time
- Considerações técnicas mencionadas por engenheiros
- Feedback de usuários compartilhado nos canais
- Preocupações ou requisitos de stakeholders
- Links/documentos relevantes compartilhados

**Workflow de Busca no Slack:**

```
1. Usar nome da feature e palavras-chave do Passo 1 para buscar em todos os canais acessíveis
2. Buscar por palavras-chave relacionadas ao problema
3. Procurar mensagens recentes (últimos 30-90 dias) por relevância
4. Identificar participantes-chave nas discussões
5. Extrair insights e linkar para mensagens originais quando relevante
```

**Integração com PRD:**

- Incluir citações ou referências relevantes no PRD
- Notar decisões já tomadas
- Sinalizar opiniões conflitantes para resolução
- Referenciar stakeholders-chave identificados nas discussões

**Nota:** Se nenhuma discussão relevante no Slack for encontrada, ou se acesso ao Slack não estiver disponível, prossiga diretamente para o Passo 3. Este passo enriquece contexto mas não é obrigatório.

### Passo 3: Gerar Estrutura do PRD

Use o template padrão de PRD em `references/prd_template.md` para criar um documento bem estruturado. O PRD deve incluir:

1. **Resumo Executivo** - Visão geral de alto nível (2-3 parágrafos)
2. **Declaração do Problema** - Articulação clara do problema
3. **Objetivos & Metas** - O que estamos tentando alcançar
4. **Personas de Usuário** - Para quem estamos construindo
5. **User Stories & Requisitos** - Requisitos funcionais detalhados
6. **Métricas de Sucesso** - KPIs e critérios de medição
7. **Escopo** - O que está dentro e fora do escopo
8. **Considerações Técnicas** - Arquitetura, dependências, restrições
9. **Requisitos de Design & UX** - Considerações de UI/UX
10. **Timeline & Milestones** - Datas-chave e fases
11. **Riscos & Mitigação** - Problemas potenciais e soluções
12. **Dependências & Premissas** - No que estamos confiando
13. **Perguntas em Aberto** - Itens não resolvidos

### Passo 4: Criar User Stories

Para cada requisito principal, gere uma user story ou user stories usando o formato padrão que você pode encontrar em `references/user_story_examples.md` para padrões comuns e melhores práticas.
Para cada story, revise se você tem os seguintes detalhes seguindo as melhores práticas abaixo.

**FAÇA:**

- Peça detalhes sobre a user story
- Valide se você tem contexto suficiente para criar cada uma com critérios de aceite bem escritos
- Peça ao usuário para verificar cada uma antes de definir a escrita da story como finalizada

### Passo 5: Definir Métricas de Sucesso

Use frameworks de métricas apropriados baseados no tipo de produto:

- **AARRR (Pirate Metrics)**: Acquisition, Activation, Retention, Revenue, Referral
- **HEART Framework**: Happiness, Engagement, Adoption, Retention, Task Success
- **North Star Metric**: Métrica-chave única que representa valor core
- **OKRs**: Objectives and Key Results

Consulte `references/metrics_frameworks.md` para orientação detalhada sobre cada framework.

### Passo 6: Validar & Revisar

Opcionalmente rode o script de validação para garantir completude do PRD:

```bash
scripts/validate_prd.sh <arquivo_prd.md>
```

Isso verifica:

- Todas as seções requeridas presentes
- User stories seguem formato adequado
- Métricas de sucesso estão definidas
- Escopo está claramente articulado
- Nenhum texto placeholder permanece

## Padrões de Uso

### Padrão 1: PRD de Nova Feature

**Solicitação do Usuário:** "Crie um PRD para adicionar dark mode ao nosso app mobile"

**Execução:**

1. Fazer perguntas de discovery sobre requisitos de dark mode
2. Buscar no Slack discussões existentes sobre dark mode ou theming
3. Gerar PRD usando template
4. Criar user stories para:
   - Troca de tema
   - Persistência de preferência
   - Sincronização com nível de sistema
   - Atualizações de design tokens
5. Definir métricas de sucesso (taxa de adoção, satisfação do usuário)
6. Identificar dependências técnicas (design system, APIs de plataforma)

### Padrão 2: PRD de Melhoria de Produto

**Solicitação do Usuário:** "Escreva requisitos para melhorar nossa funcionalidade de busca"

**Execução:**

1. Coletar contexto sobre limitações atuais da busca
2. Identificar pain points do usuário e melhorias desejadas
3. Buscar no Slack discussões sobre problemas de busca e feedback
4. Gerar PRD com foco em:
   - Análise do estado atual
   - Melhorias propostas
   - Avaliação de impacto
5. Criar user stories priorizadas
6. Definir métricas antes/depois

### Padrão 3: PRD de Novo Produto

**Solicitação do Usuário:** "Preciso de um PRD para um novo produto de dashboard de analytics"

**Execução:**

1. Discovery abrangente (análise de mercado, pesquisa de usuário)
2. Buscar no Slack discussões sobre necessidades de analytics e requisitos de dashboard
3. Gerar PRD completo com:
   - Oportunidade de mercado
   - Análise competitiva
   - Visão do produto
   - Escopo de MVP
   - Considerações de go-to-market
4. User stories detalhadas para features core
5. Plano de rollout em fases
6. Métricas de sucesso alinhadas com objetivos de negócio

### Padrão 4: PRD Rápido / One-Pager

**Solicitação do Usuário:** "Crie um PRD leve para uma feature de correção de bug pequena"

**Execução:**

1. Gerar PRD simplificado focando em:
   - Declaração do problema
   - Abordagem da solução
   - Critérios de aceite
   - Métricas de sucesso
2. Opcionalmente buscar no Slack por reports de bugs ou discussões relacionadas
3. Pular seções não relevantes para escopo pequeno
4. Manter documento conciso (1-2 páginas)

## Melhores Práticas de PRD

### Escrevendo Requisitos de Qualidade

**Bons Requisitos São:**

- **Específicos**: Claros e não ambíguos
- **Mensuráveis**: Podem ser verificados/testados
- **Alcançáveis**: Tecnicamente viáveis
- **Relevantes**: Ligados a valor de usuário/negócio
- **Temporais**: Têm timeline claro

**Evite:**

- Linguagem vaga ("rápido", "fácil", "intuitivo")
- Detalhes de implementação (deixe engenheiros decidir como)
- Escopo creep (mantenha requisitos core)
- Suposições sem validação

### Melhores Práticas de User Story

**FAÇA:**

- Foque em valor para o usuário, não features
- Escreva da perspectiva do usuário
- Inclua critérios de aceite claros
- Mantenha stories independentes e pequenas
- Use formato consistente

**NÃO FAÇA:**

- Escreva detalhes de implementação técnica
- Crie dependências entre stories
- Faça stories muito grandes (epics)
- Use jargão interno
- Pule critérios de aceite

### Gestão de Escopo

**Seção In-Scope:**

- Liste features/capacidades específicas incluídas
- Seja explícito e detalhado
- Linke para user stories

**Seção Out-of-Scope:**

- Declare explicitamente o que NÃO está incluído
- Previne scope creep
- Gerencia expectativas de stakeholders
- Pode incluir "considerações futuras"

### Diretrizes de Métricas de Sucesso

**Escolha Métricas Que:**

- Alinham com objetivos de negócio
- São mensuráveis e rastreáveis
- Têm targets/thresholds claros
- Incluem indicadores leading e lagging
- Consideram valor de usuário e negócio

**Categorias Típicas de Métricas:**

- **Adoção**: Quantos usuários usam a feature?
- **Engajamento**: Com que frequência eles usam?
- **Satisfação**: Usuários gostam?
- **Performance**: Funciona bem?
- **Impacto de Negócio**: Impulsiona objetivos de negócio?

## Features Avançadas

### Templates de PRD para Diferentes Contextos

A skill suporta diferentes formatos de PRD:

**PRD Padrão** - Documento abrangente completo
**PRD Lean** - Simplificado para times ágeis
**One-Pager** - Formato de resumo executivo
**PRD Técnico** - Requisitos focados em engenharia
**PRD de Design** - Requisitos focados em UX/UI

Especifique o formato ao solicitar: "Crie um PRD lean para..." ou "Gere um PRD técnico para..."

### Integração com Design

**Seção de Requisitos de Design Deve Incluir:**

- Requisitos de design visual
- Padrões de interação
- Requisitos de acessibilidade (conformidade WCAG)
- Considerações de design responsivo
- Componentes do design system a usar
- Diagramas de user flow
- Referências de wireframe/mockup

### Seção de Considerações Técnicas

**Deve Abordar:**

- **Arquitetura**: Abordagem técnica de alto nível
- **Dependências**: Serviços externos, bibliotecas, APIs
- **Segurança**: Autenticação, autorização, proteção de dados
- **Performance**: Tempos de carga, requisitos de escalabilidade
- **Compatibilidade**: Suporte de browser, dispositivo, plataforma
- **Dados**: Armazenamento, migração, considerações de privacidade
- **Integração**: Como se encaixa com sistemas existentes

### Alinhamento de Stakeholders

**PRD Deve Ajudar a:**

- Alinhar times cross-funcionais
- Definir expectativas claras
- Habilitar work streams paralelos
- Facilitar tomada de decisão
- Fornecer single source of truth

**Checklist de Distribuição:**

- [ ] Engenharia revisou viabilidade técnica
- [ ] Design revisou requisitos de UX
- [ ] Liderança de produto aprovou escopo
- [ ] Stakeholders entendem timeline
- [ ] Métricas de sucesso acordadas

## Cenários Comuns de PRD

### Cenário 1: Feature Request de Cliente

Ao criar um PRD baseado em feedback de cliente:

1. Documente o request do cliente verbatim
2. Analise o problema subjacente
3. Generalize a solução para todos os usuários
4. Valide com estratégia de produto
5. Escopeie apropriadamente (pode ser menor ou maior que o request)

### Cenário 2: Iniciativa Estratégica

Ao criar um PRD para uma iniciativa estratégica da empresa:

1. Linke com OKRs/objetivos da empresa
2. Inclua análise de mercado
3. Considere landscape competitivo
4. Pense em rollout multi-fase
5. Inclua critérios de sucesso alinhados com estratégia

### Cenário 3: Technical Debt / Infraestrutura

Ao criar um PRD para melhorias técnicas:

1. Explique impacto no usuário (mesmo se indireto)
2. Documente limitações atuais
3. Articule benefícios (velocidade, confiabilidade, manutenibilidade)
4. Inclua input de engenharia pesadamente
5. Defina melhorias mensuráveis

### Cenário 4: Compliance / Regulatório

Ao criar um PRD para requisitos de compliance:

1. Referencie regulamentações específicas (LGPD, GDPR, etc.)
2. Inclua revisão legal/compliance
3. Deadline geralmente não é negociável
4. Foque em compliance mínimo viável
5. Documente requisitos de trilha de auditoria

## Validação & Verificações de Qualidade

### Checklist de Auto-Revisão

Antes de finalizar o PRD, verifique:

- [ ] **Problema está claro**: Qualquer um pode entender o que estamos resolvendo
- [ ] **Usuários estão identificados**: Sabemos para quem é isso
- [ ] **Sucesso é mensurável**: Podemos determinar se funcionou
- [ ] **Escopo está limitado**: Claro o que está dentro e fora
- [ ] **Requisitos são testáveis**: QA pode verificar completude
- [ ] **Timeline é realista**: Estimativas validadas com engenharia
- [ ] **Riscos estão identificados**: Pensamos no que pode dar errado
- [ ] **Stakeholders alinhados**: Pessoas-chave revisaram e aprovaram

### Usando o Script de Validação

```bash
# Validação básica
scripts/validate_prd.sh meu_prd.md

# Output detalhado com sugestões
scripts/validate_prd.sh meu_prd.md --verbose

# Verificar apenas seções específicas
scripts/validate_prd.sh meu_prd.md --sections "user-stories,metrics"
```

## Recursos

Esta skill inclui recursos empacotados:

### scripts/

- **generate_prd.sh** - Workflow interativo de geração de PRD
- **validate_prd.sh** - Valida completude e qualidade do PRD

### references/

- **prd_template.md** - Estrutura de template de PRD padrão
- **user_story_examples.md** - Padrões e exemplos de user story
- **metrics_frameworks.md** - Guia de métricas de PM (AARRR, HEART, OKRs)

## Dicas para Product Managers

### Antes de Escrever o PRD

1. **Faça sua pesquisa**: Entrevistas com usuários, análise de dados, análise competitiva
2. **Valide o problema**: Garanta que vale a pena resolver
3. **Verifique alinhamento estratégico**: Isso se encaixa no nosso roadmap?
4. **Estime esforço**: T-shirt size aproximado com engenharia
5. **Considere alternativas**: Esta é a melhor solução?

### Durante Criação do PRD

1. **Seja claro, não esperto**: Linguagem simples ganha
2. **Mostre, não conte**: Use exemplos, mockups, diagramas
3. **Pense em edge cases**: O que pode dar errado?
4. **Priorize implacavelmente**: O que é MVP vs nice-to-have?
5. **Colabore cedo**: Não trabalhe isolado

### Após Completar o PRD

1. **Revise com stakeholders**: Obtenha feedback cedo
2. **Itere baseado em input**: PRDs são documentos vivos
3. **Apresente, não apenas compartilhe**: Caminhe através do PRD
4. **Obtenha sign-off formal**: Garanta compromisso
5. **Mantenha atualizado**: Ajuste conforme entendimento evolui

## Exemplos

### Exemplo 1: PRD de Feature Mobile

```bash
# Usuário: "Crie um PRD para adicionar autenticação biométrica ao nosso app iOS"

# Assistente irá:
# 1. Fazer perguntas de discovery sobre requisitos de segurança, personas, auth existente
# 2. Gerar PRD cobrindo:
#    - Problema: Fricção de senha, preocupações de segurança
#    - Solução: Integração Face ID / Touch ID
#    - User stories: Habilitar biométrico, fallback para senha, gestão de settings
#    - Métricas: Taxa de adoção, taxa de sucesso de login, tickets de suporte
#    - Técnico: iOS Keychain, LocalAuthentication framework
#    - Riscos: Compatibilidade de dispositivo, preocupações de privacidade
# 3. Output PRD formatado em markdown
```

### Exemplo 2: Melhoria de Plataforma Web

```bash
# Usuário: "Escreva requisitos para melhorar conversão do nosso checkout flow"

# Assistente irá:
# 1. Coletar dados sobre taxas de conversão atuais e pontos de abandono
# 2. Gerar PRD incluindo:
#    - Análise do estado atual com métricas
#    - Melhorias propostas (guest checkout, pagamento salvo, indicador de progresso)
#    - Plano de teste A/B
#    - Métricas de sucesso: Aumento de taxa de conversão, tempo até checkout
#    - User stories para cada melhoria
# 3. Incluir abordagem de rollout em fases
```

### Exemplo 3: PRD de Produto B2B

```bash
# Usuário: "Preciso de um PRD para um dashboard admin para clientes enterprise"

# Assistente irá:
# 1. Identificar requisitos específicos de B2B (multi-tenancy, permissões, relatórios)
# 2. Gerar PRD abrangente com:
#    - Personas de usuário enterprise (admin, gerente, analista)
#    - Requisitos de controle de acesso baseado em roles
#    - Necessidades de relatórios e analytics
#    - Requisitos de integração (SSO, SCIM)
#    - Métricas de sucesso: Adoção pelo cliente, eficiência do admin
# 3. Incluir considerações específicas de enterprise (compliance, SLAs)
```

## Troubleshooting

**Problema: PRD está muito longo/detalhado**

Solução: Crie um "PRD Lean" focando em problema, solução, critérios de aceite e métricas. Reserve PRD completo para iniciativas maiores.

**Problema: Requisitos estão muito vagos**

Solução: Adicione exemplos específicos, use números concretos, inclua referências visuais. Substitua "rápido" por "carrega em menos de 2 segundos."

**Problema: Stakeholders não alinhados**

Solução: Compartilhe PRD cedo como draft, incorpore feedback, apresente pessoalmente, obtenha sign-off explícito antes do desenvolvimento começar.

**Problema: Escopo continua expandindo**

Solução: Use seção "Fora do Escopo" agressivamente, crie PRDs separados para fases futuras, amarre escopo a restrições de timeline.

**Problema: Engenheiros dizem que não é viável**

Solução: Envolva engenharia mais cedo no processo, seja flexível na abordagem da solução, foque no problema não na implementação.

## Resumo de Melhores Práticas

1. **Comece com o problema, não a solução**
2. **Escreva para seu público** (execs precisam de resumo, engenheiros precisam de detalhes)
3. **Seja específico e mensurável** (evite linguagem vaga)
4. **Inclua visuais** (mockups, diagramas, fluxos)
5. **Defina sucesso de antemão** (métricas, não features)
6. **Escopeie agressivamente** (mentalidade MVP)
7. **Colabore, não dite** (obtenha input de todas as funções)
8. **Mantenha atualizado** (PRD é documento vivo)
9. **Foque em "por que" e "o que", não "como"** (deixe engenheiros resolverem "como")
10. **Torne escaneável** (headers, bullets, resumos)
