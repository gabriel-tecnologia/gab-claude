# Postmortem

Análise estruturada pós-incidente para entender causa raiz e evitar recorrência.

**Responsável**: _preencher_ | **Atualizado**: _preencher_

---

## Quando Fazer

| Severidade | Postmortem   | Outros gatilhos                                  |
| ---------- | ------------ | ------------------------------------------------ |
| P1         | Obrigatório  | Near miss, 3ª recorrência, pedido de stakeholder |
| P2         | Recomendado  |                                                  |
| P3/P4      | Opcional/Não |                                                  |

---

## Princípio Blameless

Foco em **sistemas**, não pessoas. Se alguém "errou", o sistema permitiu.

- ❌ "João não testou direito"
- ✅ "O deploy não exigia testes automatizados"

---

## Timeline do Processo

| Etapa                   | Prazo        | Responsável         |
| ----------------------- | ------------ | ------------------- |
| Documento inicial       | 48h          | Quem resolveu       |
| Reunião (opcional)      | 5 dias úteis | Engineering Manager |
| Action items concluídos | 2 sprints    | Squad               |

---

## Template de Postmortem

```markdown
# Postmortem: [Título]

**Data**: [YYYY-MM-DD] | **Duração**: [Xh] | **Severidade**: [P1/P2/P3] | **Autor**: [Nome]

## Resumo

[2-3 frases: o que aconteceu e impacto]

## Impacto

- Usuários afetados: [número/%]
- Funcionalidades: [lista]
- Duração: [tempo]

## Timeline

| Horário | Evento   |
| ------- | -------- |
| HH:MM   | [Evento] |

## Causa Raiz (5 Whys)

1. Por que caiu? →
2. Por que isso aconteceu? →
3. Por que foi possível? →
4. Por que não foi prevenido? →
5. Por que não detectado antes? →

## O que funcionou / O que falhou / Onde tivemos sorte

- [bullet points]

## Action Items

| Ação   | Prioridade | Responsável | Prazo  | Ticket  |
| ------ | ---------- | ----------- | ------ | ------- |
| [Ação] | Alta/Média | [Nome]      | [Data] | LIN-XXX |
```

---

## Reunião (1h)

**Participantes**: Engenheiros envolvidos, EM, PM (opcional)

| Tempo | Tópico                 |
| ----- | ---------------------- |
| 0-15  | Timeline               |
| 15-30 | Causa raiz             |
| 30-45 | O que funcionou/falhou |
| 45-60 | Action items           |

**Facilitação**: Fatos > opiniões. Interromper blame. Garantir participação.

---

## Action Items

**Bons Action Items são**: Específicos, mensuráveis, com dono e prazo.

| Prioridade | Critério            | Prazo     |
| ---------- | ------------------- | --------- |
| Alta       | Previne recorrência | 1 sprint  |
| Média      | Melhora detecção    | 2 sprints |

**Tracking**: Linear com label `postmortem`. Revisar em sprint planning.

---

## Compartilhamento (P1/P2)

- Resumo no #engenharia
- Arquivar em `./reports`
- **NÃO compartilhar**: detalhes que identifiquem "culpados", info sensível de segurança
