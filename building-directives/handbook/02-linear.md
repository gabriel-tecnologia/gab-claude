# Estrutura do Linear

Aprenda a hierarquia (Initiative → Project → Issue → Sub-Issue), tipos de Issues, e como usar prioridades.

**Responsável**: Comitê de Tecnologia

---

O Linear é a fotografia de como trabalhamos as Iniciativas Estratégicas e o reflexo do nosso dia-a-dia. Ele deve ser a nossa **única fonte da verdade** sobre o processo de desenvolvimento e entrega de Produto.

---

## Hierarquia

Como usamos a estrutura do Linear, de cima para baixo:

---

## 1️⃣ INITIATIVE (Iniciativa Estratégica)

### O que é

Representa uma **Iniciativa Estratégica** - bloco de épicos que atuam em conjunto para os objetivos da área de Tecnologia.

### Características

- É o item de mais alto nível
- Pode ser **trimestral, semestral ou anual**
- São criadas por GPM e EM
- Contém 1 ou mais Épicos
- **Exemplo:** "Aumentar retenção de clientes em 20%", "Tornar-se líder em X mercado", "Lançamento do Camaleão 3"

---

## 2️⃣ PROJECT (Épico)

### O que é

Representa um **Épico** - uma grande feature ou objetivo que levará semanas/meses para ser construído.

### Características

- **É o desdobramento tático de uma Iniciativa Estratégica** - o que vamos construir para atingir determinado objetivo
- Um **Épico de Produto** deve sempre estar associado a uma Iniciativa
- Pode existir **Épico de Engenharia** sem associação a uma Iniciativa
- Deve ser concluído, preferencialmente, **em um trimestre**
- **Exemplo:** "Sistema de notificações push", "Refatoração da API de pagamentos"

---

## 3️⃣ ISSUE (História)

### O que é

Representa uma **unidade de trabalho** - um contrato necessário para uma entrega.

### Características

- Pode ser: **História de Usuário, História Técnica, Spike ou Bug**
- Deve ser concluída **em até uma Sprint (2 semanas)**
- Contém critérios de aceite claros
- **Exemplo:** "Como usuário, quero receber notificação quando meu camaleão for utilizado em uma ocorrência", "Migrar banco de dados para PostgreSQL 15"

---

## 4️⃣ SUB-ISSUE (Tarefa)

### O que é

Representa uma tarefa dentro de uma **Issue** - é o plano de execução técnico.

### Características

- É o passo-a-passo de **COMO** entregar uma Issue
- **Deve sempre estar conectada a uma Issue**
- Permite visualizar o progresso da Issue principal
- Tamanho flexível: bloco de entregas que faça sentido para o time

### Como as Sub-Issues funcionam

**Quebra e execução:**

- Quebre a Issue em passos executáveis (blocos de entregas que façam sentido)
- Cada Sub-Issue concluída é movida para **"Finalizada"**
- O progresso da Issue principal é calculado automaticamente
  - Exemplo: 3 de 5 Sub-Issues finalizadas = 60% de progresso

**Fluxo diferente:**

- **Sub-Issues** são finalizadas individualmente conforme são concluídas
- **A Issue principal** passa pelo fluxo completo:
  - Em Andamento → Em Revisão → Em Homologação → Para Publicar → Finalizada

### Exemplo prático

**Issue:** "Implementar notificações por email"

- ✅ Sub-Issue 1: Configurar Sendgrid → **Finalizada**
- ✅ Sub-Issue 2: Criar template de email → **Finalizada**
- ⏳ Sub-Issue 3: Implementar fila de envio → **Em Andamento**
- ⬜ Sub-Issue 4: Adicionar testes unitários → **Não iniciada**

**Status da Issue principal:** "Em Andamento" (50% completa - 2 de 4 Sub-Issues finalizadas)

Quando todas Sub-Issues estiverem finalizadas, a Issue vai para "Em Revisão" - caso ainda tenha code review; ou "Em Homologação", etc.

---

## 5️⃣ CYCLE (Sprint)

### O que é

Representa a **Sprint** de 2 semanas.

### Características

- Ciclo de desenvolvimento para planejar e executar entregas de forma previsível
- Tem data de início e fim fixas
- Time se compromete com um conjunto de Issues no início
- **Exemplo:** "Sprint 15 - 02/Dez a 15/Dez"

---

## Tipos de Issues

Para organizar nosso trabalho, classificamos cada `Issue` por tipo, utilizando as "Labels Demandas" disponíveis no Linear.

### Tabela de Tipos (labels Demandas)

| Tipo                                    | Quando usar                                                                                                         | Deve ter Épico?                                  |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| **História de Usuário**                 | Funcionalidade com valor direto para o usuário final. Foco no problema do usuário, não na solução técnica.          | ✅ Sempre                                        |
| **História Técnica Habilitadora**       | Trabalho técnico necessário para viabilizar uma feature.                                                            | ✅ Sim, o mesmo da feature que será viabilizada. |
| **História Técnica (Saúde do Sistema)** | Débito técnico, refatoração, performance, segurança, evolução arquitetural. Não vinculada a uma feature específica. | ❌ Opcional                                      |
| **Spike**                               | Investigação/estudo técnica ou de produto com time-box definido. Resultado é conhecimento, não código em produção.  | ❌ Opcional                                      |
| **Bug**                                 | Correção de comportamento incorreto em produção ou staging.                                                         | ❌ Não                                           |

---

## Prioridades

Use prioridades no Linear para sinalizar urgência:

| Prioridade    | Quando usar                                                         |
| ------------- | ------------------------------------------------------------------- |
| 🔴 **Urgent** | Bloqueia produção ou usuários. Precisa ser resolvido imediatamente. |
| 🟠 **High**   | Importante para o objetivo da Sprint. Deve ser priorizado.          |
| 🟡 **Medium** | Relevante mas pode esperar se necessário.                           |
| 🟢 **Low**    | Melhoria incremental. Fazer quando houver capacidade.               |

> ⚠️ **Importante:** Se tudo é urgente, nada é urgente. Use "Urgent" apenas para **situações realmente críticas**.
