# Regras de Ouro

As regras inegociáveis para o sistema funcionar.

**Responsável**: Comitê de Tecnologia

---

Para o sistema funcionar, precisamos de disciplina. Estas são as regras inegociáveis:

---

## 1. Nada existe fora do Linear

Se não está no Linear, não é trabalho no nível de esquadrão.

Qualquer demanda (do CPO, GPM, EM, cliente) deve se tornar uma `Issue` no board do time.

Não existe "só uma coisinha rápida" sem estar documentada.

---

## 2. O contrato é sagrado

Uma `Issue` é o contrato necessário para uma entrega e **não deve ser alterado no meio do Cycle** sem renegociação com o time.

Se surgir uma mudança de escopo:

- Criar uma Issue nova para a mudança
- Discutir com PM e time se entra na Sprint atual
- Se entrar, algo planejado precisa sair

---

## 3. Engenharia só puxa de "Pronto para Planejar"

Na Planning, o time **só** pode se comprometer com Issues que estão na coluna `Pronto para Planejar`.

Nada de planejar Issue mal detalhada.

Se uma Issue não está pronta:

- Não planeja
- Volta para a coluna apropriada (Detalhamento ou Refinamento)
- PM reprioriza o backlog

---

## 4. WIP Limit: 1 Issue e/ou Sub-Issue "Em Andamento" por pessoa

Para evitar gargalos e aumentar foco, cada engenheiro deve ter **no máximo**:

- **1 Issue** na coluna `Em Andamento`
- **E/OU 1 Sub-Issue** ativa por vez (se estiver trabalhando em Sub-Issues)

Isso não impede ter outras Issues em `Em Revisão` ou `Em Homologação`.

O objetivo é **"parar de começar e começar a terminar"**.

### Exemplos práticos:

✅ **OK:** Ana tem Issue A em "Em Andamento" + Issue B em "Em Revisão"
✅ **OK:** Carlos tem Sub-Issue X em andamento (da Issue principal em "Em Andamento")
❌ **NÃO:** Bruno tem Issue A em "Em Andamento" + Issue B em "Em Andamento"
❌ **NÃO:** Maria tem Sub-Issue X e Sub-Issue Y ambas em andamento ao mesmo tempo

### Por que WIP Limit funciona:

✅ **Foco:** Time termina uma coisa antes de começar outra
✅ **Colaboração:** Força pair programming e code reviews mais rápidos
✅ **Menos "quase pronto":** Maior visibilidade e cadência de entrega
✅ **Reduz carga cognitiva:** Menos troca de contexto

---

## 5. Status sempre atualizado - em tempo real

Cada engenheiro é **responsável por mover suas Issues** no board.

O Linear precisa refletir a realidade, **sempre**.

### ⚠️ Regras importantes:

> **NÃO espere a Daily para atualizar o status.**
>
> Atualize **em tempo real** conforme o trabalho avança:
>
> - Começou a trabalhar? → Move para "Em Andamento"
> - Abriu PR? → Move para "Em Revisão"
> - PR aprovado e mergeado? → Move para "Em Homologação"
> - PM validou? → Move para "Para Publicar"
> - Deploy feito? → Move para "Finalizada"

> **A Daily é para sincronizar, não para atualizar status.**
>
> Se você chegar na Daily e precisa atualizar 3 Issues, algo está errado.

**Estamos em processo de integração com o GitHub que automatizará parte do fluxo de Issues no Linear.**

### Por que isso é importante:

- **PM precisa saber** o status real para homologar
- **Time precisa saber** o que está travado para ajudar
- **Lideranças precisam saber** o progresso da Sprint
- **Métricas dependem** de status atualizados

---

## 6. Toda comunicação acontece na Issue

Conversas sobre uma Issue devem acontecer **nos comentários da própria Issue no Linear**.

Não usar Slack, email ou outras ferramentas para discussões sobre:

- Dúvidas de escopo
- Decisões técnicas
- Mudanças de abordagem
- Problemas encontrados
- Atualizações importantes

### Por quê?

✅ **Contexto centralizado:** Tudo que foi discutido fica documentado na Issue
✅ **Histórico completo:** Qualquer pessoa pode entender o que aconteceu
✅ **Notificações automáticas:** Pessoas tagueadas na Issue são notificadas
✅ **Busca futura:** Fácil encontrar decisões passadas

### Como usar:

**Use comentários na Issue para:**

- Fazer perguntas para PM sobre escopo
- Documentar decisões técnicas
- Avisar sobre bloqueios
- Compartilhar progresso ou descobertas
- Informar bloqueios ou dependências

**Use threads (respostas aos comentários) para:**

- Discussões mais longas
- Não poluir o feed principal da Issue

**Tagueie pessoas relevantes:**

- `@pessoa` notifica automaticamente
- PM, Líder do time, EM ou quem precisa saber

### ⚠️ Exceções (quando usar Slack):

- Daily (sincronização rápida do time)
- Questões urgentes que precisam resposta imediata
- Discussões gerais que não são sobre uma Issue específica

**Mas depois documente a decisão na Issue!**

**Estamos em processo de integração do Linear com o Slack para automatizar e manter as conversas nos dois lugares.**
