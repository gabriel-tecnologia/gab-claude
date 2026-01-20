# Severidade de Incidentes

**Responsável**: Líder da Engenharia | **Atualizado**: _preencher_

---

## Níveis

| Nível  | Definição                                       | Exemplos                                   | Resposta                        | Postmortem  |
| ------ | ----------------------------------------------- | ------------------------------------------ | ------------------------------- | ----------- |
| **P1** | Sistema fora do ar ou core inacessível p/ todos | App não abre, API 500, perda dados, breach | 15min, EM + Sr Eng, #engenharia | Obrigatório |
| **P2** | Core degradado/indisponível p/ parte            | Login falha 30%, pagamentos intermitentes  | 1h, EM + Sr Eng, #incidents     | Recomendado |
| **P3** | Bug com workaround disponível                   | Feature secundária quebrada, edge cases    | 4h (comercial), Sr Eng          | Opcional    |
| **P4** | Bug menor, não impacta operação                 | Typo, inconsistência menor                 | Próximo sprint, backlog         | Não         |

---

## Como Classificar

|                 | Core | Não-Core |
| --------------- | ---- | -------- |
| Todos afetados  | P1   | P2       |
| Muitos afetados | P2   | P3       |
| Poucos afetados | P3   | P4       |

**Regra**: Perda de dados ou risco de segurança → P1 automático. Na dúvida → assume maior.

---

## Escalation

| Situação                   | Ação               |
| -------------------------- | ------------------ |
| P1 sem resolução em 30 min | → CPTO             |
| P2 sem resolução em 2h     | → Tech Lead sênior |
| Múltiplos times            | → Coordenação      |

---

## Templates de Comunicação

```
🔴 INCIDENTE P[X] - [Título]
Status: Investigando | Impacto: [descrição] | Início: [hora]

🟡 UPDATE - Status: [Investigando/Mitigando] | Progresso: [...] | ETA: [...]

🟢 RESOLVIDO - Duração: [Xh] | Causa: [...] | Postmortem: [link]
```
