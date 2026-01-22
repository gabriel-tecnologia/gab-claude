# Estratégia de Produto: Gabriel OS

**Status:** Draft
**Autor:** Vitor Finger
**Stakeholders:** Vitor Finger (CPO), Carolina Higo (EM), Luiz Torres (GPM), Beatriz Lima (PM)
**Data de Criação:** 2026-01-21
**Última Atualização:** 2026-01-21
**Versão:** 1.0

---

## Sumário

1. [Visão do Produto](#1-visão-do-produto)
2. [Insights de Produto](#2-insights-de-produto)
3. [Desafios](#3-desafios)
4. [Abordagens](#4-abordagens)
5. [Accountability](#5-accountability)
6. [Sign-off](#sign-off)

---

## 1. Visão do Produto

A **essência** da estratégia. Define o quê, para quem e por que agora.

### Visão da Plataforma (Guarda-Chuva)

O Gabriel OS é uma **plataforma modular de inteligência em vídeo** — similar ao modelo HubSpot — que atende diferentes stakeholders com módulos especializados compartilhando uma infraestrutura comum.

| Módulo | Cliente | Problema | Timeline |
|--------|---------|----------|----------|
| **Autoridades** | Delegacias, polícias | Investigação de crimes com recursos limitados | **2026 (foco)** |
| **Enterprise B2B** | Redes varejistas, empresas | Prevenção de perdas, segurança distribuída | 2027+ |
| **Operações Internas** | Central 24h Gabriel | Saúde de dispositivos, escala operacional | 2027+ |

**Infraestrutura Compartilhada:**
- Plataforma de Vídeo (live, histórico, storage)
- LPR/Reconhecimento (placas, veículos)
- Mapa/Geolocalização (mapeamento de câmeras, rotas)
- Alertas de analíticos e ocorrências

**Não compartilhado:** Alertas de saúde de parque (apenas Operações Internas + Enterprise)

### Declaração de Visão (Plataforma)

| Campo             | Conteúdo                                                                                       |
| ----------------- | ---------------------------------------------------------------------------------------------- |
| **Para**          | Organizações que precisam gerenciar e extrair inteligência de infraestrutura de vídeo          |
| **Que**           | Precisam de mais do que monitoramento — precisam de insights acionáveis                        |
| **O**             | Gabriel OS é uma plataforma modular de inteligência em vídeo                                   |
| **Que**           | Transforma dados de câmeras em inteligência operacional e estratégica                          |
| **Ao contrário**  | VMS tradicionais (apenas visualização) ou soluções fragmentadas                                |
| **Nosso produto** | Oferece módulos especializados para diferentes stakeholders compartilhando infraestrutura core |

---

### Foco 2026: Módulo Autoridades

**Para quem:** Delegacias, polícias civil e militar, operadores de segurança pública

**O Quê (Problema):**

1. **Monitoramento de vídeo ineficiente**: Autoridades não têm ferramentas para visualizar e operar múltiplas câmeras de forma eficiente
2. **Resposta lenta a incidentes**: Falta de integração entre câmeras e investigação criminal
3. **Rastreamento de veículos**: Necessidade de visualizar rotas de veículos específicos e criar hot lists de veículos roubados ou envolvidos em crimes

**Por Que Agora (Timing):**

1. **Janela de implementação**: Autoridades estão ativamente interessadas em implementar o Gabriel OS em delegacias — essa é uma janela de oportunidade que pode fechar
2. **Pressão competitiva**: Paladium levantou R$100M+ e está mirando segurança pública; CoSecurity já está presente em delegacias com VMS simples; DGT (Bridgefy) tem forte presença no Sul
3. **Transformação estratégica**: Momento de evoluir de "ferramenta de visualização" para "plataforma de inteligência para resolver crimes"

### Declaração de Visão (Módulo Autoridades)

| Campo             | Conteúdo                                                                         |
| ----------------- | -------------------------------------------------------------------------------- |
| **Para**          | Delegacias e operadores de segurança pública                                     |
| **Que**           | Precisam investigar crimes de forma eficiente com recursos limitados             |
| **O**             | Gabriel OS (Módulo Autoridades) é uma plataforma de inteligência investigativa   |
| **Que**           | Transforma dados de câmeras em inteligência acionável para resolver crimes       |
| **Ao contrário**  | VMS tradicionais (só visualização) ou ferramentas forenses caras                 |
| **Nosso produto** | Combina monitoramento em tempo real com inteligência investigativa em um produto |

**Visão Consolidada:**

> Fazer com que as autoridades consigam operar a Gabriel de forma autônoma, extraindo inteligência das câmeras para resolver mais crimes — sem depender da Central 24h da Gabriel. Permitir que delegacias escalem sua capacidade investigativa usando dados de vídeo.

### Conexão com a Visão da Empresa

A visão da Gabriel é ser a **infraestrutura de inteligência que conecta cidades e autoridades** para uma segurança pública mais efetiva. O Gabriel OS para autoridades materializa essa visão ao entregar as ferramentas que permitem às autoridades operar a infraestrutura Gabriel diretamente.

---

### Módulos Futuros (Roadmap)

#### Enterprise B2B (2027+)

**Problema:** Prevenção de perdas e segurança em locais distribuídos

**Usuários:** Times de segurança, times de operações

**Features Planejadas:**
- Gestão própria de parque de câmeras
- Criação de hot lists (veículos, faces de pessoas non gratas)
- Compartilhamento entre unidades (inteligência cross-chain)
- **Integração multi-dispositivo:**
  - Câmeras internas para detecção de movimento
  - Dispositivos de áudio para identificação de falas específicas
  - Câmeras especializadas de LPR para maior taxa de acerto

**Moat Competitivo:** A definir — requer exploração do cliente

#### Operações Internas (2027+)

**Problema:**
- Monitoramento de saúde de dispositivos
- Manutenção remota (reinicialização, firmware)
- Gestão de clientes
- Eficiência operacional

**Pain Points:** Ferramentas fragmentadas, limitação de escala, tempo de resposta lento

**Diferenciação:** Self-service, escalabilidade, integração com sistemas internos

---

## 2. Insights de Produto

A **lógica** da estratégia. Dados, diferenciadores e conhecimento de mercado.

### 2.1 Concorrentes (Análise Competitiva)

| Concorrente | Foco | Forças | Fraquezas | Diferenciador Gabriel |
|-------------|------|--------|-----------|----------------------|
| **Paladium** | IA forense para governo | R$100M+ levantados, foco em IA, tecnologia soberana brasileira, compliance LGPD | Sem integração com hardware próprio | Gabriel tem hardware + software integrado |
| **DGT (Bridgefy)** | Plataforma smart city, segurança pública | Visão computacional, busca de padrões, forte presença em RS/SC, 200+ cidades | Menos capital, sem integração de hardware | Gabriel tem rede nacional + hardware próprio |
| **Flock Safety** | Enterprise + governo (EUA) | Benchmark em extração de inteligência, 20B+ scans/mês, Vehicle Fingerprint | Não opera no Brasil | Gabriel entende contexto brasileiro |
| **CoSecurity** | Concorrente direto | Já está em delegacias, botão pânico | VMS simples, sem inteligência avançada | Gabriel tem impacto comprovado + features superiores |
| **VMS Tradicionais** | Apenas monitoramento | Estabelecidos (Milestone, Genetec, Hikvision) | Só visualização, sem inteligência | Gabriel oferece inteligência investigativa |

**Nossa Posição Competitiva:**

- **vs Paladium**: Ambos focam em segurança pública com IA. Gabriel diferencia por ter **hardware próprio integrado** (Camaleão), criando um ecossistema fechado e dados proprietários
- **vs DGT (Bridgefy)**: DGT é forte no Sul (RS/SC). Gabriel tem presença nacional e integração vertical com hardware
- **vs Flock Safety**: Flock é o benchmark de features. Gabriel deve evoluir para esse nível de capacidades, mas com distribuição gratuita para autoridades
- **vs CoSecurity**: CoSecurity tem VMS básico em delegacias. Gabriel oferece inteligência superior + distribuição gratuita

**Moat Competitivo (Autoridades):** **Distribuição GRATUITA**
- O produto real da Gabriel é o Camaleão (hardware)
- Gabriel OS gratuito → comprova valor → vende mais Camaleão
- Qualquer concorrente pago se torna menos atrativo
- Autoridades podem integrar câmeras de outras empresas também

### 2.2 Insights de Mercado

**Tamanho de Mercado:**
- Mercado de segurança Brasil: **USD 7B em 2024 → USD 14.7B em 2034** (CAGR 7.7%)
- Video surveillance: **39.6% do mercado**
- Access control: USD 536M em 2024 → USD 1.2B em 2033 (CAGR 9.42%)

**Investimento Governamental:**
- Plano Nacional de Segurança Pública: **USD 300M** para sistemas de vigilância inteligente
- Tendência de integração de agências policiais em sistema único
- Demanda crescente por tecnologia em segurança pública

**Tendências Relevantes:**

1. **IA em segurança pública**: Adoção crescente de visão computacional para reconhecimento de placas, faces e padrões
2. **Integração de sistemas**: Movimento para conectar diferentes agências e bases de dados
3. **Smart cities**: Municípios investindo em infraestrutura de monitoramento urbano
4. **LPR como commodity**: Reconhecimento de placas se tornando feature básica; diferenciação vem da inteligência sobre os dados

**Fontes:**
- [Ken Research - Brazil Electronic Security Market](https://www.kenresearch.com/brazil-electronic-security-and-smart-surveillance-market)
- [Expert Market Research - Brazil Security Market](https://www.expertmarketresearch.com/reports/brazil-security-market)
- [IMARC Group - Brazil Access Control Market](https://www.imarcgroup.com/brazil-access-control-market)

### 2.3 Insights de Cliente (Personas Autoridades)

**Persona 1: Delegado / Investigador**

| Atributo | Descrição |
|----------|-----------|
| **Demografia** | 35-55 anos, delegado de polícia civil ou investigador |
| **Comportamento** | Precisa de evidências para casos, trabalha sob pressão de prazos |
| **Necessidades** | Busca rápida de veículos, histórico de rotas, exportação de evidências |
| **Motivações** | Resolver mais casos, aumentar taxa de elucidação |
| **Dores** | Ferramentas fragmentadas, processos manuais, falta de inteligência |

_"Preciso encontrar um veículo que foi visto na cena do crime há 3 dias. Com as ferramentas atuais, isso leva horas. Precisa ser mais rápido."_

---

**Persona 2: Operador 24h**

| Atributo | Descrição |
|----------|-----------|
| **Demografia** | 25-45 anos, operador de monitoramento em tempo real |
| **Comportamento** | Monitora múltiplas câmeras simultaneamente, responde a alertas |
| **Necessidades** | Interface intuitiva, alertas inteligentes, visualização multi-câmera |
| **Motivações** | Responder rapidamente a incidentes, não perder eventos críticos |
| **Dores** | Sobrecarga de informação, interface complexa, falsos positivos |

_"Tenho 50 câmeras pra monitorar. Preciso que o sistema me avise do que é importante."_

---

**Persona 3: Gestor de Segurança Pública**

| Atributo | Descrição |
|----------|-----------|
| **Demografia** | 40-60 anos, secretário de segurança ou comandante |
| **Comportamento** | Precisa justificar investimentos, reportar resultados |
| **Necessidades** | Dashboards, métricas de impacto, relatórios |
| **Motivações** | Demonstrar resultados, reduzir criminalidade, justificar orçamento |
| **Dores** | Falta de dados para tomada de decisão estratégica |

_"Preciso mostrar ao prefeito que o investimento em câmeras está dando resultado."_

---

## 3. Desafios

Os **obstáculos** da estratégia. Riscos e barreiras antecipadas.

### 3.1 Customer Pain Points

**Desafio Principal: Adoção pelos usuários**

- **Tipo:** Comportamental
- **Severidade:** **CRÍTICA**
- **Descrição:** Para a Gabriel efetivamente gerar valor, as autoridades precisam usar a ferramenta de verdade, extrair inteligência e resolver casos com ela. Baixa adoção = zero valor.

**Desafio: Percepção de valor**

- **Tipo:** Emocional/Psicológico
- **Severidade:** Alta
- **Descrição:** Autoridades podem ver como "mais uma ferramenta" se não demonstrarmos valor rápido. Precisa haver "quick wins" para gerar confiança.

### 3.2 Technical

**Desafio: Escala de infraestrutura**

- **Impacto:** Médio
- **Complexidade:** Alta
- **Descrição:** Mais câmeras, mais dados, mais processamento. Precisa escalar sem degradar performance.

**Desafio: Acesso a dados de outcome**

- **Impacto:** Médio
- **Complexidade:** Alta
- **Descrição:** Não temos visibilidade dos crimes resolvidos pelas delegacias. Difícil medir impacto real sem esses dados.

### 3.3 GTM Risks

**Risco: Timing — Perder a janela de oportunidade**

- **Probabilidade:** Média-Alta
- **Impacto:** **CRÍTICO**
- **Descrição:** Se um concorrente (Paladium, DGT, CoSecurity) ocupar as delegacias primeiro, será muito mais difícil entrar depois. A janela de interesse das autoridades é AGORA.

**Risco: Competição com players capitalizados**

- **Probabilidade:** Alta
- **Impacto:** Alto
- **Descrição:** Paladium levantou R$100M+ e está mirando o mesmo mercado. Velocidade de execução é crítica.

---

## 4. Abordagens

Os **caminhos** da estratégia. Como alcançar a visão.

### 4.1 Abordagem (Estratégia Escolhida)

**Tipo de Abordagem:** Multi-prong focada em escala via self-service

**Estratégia Principal:**

A estratégia do Gabriel OS para 2026 foca em **permitir que autoridades operem a Gabriel de forma autônoma**, sem depender da Central 24h, para escalar a operação sem aumento proporcional de headcount.

**Pilares da Estratégia:**

1. **Modelo Self-Service para Delegacias (PRIORIDADE #1):** Delegacias conseguem usar o Gabriel OS de forma independente, sem acionar a Central 24h. Isso permite escala em novas cidades sem footprint operacional pesado.

2. **Features de Inteligência:** Evoluir de "ferramenta de visualização e filtros" para "plataforma de extração de inteligência". Busca de rotas, hot lists, alertas inteligentes.

3. **Distribuição Gratuita (Moat):** Gabriel OS gratuito para autoridades. O valor está em vender mais Camaleão e demonstrar impacto.

**Justificativa:**

O foco em self-service ataca diretamente o desafio de escala: a Gabriel não pode crescer para novas cidades se cada cidade requer operação pesada da Central 24h. O modelo de distribuição gratuita cria barreira competitiva contra qualquer solução paga.

### 4.2 Superar Desafios

| Desafio | Plano de Mitigação | Responsável |
|---------|-------------------|-------------|
| Adoção pelos usuários | Programa de onboarding, treinamento in-loco, métricas de sucesso, quick wins | Squad GabrielOS + PM |
| Timing | Implementação agressiva nas delegacias interessadas, fast follow em oportunidades | PM + Comercial |
| Escala técnica | Arquitetura para alta escala desde o início, monitoramento de performance | Engineering |
| Acesso a dados | Criar métricas proxy que conseguimos medir (buscas, exports, alertas) | PM + Data |

### 4.3 Do's & Don'ts (Guardrails)

**O que FAREMOS (Do's):**

- [x] Focar em casos de uso investigativos (resolver crimes)
- [x] Medir contribuição para resolução de crimes (mesmo que proxy)
- [x] Distribuir gratuitamente para autoridades
- [x] Priorizar UX para operadores não-técnicos
- [x] Integrar com câmeras de outras empresas (não só Camaleão)
- [x] Implementar analytics para medir adoção

**O que NÃO FAREMOS (Don'ts):**

- [ ] Competir em monitoramento puro (commodity)
- [ ] Cobrar de autoridades pelo software
- [ ] Over-engineer antes de validar adoção
- [ ] Depender da Central 24h para operação do cliente
- [ ] Ignorar a experiência do usuário (autoridades são menos técnicas)

---

## 5. Accountability

A **medida** da estratégia. Como saber se está funcionando.

### 5.1 North Star Metric

**Métrica:** Casos com Evidência Gabriel (Cases with Gabriel Evidence)

| Atributo | Valor |
|----------|-------|
| **Definição** | Número de casos criminais onde dados do Gabriel OS (vídeo, rota, busca de veículo) foram utilizados na investigação |
| **Por que esta métrica** | Mede o valor real entregue (não só uso, mas contribuição para resolver crimes) |
| **Como medir** | Contador de exports de evidência, relatórios gerados, buscas que resultaram em ação |
| **Baseline Atual** | 0 (nova métrica) |
| **Target (6 meses)** | 50 casos/mês |
| **Target (12 meses)** | 200 casos/mês |

**Por que não outras métricas:**
- "Crimes resolvidos" — não temos acesso a esse dado das delegacias
- "Usuários ativos" — não mede valor, só uso
- "Incidentes com Gabriel" — afetado por sazonalidade

### 5.2 Métricas de Suporte

**Métricas de Adoção:**

| Métrica | Baseline | Target 6mo | Target 12mo |
|---------|----------|------------|-------------|
| Delegacias ativas | 0 | 10 | 30 |
| Operadores ativos diários | 0 | 50 | 150 |
| DAU/MAU Ratio (Stickiness) | 0% | >20% | >30% |

**Métricas de Valor:**

| Métrica | Baseline | Target 6mo | Target 12mo |
|---------|----------|------------|-------------|
| Buscas de veículo/mês | 0 | 500 | 2.000 |
| Exports de evidência/mês | 0 | 100 | 500 |
| Hot lists criadas | 0 | 20 | 100 |

**Métricas de Engagement:**

| Métrica | Baseline | Target 6mo | Target 12mo |
|---------|----------|------------|-------------|
| Tempo médio de sessão | 0 | >15min | >20min |
| Alertas respondidos | 0 | >70% | >85% |

### 5.3 Tracking de Progresso

**Frequência de Revisão:** Semanal (squad) + Mensal (stakeholders)

**Responsável:** PM do Squad GabrielOS (Beatriz Lima)

**Rituais:**
- Weekly: Review de métricas no standup
- Monthly: Product Review com stakeholders
- Quarterly: Strategy Review com leadership

### 5.4 Notas de Accountability

Se as métricas não estiverem evoluindo após 4 semanas:

1. Investigar se o problema é de **awareness** (delegacias não sabem usar)
2. Investigar se o problema é de **valor** (features não resolvem dor real)
3. Investigar se o problema é de **UX** (interface muito complexa)
4. Pivotar abordagem se necessário

---

## Sign-off

### Aprovação dos Stakeholders

| Stakeholder | Papel | Status da Revisão | Aprovado | Data |
|-------------|-------|-------------------|----------|------|
| Vitor Finger | CPO | ⏳ Pendente | ☐ | - |
| Carolina Higo | Engineering Manager | ⏳ Pendente | ☐ | - |
| Luiz Torres | GPM | ⏳ Pendente | ☐ | - |
| Beatriz Lima | PM do Squad | ⏳ Pendente | ☐ | - |

### Notas da Revisão

[Capturar feedback importante das revisões dos stakeholders]

---

## Apêndice

### Referências

**Competidores:**
- [Paladium](https://paladium.ai/)
- [DGT / Bridgefy](https://dgt.com.br/en/bridgefy-en/)
- [Flock Safety](https://www.flocksafety.com/)
- [CoSecurity](https://www.cosecurity.com.br/)

**Mercado:**
- [Ken Research - Brazil Electronic Security Market](https://www.kenresearch.com/brazil-electronic-security-and-smart-surveillance-market)
- [Expert Market Research - Brazil Security Market](https://www.expertmarketresearch.com/reports/brazil-security-market)
- [IMARC Group - Brazil Access Control Market](https://www.imarcgroup.com/brazil-access-control-market)
- [Trade.gov - Brazil Safety and Security](https://www.trade.gov/country-commercial-guides/brazil-safety-and-security-0)

### Change Log

| Versão | Data | Autor | Mudanças |
|--------|------|-------|----------|
| 1.0 | 2026-01-21 | Vitor Finger | Draft inicial com visão guarda-chuva + foco 2026 em Autoridades |
