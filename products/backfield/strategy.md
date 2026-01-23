# Backfield - Product Strategy

**Produto:** Backfield (Operações de Campo)
**Status:** Draft
**Autor:** Rafael Vaz
**Stakeholders:** Time de Operações, CGS, Suprimentos
**Data de Criação:** 2026-01-23
**Última Atualização:** 2026-01-23
**Versão:** 1.0

---

## Sumário

1. [Product Vision](#1-product-vision)
2. [Product Insights](#2-product-insights)
3. [Challenges](#3-challenges)
4. [Approaches](#4-approaches)
5. [Accountability](#5-accountability)
6. [Sign-off](#sign-off)

---

## 1. Product Vision

A **essência** da estratégia do produto. Define o quê, para quem e por que agora.

### What (Problema)

Operações de campo da Gabriel dependem de sistemas fragmentados (Airtable, Backend, Hubspot, S3, planilhas no Google Sheets, conversas fragmentadas no Slack e Whatsapp) para gerenciar ordens de serviço, estoque e provisionamento de equipamentos. Isso gera:

- Retrabalho manual para o CGS
- Dependência dos técnicos em relação ao suporte interno
- Falta de visibilidade end-to-end das operações
- Limitações de escala (Airtable com limite de registros, ineficiência operacional pelo excesso de etapas manuais)

### Who (Cliente-Alvo)

Backfield serve **múltiplos usuários internos**:

| Persona | Função | Necessidade Principal |
|---------|--------|----------------------|
| **CGS** | Alocação de OS's, controle de qualidade remoto, suporte | Reduzir tempo em tarefas manuais |
| **Técnicos Parceiros** | Execução de instalações/manutenções em campo | Autonomia para resolver problemas e ter visibilidade dos processos sem depender do CGS |
| **Suprimentos** | Gestão de estoque, abastecimento de parceiros | Visibilidade de movimentações e divergências, integração com Operador Logístico |
| **Backoffice** | Supervisão de equipes parceiras | Ferramental para controle e acompanhamento de produtividade |

### Why Now (Timing)

Convergência de fatores críticos em 2026:

1. **Deadline Airtable (15/04/2026):** Limite de registros; migração de dados para Bifrost é obrigatória
2. **Escala da operação:** ~5.000 contratos ativos processando 1.500-3.000 OS's/mês
3. **Novo hardware (Camaleão 3):** Requer novo fluxo de provisionamento no backend
4. **Compliance (DCe):** Declaração de Conteúdo Eletrônica obrigatória a partir de 06/04/2026

### Vision Statement

| Campo | Conteúdo |
|-------|----------|
| **Para** | Times operacionais da Gabriel (CGS, Suprimentos, Backoffice, Técnicos) |
| **Que** | Precisam gerenciar ordens de serviço, estoque e provisionamento de forma eficiente |
| **O** | Backfield é uma plataforma de operações de campo |
| **Que** | Integra OS's, estoque e provisionamento em um ecossistema unificado e automatizado |
| **Ao contrário de** | Airtable, planilhas e sistemas desconectados |
| **Nosso produto** | Oferece integração end-to-end (HubSpot → OS → Estoque → Provisionamento) com automação de processos |

**Consolidated Vision Statement:**

> O Backfield é a plataforma que conecta todos os sistemas de operações de campo da Gabriel, permitindo que times internos e parceiros externos executem serviços de forma autônoma, escalável e rastreável — substituindo a fragmentação atual por um ecossistema integrado ao backend (API Bifrost).

### Conexão com a Visão da Empresa

A Gabriel tem como missão tornar autoridades de segurança pública mais eficientes através de visão computacional. Para entregar esse valor, a empresa precisa:

1. **Instalar equipamentos** (Camaleões) em milhares de locais
2. **Manter a operação** funcionando com qualidade
3. **Escalar** para novas cidades e regiões

Backfield é a **infraestrutura operacional** que viabiliza essa escala. Sem operações eficientes, a Gabriel não consegue crescer de ~5.000 para ~10.000+ contratos.

---

## 2. Product Insights

A **lógica** da estratégia. Dados, diferenciadores e conhecimento de mercado.

### 2.1 Contexto Competitivo (Interno)

Como plataforma interna, Backfield não compete no mercado externo. A "competição" são as alternativas internas:

| Alternativa | Força | Fraqueza |
|-------------|-------|----------|
| **Airtable** | Flexível, rápido para prototipar | Limite de registros, sem integração nativa, será desligado |
| **Planilhas** | Familiar para todos | Zero automação, erros humanos, sem rastreabilidade |
| **WhatsApp** | Comunicação instantânea | Informação perdida, sem histórico estruturado |
| **Processos manuais** | Funcionam no curto prazo | Não escalam, dependem de pessoas específicas |

**Posição do Backfield:** Substituir todas as alternativas acima por sistemas integrados e automatizados, centralizando as regras de negócio no nosso Backend (Bifrost).

### 2.2 Contexto de Mercado

**Métricas da Gabriel (Jan/2026):**

| Métrica | Valor |
|---------|-------|
| MRR | ~R$ 4M |
| Contratos ativos | ~5.000 |
| Churn | 11.4% |
| OS's/mês | 1.500-3.000 |
| Regiões | SP, RJ, MG |

**Oportunidade:** Meta de crescimento para R$ 7M MRR em 2026 exige operações mais eficientes para suportar mais contratos sem aumentar proporcionalmente o time de CGS.

### 2.3 Tendências Internas (2026)

| Tendência | Impacto no Backfield |
|-----------|---------------------|
| **Expansão geográfica** | Novos parceiros, novos locais de estoque |
| **Aumento de volume** | Mais OS's, mais movimentações de estoque |
| **Novos tipos de serviço** | Camaleão 3, novos fluxos de provisionamento |
| **Pressão por eficiência** | Automação para fazer mais com menos |

### 2.4 Personas

#### Persona 1: Operador CGS

| Atributo | Descrição |
|----------|-----------|
| **Perfil** | Analista de operações, 25-35 anos |
| **Comportamento** | Gerencia dezenas de OS's por dia, usa múltiplos sistemas |
| **Necessidade** | Reduzir tempo gasto em tarefas repetitivas |
| **Motivação** | Resolver problemas de instalações e ajudar técnicos |
| **Dor Principal** | Muito tempo em tarefas manuais (copiar dados, atualizar status, enviar mensagens) |

_"Passo metade do meu dia atualizando planilhas e copiando informações de um sistema para outro."_

---

#### Persona 2: Técnico Parceiro

| Atributo | Descrição |
|----------|-----------|
| **Perfil** | Técnico de campo, 25-45 anos, trabalha para parceiros (Icatel, C&K, etc.) |
| **Comportamento** | Executa 3-5 OS's por dia, usa app mobile |
| **Necessidade** | Informações claras para executar o serviço |
| **Motivação** | Finalizar OS's rapidamente para ganhar mais |
| **Dor Principal** | Precisa ligar para o CGS para resolver problemas simples |

_"Às vezes fico 30 minutos esperando o CGS me passar uma informação que deveria estar no app."_

---

#### Persona 3: Analista de Suprimentos

| Atributo | Descrição |
|----------|-----------|
| **Perfil** | Analista de supply chain, 28-40 anos |
| **Comportamento** | Gerencia estoque de múltiplas regiões, faz conciliação com Omie |
| **Necessidade** | Visibilidade das movimentações de estoque |
| **Motivação** | Evitar falta de material e divergências |
| **Dor Principal** | Divergências entre sistema e estoque real |

_"Todo mês passo dias tentando entender por que o estoque no sistema não bate com o físico."_

---

## 3. Challenges

Os **obstáculos** da estratégia. Riscos e desafios antecipados.

### 3.1 Desafios Técnicos

#### Migração Airtable → Bifrost

- **Impacto:** Alto
- **Complexidade:** Alta
- **Descrição:** Migrar dados históricos, automações e integrações do Airtable para o Bifrost sem interromper operações. Envolve tabelas de `movimento_de_estoque`, `movimento_interno_de_estoque`, `ordens-de_servico`.

#### Integrações Múltiplas

- **Impacto:** Médio
- **Complexidade:** Média
- **Descrição:** Manter sincronização entre HubSpot, Omie, Bifrost, S3, Appsmith. Cada sistema tem suas limitações e APIs diferentes.

#### Capacidade do Time

- **Impacto:** Médio
- **Complexidade:** Média
- **Descrição:** Time composto por 2 engenheiros júnior (Gabriel Akio, Vinícius Borsato). Entregas complexas podem exigir suporte de Staff Engineers da tribe.

### 3.2 Dores do Cliente (Interno)

#### Curva de Aprendizado

- **Tipo:** Comportamental
- **Severidade:** Média
- **Descrição:** Usuários acostumados com Airtable/planilhas podem resistir a novos fluxos no Bifrost. Treinamento e comunicação são necessários, mas centralizamos as aplicações no Appsmith, o que deve se manter.

### 3.3 Riscos de GTM/Operação

#### Deadline Airtable (15/04/2026)

- **Probabilidade:** Certa (deadline externo)
- **Impacto:** Crítico
- **Descrição:** Se a migração não for concluída, operações de campo param. Não há plano B.

#### Coordenação com Outros Squads

- **Probabilidade:** Média
- **Impacto:** Médio
- **Descrição:** Dependências com squad de Borda (Camaleão 3), Dados e Infraestrutura podem atrasar entregas, stakeholders esclarecerem requisitos

### 3.4 Requisitos Legais/Regulatórios

#### DCe - Declaração de Conteúdo Eletrônica

- **Obrigatório:** Sim
- **Deadline:** 06/04/2026
- **Descrição:** Nova obrigatoriedade para transporte de mercadorias. Time de Suprimentos identificou impacto na Gabriel.

#### LGPD

- **Obrigatório:** Sim
- **Deadline:** Contínuo
- **Descrição:** Dados de clientes, técnicos e parceiros precisam seguir práticas de privacidade. Atenção especial ao armazenar fotos e dados de localização.

---

## 4. Approaches

Os **caminhos** da estratégia. Como alcançar a visão.

### 4.1 Abordagem Estratégica

**Tipo:** Feature Parity + Migração

**Estratégia Principal:**

A prioridade absoluta do Backfield em 2026 é **migrar do Airtable para o Bifrost** mantendo paridade de funcionalidades. Não se trata de redesenhar a operação, mas de transferir os fluxos existentes para uma infraestrutura sustentável.

**Fases:**

1. **Q1/2026 - Migração Crítica (Deadline: 15/04/2026)**
   - Migrar tabelas de estoque (`movimento_de_estoque`, `movimento_interno_de_estoque`)
   - Migrar ordens de serviço para Bifrost
   - Migrar automações do Airtable para backend
   - Garantir integração 3PL funcionando no Bifrost
   - Provisionamento automático do Camaleão 3

2. **Q2-Q3/2026 - Evolução**
   - Implementar DCe (Declaração de Conteúdo Eletrônica)
   - Serialização de estoque
   - Novas fases de OS
   - Melhorias de automação operacional

3. **Q4/2026 - Escala + Automação**
   - Automação de processos operacionais end-to-end
   - Redução de intervenções manuais
   - Preparação para escala 10k+ contratos

### 4.2 Superando Desafios

| Desafio | Plano de Mitigação | Responsável |
|---------|-------------------|-------------|
| Migração Airtable (deadline 15/04) | Spike BAO-118 para mapear dados + refinamento com Suprimentos. Priorização absoluta, sem features novas até migração. | Rafael (PM) + Time |
| Capacidade do time | Solicitar apoio de Staff Engineers se necessário | GPM |
| DCe | Spike BAO-119 para entender impacto | Rafael (PM) |
| Curva de aprendizado | Comunicação proativa + treinamento com CGS/Suprimentos | Rafael (PM) |

### 4.3 Guardrails (Do's & Don'ts)

**O que FAREMOS (Do's):**

- [x] Priorizar migração sobre features novas até 15/04
- [x] Manter feature parity durante migração
- [x] Documentar decisões técnicas no Linear
- [x] Comunicar mudanças proativamente aos stakeholders
- [x] Construir para escala (pensar em 10k+ contratos)

**O que NÃO FAREMOS (Don'ts):**

- [ ] Criar features novas antes de concluir migração crítica
- [ ] Customizar soluções para casos específicos de um parceiro
- [ ] Acumular débito técnico para cumprir prazos
- [ ] Implementar sem refinar com stakeholders (CGS, Suprimentos)
- [ ] Depender de automações no Airtable após 15/04

### 4.4 Posicionamento: Plataforma vs. Sistema

> **O Backfield é uma PLATAFORMA que serve Operações.**
>
> Operações usa o que oferecemos para criar e operar ferramentas de acordo com suas regras de negócio. Não somos um sistema customizado para cada caso de uso.

Isso significa:
- Construímos **capacidades genéricas** (APIs, fluxos, integrações)
- Operações **configura e opera** de acordo com suas necessidades
- Evitamos **customizações one-off** que não escalam

---

## 5. Accountability

A **medida** da estratégia. Como saber se está funcionando.

### 5.1 North Star Metric

O Backfield tem **duas North Stars** dependendo da fase:

#### 2026 (Fase de Migração)

**Métrica:** % de fluxos operacionais rodando na Bifrost

| Atributo | Valor |
|----------|-------|
| **Definição** | Proporção de fluxos de OS e estoque que não dependem mais do Airtable |
| **Baseline (Jan/2026)** | ~20% |
| **Target (Abr/2026)** | 80% (fluxos críticos migrados) |
| **Target (Jun/2026)** | 100% |
| **Por que essa métrica** | Captura o objetivo estratégico principal do Q1: sair do Airtable |

#### 2027+ (Fase de Escala)

**Métrica:** Taxa de automação de processos operacionais

| Atributo | Valor |
|----------|-------|
| **Definição** | % de fluxos que rodam end-to-end sem intervenção manual |
| **Baseline** | A definir após migração |
| **Target** | A definir |
| **Por que essa métrica** | Representa eficiência operacional e capacidade de escalar |

### 5.2 Métricas de Suporte

#### Métricas de Impacto (influenciamos)

| Métrica | Atual | Target Q2 | Target Q4 |
|---------|-------|-----------|-----------|
| Taxa de OS's produtivas | - | +5% | +10% |
| Divergências de estoque | - | -30% | -50% |
| Chamados ao CGS (por OS) | - | -20% | -40% |
| Tempo de provisionamento | - | -25% | -50% |

### 5.3 Acompanhamento

**Frequência de Revisão:** Semanal (sprint review)

**Responsável:** Rafael Vaz (PM)

**Rituais:**

| Ritual | Frequência | Participantes | Objetivo |
|--------|------------|---------------|----------|
| Sprint Review | Quinzenal | Squad + Stakeholders | Demo de entregas |
| Sync com CGS | Semanal | PM + CGS Lead | Feedback operacional |

**Dashboard:** DataDog (a configurar)

### 5.4 Notas de Accountability

- Métricas de impacto (OS produtivas, divergências) dependem de como Operações usa a plataforma
- Backfield é accountable pela **disponibilidade e capacidade** da plataforma
- Operações é accountable pelo **uso efetivo** das ferramentas
- Revisão trimestral das North Stars para ajustar conforme aprendizados

---

## Sign-off

### Aprovação dos Stakeholders

| Stakeholder | Cargo | Status | Aprovado | Data |
|-------------|-------|--------|----------|------|
| Matias Montangero | Líder de Operações | ⏳ Pendente | ☐ | - |
| Felipe França | Lead CGS | ⏳ Pendente | ☐ | - |
| Victor Esteves | Suprimentos | ⏳ Pendente | ☐ | - |
| [EM Plataforma] | Engineering Manager | ⏳ Pendente | ☐ | - |

### Notas da Revisão

_[Capturar feedback importante das revisões com stakeholders]_

---

## Apêndice

### Referências

- [Linear - Team BAO](https://linear.app/gabriel-tecnologia/team/BAO)
- [Spike BAO-118 - Migração Estoque](https://linear.app/gabriel-tecnologia/issue/BAO-118)
- [Spike BAO-119 - DCe](https://linear.app/gabriel-tecnologia/issue/BAO-119)
- [Projeto - Morte do Airtable](https://linear.app/gabriel-tecnologia/project/morte-do-airtable-para-operacoes-de-campo-8d28a86afff8)
- [Projeto - Integração 3PL](https://linear.app/gabriel-tecnologia/project/integrar-um-operador-logistico-3pl-na-gestao-de-estoque-da-gabriel-084edca59b41)

### Assets Operados

| Repositório | Descrição | Status |
|-------------|-----------|--------|
| App do Parceiro | App mobile para técnicos de campo | Produção |
| App do Backoffice | App para supervisores de equipes | Produção |
| App do CGS | Sistema de gerenciamento de OS | Produção |
| Sistema de Estoque | Controle de movimentações | Produção (migrando) |
| Sistema de Snapshots no App de Diagnóstico de SN2 | Validação de angulação de câmeras | Produção |

### Integrações

| Sistema | Função | Tipo |
|---------|--------|------|
| Bifrost API | Backend principal | Próprio |
| Airtable | Legado (em migração) | No-code DB |
| HubSpot | CRM | Externo |
| Omie | ERP | Externo |
| AWS S3 | Storage de fotos | Cloud |
| Appsmith | Construção de Aplicações Low-Code | Interface low-code |

### Changelog

| Versão | Data | Autor | Mudanças |
|--------|------|-------|----------|
| 1.0 | 2026-01-23 | Rafael Vaz | Versão inicial |
