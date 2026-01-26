# PRD: Hotlist (Resumo)

**Autor**: Luiz Torres
**Data**: 2026-01-24
**Status**: Em Review
**Ticket**: -

> Ver [PRD completo](./hotlist.md) para detalhes técnicos e modelo de dados.

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
