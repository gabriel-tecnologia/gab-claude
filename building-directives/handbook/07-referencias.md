# Referências

Guias rápidos, glossário e FAQ.

**Responsável**: Comitê de Tecnologia

---

## Guia de Consulta Rápida

### Fluxo de uma Issue do início ao fim

**Exemplo:** Nova feature de notificações por email

---

### Semana -2 (Upstream - Discovery):

**Segunda:**
PM cria Issue "Como usuário, quero receber email quando alguém comentar no meu post" em `Ideia`

**Terça:**
PM detalha a Issue, escreve critérios de aceite → move para `Refinamento Geral`

**Quarta (Refinamento Geral):**
PM apresenta, PD mostra design do email, time entende → PM move para `Refinamento Técnico`

**Quinta (Refinamento Técnico):**
Time debate arquitetura, quebra em 3 Sub-Issues, estima em 8 pontos → move para `Pronto para Planejar`

---

### Semana -1 (Planning):

**Segunda (Sprint Planning):**
Time puxa a Issue para o Cycle 15 → status `Planejado`

> 💡 Issue ainda não tem assigned. Time vai se organizar e definir quem pega quando for começar.

---

### Semana 1-2 (Execução):

**Terça S1:**
Engenheira Ana pega a Issue (agora fica assigned para ela), muda para `Em Andamento`, começa primeira Sub-Issue

**Daily:**
Ana atualiza time sobre progresso (mas já tinha movido a Issue antes da Daily!)

**Quinta S1:**
Ana termina código, abre PR, **imediatamente** move Issue para `Em Revisão` (não espera a Daily)

**Sexta S1:**
Engenheiro Bruno faz code review, aprova, Ana mergeia PR → **imediatamente** move para `Em Homologação`

**Segunda S2:**
PM testa no Staging, encontra bug pequeno → volta para `Em Andamento`

**Terça S2:**
Ana corrige bug, reabre PR, Bruno aprova → volta para `Em Homologação`

**Quarta S2:**
PM valida novamente, aprova → move para `Para Publicar`

**Quinta S2:**
Time faz deploy para produção → `Finalizada` ✅

**Sexta S2 (Sprint Demo):**
PM demonstra a feature funcionando em produção

---

## Glossário

**Backlog:** Lista priorizada de Issues aguardando para serem trabalhadas.

**Bug:** Defeito no software que causa comportamento incorreto.

**Critérios de Aceite:** Lista de condições que uma Issue deve atender para ser considerada pronta. Geralmente no formato "Dado que... quando... então...".

**Cycle (Ciclo/Sprint):** Período fixo de 2 semanas onde o time trabalha em um conjunto de Issues planejadas.

**Cycle Time:** Tempo que uma Issue leva de "Em Andamento" até "Finalizada".

**Daily (Stand-up):** Reunião diária de 15 minutos para sincronizar o time.

**Definition of Done (DoD):** Checklist que define quando uma Issue está 100% pronta para ir para produção.

**Definition of Ready (DoR):** Checklist que define quando uma Issue está 100% pronta para ser planejada.

**Deploy:** Processo de colocar código em produção, disponível para usuários finais.

**Delivery:** Fase de execução onde o time constrói e entrega Issues.

**Discovery:** Fase de exploração onde Produto define o que construir e por quê.

**Épico (Project):** Grande funcionalidade ou objetivo que leva semanas/meses para ser construído. Composto por várias Issues.

**História de Usuário (User Story):** Issue que descreve funcionalidade do ponto de vista do usuário final. Formato: "Como [usuário], quero [ação], para [benefício]".

**História Técnica:** Issue que descreve trabalho técnico necessário (pode habilitar features ou melhorar saúde do sistema).

**Iniciativa (Initiative):** Objetivo estratégico de alto nível, geralmente trimestral/semestral/anual.

**Issue:** Unidade de trabalho. Pode ser História de Usuário, História Técnica, Spike ou Bug.

**Kanban:** Metodologia ágil focada em fluxo contínuo e limites de trabalho em progresso (WIP Limits).

**Lead Time:** Tempo que uma Issue leva de "Ideia" até "Finalizada".

**Planning (Planejamento de Sprint):** Ritual onde o time decide o que vai trabalhar na Sprint.

**Planning Poker:** Técnica de estimativa colaborativa usando Story Points.

**Pull Request (PR):** Proposta de alteração de código que passa por revisão antes de ser integrada.

**Refinamento:** Ritual onde o time discute e amadurece Issues antes da Planning.

**Retrospectiva (Retro):** Ritual onde o time reflete sobre o processo e define melhorias.

**Scrum:** Framework ágil baseado em Sprints de tempo fixo.

**Scrumban:** Híbrido de Scrum e Kanban (Sprints + WIP Limits).

**Spike:** Issue de investigação com time-box definido. Resultado é conhecimento, não código em produção.

**Sprint:** Ver Cycle.

**Sprint Demo:** Ritual onde o time demonstra o valor entregue na Sprint para stakeholders.

**Staging:** Ambiente de testes que imita produção, usado para validação final antes do deploy.

**Story Points:** Unidade de medida relativa de complexidade/esforço de uma Issue (não são horas). Na Gabriel, usamos a escala Fibonacci: 1, 2, 3, 5, 8.

**Sub-Issue:** Tarefa técnica dentro de uma Issue. Representa o plano de execução passo-a-passo.

**Velocity:** Média de Story Points que o time entrega por Sprint. Usado para estimar capacidade.

**WIP Limit (Work In Progress Limit):** Limite máximo de Issues que podem estar em uma coluna ao mesmo tempo. No nosso caso: 1 Issue e/ou Sub-Issue por pessoa em "Em Andamento".

---

## FAQ (Perguntas Frequentes)

### Sobre Issues e Planejamento

**Q: E se uma Issue urgente surgir no meio da Sprint?**

**A:** Avaliar com PM e Líder de Engenharia. Se for realmente urgente (ex: bug crítico em produção), pode entrar. MAS: algo planejado precisa sair da Sprint para manter o compromisso original. Renegociar com o time.

---

**Q: Posso trabalhar em algo que não está no Cycle?**

**A:** Não. Todo trabalho deve estar no Linear e planejado. Se surgiu algo, crie uma Issue e discuta a prioridade com PM.

---

**Q: O que acontece se não entregarmos tudo que foi planejado?**

**A:** Não é o fim do mundo. Issues não concluídas voltam para `Pronto para Planejar` (se não começaram) ou continuam para a próxima Sprint (se já começaram). Na Retro, discutimos o porquê e aprendemos para melhorar.

---

**Q: Como lidar com bugs encontrados durante a Sprint?**

**A:**

- **Bugs em Issues da Sprint atual:** corrigir antes de mover para `Finalizada`
- **Bugs em funcionalidades antigas:** criar Issue nova com tipo `Bug` e priorizar no backlog

---

**Q: Issues planejadas ficam assigned para alguém?**

**A:** Não. Quando uma Issue vai para `Planejado`, ela não tem assigned. O time se organiza e só estabelece um responsável quando alguém pega a Issue e move para `Em Andamento`.

---

### Sobre Refinamento

**Q: Posso pular o Refinamento Técnico se a Issue for "simples"?**

**A:** Não recomendado. Mesmo Issues simples se beneficiam do debate do time. Mas se for MUITO simples (ex: correção de typo), o Líder do Time pode aprovar que vá direto para `Pronto para Planejar`.

---

**Q: Quando EM deve participar dos Refinamentos?**

**A:** EM participa quando:

- Issue tem complexidade técnica alta que precisa de visão estratégica
- Precisa de alinhamento sobre decisões de arquitetura
- Há conflito de priorização que precisa mediação
- Decisões que impactam múltiplas squads

---

### Sobre Sub-Issues

**Q: Sub-Issues são obrigatórias?**

**A:** Para Issues de desenvolvimento (Histórias de Usuário e Técnicas), sim. Sub-Issues são o plano de execução. Para Bugs muito pequenos, podem ser opcionais.

---

**Q: Qual o tamanho ideal de uma Sub-Issue?**

**A:** Flexível - um bloco de entregas que faça sentido para o time. Não precisa ser "< 1 dia". O importante é que seja executável e claro o que precisa ser feito.

---

### Sobre Estimativas

**Q: Como aprender a estimar melhor?**

**A:** Com o tempo. Nas primeiras Sprints, errem à vontade. Depois da Sprint, comparem: estimamos 5 pontos, entregamos em quanto tempo real? Isso calibra o time.

---

**Q: O que fazer quando há divergência grande no Planning Poker?**

**A:** Quem votou o número maior e o menor explicam seu raciocínio. Time discute e vota novamente. Se continuar divergindo, pode ser sinal de que a Issue não está clara o suficiente.

---

### Sobre Processo

**Q: O que fazer quando PM e Engenharia discordam sobre prioridade?**

**A:** Escalar para GPM e EM. PM é dono da priorização de features, mas EM tem autonomia sobre itens técnicos críticos (ex: débito que pode causar incidente).

---

**Q: Esqueci de mover uma Issue no Linear. Posso atualizar depois?**

**A:** Sim, mas atualize **assim que lembrar**. Não espere a próxima Daily. O ideal é criar o hábito de mover em tempo real.

---

**Q: Onde devo fazer perguntas sobre uma Issue?**

**A:** Nos **comentários da própria Issue no Linear**. Não use Slack para discussões sobre Issues. Isso mantém o contexto centralizado e o histórico completo.

---

**Q: Como sei se devo usar Slack ou Linear para comunicação?**

**A:**

**Use Linear (comentários na Issue):**

- Dúvidas sobre escopo
- Decisões técnicas
- Problemas encontrados
- Qualquer coisa relacionada à Issue específica

**Use Slack:**

- Daily (sincronização rápida)
- Urgências que precisam resposta imediata
- Discussões gerais não relacionadas a uma Issue

---

## Feedback

Este é um documento vivo. Se algo não está claro ou pode melhorar, traga na próxima Retrospectiva ou fale com sua gestão direta.
