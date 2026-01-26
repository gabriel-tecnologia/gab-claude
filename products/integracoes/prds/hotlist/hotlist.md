# PRD: Hotlist

**Autor**: Luiz Torres
**Data**: 2026-01-24
**Status**: Em Review
**Ticket**: -

---

## Alinhamento do Problema

### Problema

A equipe de investigação criminal da Gabriel e autoridades parceiras não têm como monitorar placas de interesse em tempo real na rede de 16K câmeras. Investigações perdem janela de ação quando veículos passam sem que ninguém seja alertado.

### Por que isso importa?

- **Investigações perdem janela de ação**: veículo passa, ninguém sabe
- **Processo manual de busca retroativa é lento**: investigadores gastam horas buscando em histórico
- **Gabriel não entrega valor máximo da rede para parceiros públicos**: 16K câmeras e 90M detecções/mês subutilizadas

### Por que agora?

- Demanda urgente de investigadores internos e delegacias parceiras
- Infraestrutura de LPR já existe (90M detecções/mês)
- Concorrentes internacionais já oferecem (benchmark Flock, Axon, Motorola)

### Evidências

- Solicitações internas de investigadores criminais Gabriel
- Feedback de delegacias parceiras sobre necessidade de alertas em tempo real
- Análise competitiva: Flock Safety, Axon e Motorola oferecem funcionalidade equivalente

---

## Proposta de Valor

> "A Gabriel cria hotlists para monitorar veículos de interesse e alerta em segundos quando detectados em qualquer uma das 16.000 câmeras."

**Benefícios**:

- **Investigadores Gabriel**: produtividade em casos ativos
- **Autoridades parceiras**: resposta rápida em investigações
- **Gabriel**: demonstra valor da rede, fortalece parcerias públicas

---

## Objetivos

### Mensuráveis

1. **Latência detecção→alerta**: <30s (p95)
2. **Taxa de entrega de alertas**: >99%
3. **Disponibilidade do serviço**: 99.9%

### Imensuráveis

1. Aumentar eficiência operacional de investigadores criminais
2. Fortalecer relacionamento com autoridades parceiras
3. Demonstrar valor estratégico da rede de câmeras

---

## Não-Objetivos

| Não-Objetivo                            | Justificativa                                  |
| --------------------------------------- | ---------------------------------------------- |
| Interface gráfica para clientes         | MVP é API-first, UI vem na Fase 2              |
| Base específica de histórico de alertas | Usa base de dados existente                    |
| Gerenciamento de imagens                | Usa infraestrutura existente (S3 pré-assinado) |
| Canais adicionais (app, email, SMS)     | Fase 2 após validação                          |
| Self-service para clientes              | Gabriel opera no MVP                           |

---

## Usuários e Jobs-to-be-Done

| Persona                       | Job-to-be-Done                                            |
| ----------------------------- | --------------------------------------------------------- |
| Investigador Criminal Gabriel | "Preciso saber na hora que o carro do suspeito passar"    |
| Operador Central 24h          | "Quero criar hotlists para operações ativas"              |
| Autoridade parceira (futuro)  | "Quero receber alertas da rede Gabriel nos meus sistemas" |

---

## Principais Métricas a Monitorar

### Eficiência

- Latência detecção→webhook (p50/p95/p99)
- Taxa de entrega de webhooks por destino
- Tempo de processamento por evento

### Resultados

- **North Star**: Alertas gerados através de placas cadastradas em hotlists Gabriel
- Notificações geradas por hora/dia
- Alertas que resultaram em ação (feedback futuro)

### Adoção

- Hotlists ativas por mês
- Placas monitoradas por mês
- Investigadores usando o sistema

---

## Antes vs. Depois

| Aspecto       | Antes                                  | Depois                                         |
| ------------- | -------------------------------------- | ---------------------------------------------- |
| Monitoramento | Busca retroativa manual no histórico   | Alerta em tempo real (<30s)                    |
| Cobertura     | Investigador precisa saber onde buscar | 16K câmeras monitoram automaticamente          |
| Resposta      | Horas ou dias para localizar veículo   | Segundos após detecção                         |
| Escala        | Limitado a buscas pontuais             | Milhares de placas monitoradas simultaneamente |

---

## Narrativa

### História 1: Investigador Criminal Gabriel

> Carlos é investigador criminal da Gabriel. Recebeu informação de que um veículo envolvido em roubo de carga está circulando pela região metropolitana.

Antes: Carlos passava horas buscando manualmente no histórico de detecções, filtrando por região e horário. Quando encontrava uma passagem, o veículo já estava longe.

Depois: Carlos solicita ao operador da Central 24h que adicione a placa na hotlist "Op. Carga Q1". Em 10 segundos a placa está sendo monitorada por todas as 16K câmeras. Às 14h47, uma câmera na BR-116 detecta o veículo. Carlos recebe o alerta no sistema em 22 segundos. A equipe de campo é acionada e intercepta o veículo 3km adiante.

### História 2: Operador Central 24h

> Marina é operadora da Central 24h Gabriel. Ela gerencia várias operações simultâneas.

Antes: Marina recebia pedidos por telefone, anotava em planilha, e precisava lembrar de buscar no histórico periodicamente.

Depois: Marina cria hotlists via API para cada operação ativa. Cada hotlist tem seu próprio webhook configurado para o sistema do cliente. Quando placas são detectadas, os alertas vão automaticamente para o destino correto. Marina monitora apenas os dashboards de entrega.

---

## Experiência do Usuário (MVP)

1. Operador Gabriel cria hotlist via API
2. Adiciona placas à hotlist (placas herdam TTL da hotlist)
3. Quando câmera detecta placa, webhook dispara em <30s
4. Sistema destinatário recebe alerta em tempo real
5. Consultas históricas: usa base de dados existente

---

## Modelo de Dados

### HOTLIST - Propriedades

| Propriedade                 | Descrição                                          | Obrigatório |
| --------------------------- | -------------------------------------------------- | ----------- |
| **id**                      | Identificador único (UUID)                         | Auto        |
| **nome**                    | Identificador legível (ex: "Op. Carro Forte")      | Sim         |
| **descricao**               | Contexto/objetivo da hotlist (min 30 caracteres)   | Sim         |
| **dono**                    | Cliente Gabriel ou Gabriel interna (ID)            | Sim         |
| **ttl_dias**                | Tempo de vida das placas ativas em dias            | Sim         |
| **retencao_expiradas_dias** | Dias para manter placas expiradas antes de deletar | Sim         |
| **webhooks**                | Lista de URLs destino dos alertas                  | Sim (min 1) |
| **status**                  | ATIVA/INATIVA                                      | Sim         |
| **created_at**              | Data criação                                       | Auto        |
| **updated_at**              | Última modificação                                 | Auto        |

**Decisões de Design**:

- Descrição obrigatória (min 30 chars) - facilita indexação por LLM no futuro
- Múltiplos webhooks por hotlist (lista)
- Sem prioridade (todas processadas igual)
- Sem tags (simplificar MVP)
- TTL em dias
- Retenção de expiradas configurável por hotlist

---

### PLACA - Propriedades

| Propriedade    | Descrição                                   | Obrigatório |
| -------------- | ------------------------------------------- | ----------- |
| **placa**      | Número da placa (Mercosul/antigo)           | Sim         |
| **hotlist_id** | Vínculo com hotlist pai                     | Sim         |
| **status**     | ATIVA / EXPIRADA (calculado)                | Calculado   |
| **renewed_at** | Última renovação (timestamp para auditoria) | Auto        |
| **created_at** | Data adição (timestamp)                     | Auto        |
| **updated_at** | Última modificação (timestamp)              | Auto        |

**Modelo de expiração: TTL dinâmico + Jobs diários**

- `expires_at` = `renewed_at + hotlist.ttl_dias` (calculado, não persistido)
- `purge_at` = `expires_at + hotlist.retencao_expiradas_dias` (calculado, não persistido)
- Status calculado: ATIVA se `expires_at >= hoje`, senão EXPIRADA
- Timestamps com precisão de ms (auditoria), mas jobs operam com precisão de dias

**Jobs (meia-noite)**:

- Job de inativação: marca EXPIRADA placas onde `expires_at < hoje`
- Job de purge: deleta placas onde `purge_at < hoje`

**Decisões**:

- TTL é regra da hotlist (mudança afeta todas placas)
- Jobs diários dão janela de correção para erros de configuração
- Alertas continuam em tempo real (<30s)
- Renovação via API atualiza `renewed_at`
- Mesma placa pode estar em múltiplas hotlists
- `expires_at` e `purge_at` calculados, não persistidos

**Requisito de auditoria**: Deve existir auditoria de adição/deleção de placas. Definição de onde implementar (serviço core vs front-end) fica a cargo da engenharia durante execução.

---

### Política de Expiração e Deleção de Placas

**Status da placa**:

| Status       | Gera Alerta? | Visível? | Condição                             |
| ------------ | ------------ | -------- | ------------------------------------ |
| **ATIVA**    | Sim          | Sim      | `renewed_at + TTL >= hoje`           |
| **EXPIRADA** | Não          | Sim      | `renewed_at + TTL < hoje`            |
| **DELETADA** | N/A          | Não      | `renewed_at + TTL + retenção < hoje` |

**Ciclo de vida**:

```
ATIVA → EXPIRADA → DELETADA
         ↓
    (reativável via API - atualiza renewed_at)
```

**Jobs diários (meia-noite)**:

- **Inativação**: transiciona ATIVA → EXPIRADA
- **Purge**: deleta placas EXPIRADA após retenção configurada

## Escopo

### MVP (entrega urgente)

- API para criar/gerenciar hotlists (Gabriel opera)
- Descrição obrigatória (min 30 chars)
- TTL dinâmico como regra da hotlist (em dias)
- Jobs diários (meia-noite) para inativação e purge
- Retenção de expiradas configurável por hotlist
- Ciclo de vida: ATIVA → EXPIRADA → DELETADA
- Reativação de placas via API (atualiza renewed_at)
- Múltiplos webhooks por hotlist
- Alertas via webhook em tempo real (<30s)
- Dashboards de observabilidade
- Vínculo hotlist↔dono (Gabriel ou cliente)
- Auditoria de adição/deleção de placas

### Fora do MVP

- Interface gráfica para clientes
- Base específica de histórico de alertas (usa base existente)
- Gerenciamento de imagens (usa infra existente - S3 pré-assinado)

### Fase 2 (pós-validação)

- Portal web para gestão visual
- Canais adicionais (app, email, SMS)
- Abertura para operadores privados (modelo de cobrança)

---

## Análise Competitiva

| Aspecto               | Flock Safety / Axon / Motorola | Gabriel                    |
| --------------------- | ------------------------------ | -------------------------- |
| Hotlists customizadas | Sim                            | Sim (MVP)                  |
| Alertas tempo real    | Sim                            | Sim (MVP)                  |
| Múltiplos webhooks    | Varia                          | Sim (MVP)                  |
| Presença Brasil       | Não                            | **16K câmeras, 4 cidades** |

**Diferencial Gabriel**: Única rede LPR de escala no Brasil.

---

## Modelo de Negócio

| Usuário                           | Cobrança                  |
| --------------------------------- | ------------------------- |
| Gabriel (interno)                 | Sem custo                 |
| Operadores públicos (autoridades) | Sem custo                 |
| Operadores privados (B2B)         | Modelo a definir (fase 2) |

---

## Timeline

| Fase       | Entrega                          | Quando     |
| ---------- | -------------------------------- | ---------- |
| Discovery  | PRD aprovado                     | Semana 1   |
| Build      | API + webhooks funcionando       | Semana 2-5 |
| Beta       | Investigadores criminais Gabriel | Semana 6-7 |
| Lançamento | Produção                         | Semana 8   |

---

## Riscos

| Risco                        | Impacto                        | Mitigação                                           |
| ---------------------------- | ------------------------------ | --------------------------------------------------- |
| Alertas demoram >30s         | Perda de valor operacional     | Arquitetura event-driven, monitoramento de latência |
| Webhook destino indisponível | Alertas perdidos               | Retry com backoff, dead-letter queue, logs          |
| Falta de observabilidade     | Difícil diagnosticar problemas | Dashboards por funcionalidade, métricas desde início |

---

## Decisões Tomadas

| Decisão             | Escolha                          | Justificativa                       |
| ------------------- | -------------------------------- | ----------------------------------- |
| Operação            | Gabriel cria hotlists            | Não self-service no MVP             |
| Descrição           | Obrigatória, min 30 chars        | Facilita indexação LLM futuro       |
| TTL                 | Regra da hotlist em dias         | Mudança afeta todas placas          |
| Modelo expiração    | TTL dinâmico + jobs diários      | Janela de correção para erros       |
| Precisão            | Timestamps ms, jobs em dias      | Auditoria precisa, operação simples |
| expires_at/purge_at | Calculados                       | Não persistidos                     |
| renewed_at          | Persistido                       | Atualizado em renovação             |
| Retenção            | Configurável por hotlist         | Dias antes de hard delete           |
| Status placa        | ATIVA → EXPIRADA → DELETADA      | Ciclo claro                         |
| Reativação          | Via API                          | Atualiza renewed_at                 |
| Webhooks            | Múltiplos por hotlist            | Lista de URLs                       |
| Prioridade          | Não existe                       | Todas processadas igual             |
| Tags                | Não existe                       | Simplificar MVP                     |
| Placa multi-hotlist | Sim                              | Mesma placa em várias hotlists      |
| Auditoria           | Requisito                        | Definição técnica com eng           |
| Imagens             | URL S3 pré-assinada              | Padrão existente                    |
| Histórico alertas   | Base existente                   | Não escopo MVP                      |
| Piloto              | Investigadores criminais Gabriel | Usuários internos primeiro          |

---

## Referências

- [Flock Safety Hotlist](https://www.flocksafety.com/blog/what-happens-if-a-wanted-car-passes-by-a-flock-safety-camera)
- [Axon ALPR](https://www.axon.com/products/axon-fleet-3)
- [Motorola VehicleManager](https://www.motorolasolutions.com/en_us/video-security-access-control/license-plate-recognition-camera-systems/vehiclemanager-lpr-analytics-software.html)
