# Introdução e Filosofia Ágil

Entenda o "porquê" do nosso modelo ágil, os 4 pilares, e como Produto e Engenharia colaboram.

**Responsável**: Comitê de Tecnologia

---

## Sobre este Handbook

Este handbook define como trabalhamos na **área de tecnologia da Gabriel hoje**. Ele foi desenhado para o nosso contexto atual: uma startup em crescimento, com times pequenos, implementando estrutura pela primeira vez.

**É natural e esperado que este modelo evolua com o tempo**, conforme a empresa cresce, os times amadurecem e aprendemos na prática o que funciona e o que não funciona.

> 💡 Use as Retrospectivas para propor mudanças no processo. Nada aqui é imutável. O importante é ter clareza do modelo atual e evoluir de forma consciente.

---

## Os 4 Pilares do nosso modelo

### 🤝 PILAR 1 - Colaboração Diária

Produto e Engenharia trabalham juntos diariamente para refinar, construir e validar. Não existe "Produto demanda e Engenharia executa". Somos um time.

---

### ⏱️ PILAR 2 - Cadência e Foco (Scrumban)

- **Sprints de 2 semanas** para previsibilidade (Scrum)
- **WIP Limits** para forçar o time a "parar de começar e começar a terminar" (Kanban)
- **Resultado esperado:** entregamos mais rápido e com menos trabalho interrompido

---

### 👁️ PILAR 3 - Transparência e Valor

- **Trabalho 100%** visível no board
- **Sprint Demo** aberta para stakeholders para celebrar e comunicar valor entregue
- **Nada acontece fora do Linear**

---

### 📈 PILAR 4 - Melhoria Contínua

- **Retrospectivas** para melhorar o processo constantemente
- **Lideradas** por Engenharia (EM/Líder de time)
- **Processo é tratado como um produto:** sempre evoluindo

---

## Por que ágil?

Ágil é uma **mentalidade focada em aprender rápido e responder a mudanças**, em vez de seguir um plano rígido de longo prazo.

### O ciclo é simples:

1. **Planejar** ciclo pequeno
2. **Construir**
3. **Entregar**
4. **Aprender** - com o cliente e com o processo
5. **Adaptar** o plano para o próximo ciclo

Ágil é nossa ferramenta de gestão de risco: força validar ideias (de Produto) e otimizar execução (de Engenharia) em ciclos muito curtos.

---

## Modelo de Colaboração

### ❌ Como era (Modelo Antigo)

Produto dono e responsável por tudo. Engenharia apenas executava.

### ✅ Como é agora (Modelo Novo)

| Área           | Responsabilidade                       |
| -------------- | -------------------------------------- |
| **PRODUTO**    | Dono do **Problema** (O QUÊ e POR QUÊ) |
| **ENGENHARIA** | Dona da **Solução** (COMO e QUANTO)    |

Ambos colaboram diariamente. Decisões importantes são tomadas juntos. Responsabilidade compartilhada.

---

## Níveis de Atuação

Produto e Engenharia têm diferentes níveis de foco dependendo do cargo:

### 👔 PRODUTO

| Cargo          | Operacional (squad) | Tático (tribo) | Estratégico (área) |
| -------------- | ------------------- | -------------- | ------------------ |
| **PM**         | Predominante        | Forte          | Apoio              |
| **GPM**        | Apoio               | Predominante   | Forte              |
| **Head / CPO** | Pontual             | Apoio          | Predominante       |

### 👨‍💻 ENGENHARIA

| Cargo                | Operacional (squad) | Tático (tribo) | Estratégico (área) |
| -------------------- | ------------------- | -------------- | ------------------ |
| **Engenheiro JR/PL** | Predominante        | Apoio          | Nenhum             |
| **Engenheiro SR**    | Predominante        | Forte          | Apoio              |
| **Staff Engineer**   | Forte               | Predominante   | Apoio              |
| **EM**               | Apoio               | Predominante   | Forte              |
| **Head / CTO**       | Pontual             | Apoio          | Predominante       |

---

### O que significa cada nível?

#### 🔧 OPERACIONAL (Squad/Time)

- Dia-a-dia da squad
- Execução de Issues
- Rituais de Sprint (Daily, Planning, Retro)
- **Exemplo:** Desenvolver features, revisar código, participar de refinamentos

#### 🎯 TÁTICO (Tribo)

- Planejamento de médio prazo da tribo
- Roadmap da Tribo (trimestral)
- Decisões de arquitetura/produto que impactam a tribo
- **Exemplo:** Priorizar épicos, definir OKRs da tribo, decisões make/buy

#### 🚀 ESTRATÉGICO (Área de Tecnologia)

- Visão de longo prazo que transcende tribos
- Roadmaps de Produto e Técnico da empresa
- OKRs da área de tecnologia
- Decisões que afetam múltiplas tribos
- **Exemplo:** Visão de produto para o próximo ano, mudanças de stack tecnológico

---

## Produto vs Engenharia: Responsabilidades

### Visão Geral

| **PRODUTO** (Dono do Problema) | **ENGENHARIA** (Dona da Solução) |
| ------------------------------ | -------------------------------- |
| Foco: **O QUÊ** e **POR QUÊ**  | Foco: **COMO** e **QUANTO**      |

### Responsabilidades Detalhadas

| Área              | PRODUTO                                                    | ENGENHARIA                                                                         |
| ----------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **Visão**         | Define a Visão de produto e OKRs de Negócio/Produto        | Define a Visão Técnica e OKRs de Engenharia                                        |
| **Roadmap**       | Dono do Roadmap de Produto (o que resolver para o cliente) | Dona do Roadmap Técnico (arquitetura, débitos, ferramentas)                        |
| **Identificação** | Identifica o que resolver para o cliente                   | Identifica o que resolver na arquitetura e infraestrutura                          |
| **Priorização**   | Gerencia a Priorização do backlog de produto               | Gerencia a Capacidade e o Backlog Técnico                                          |
| **Garantia**      | Garante que o time está construindo **a coisa certa**      | Garante que o time está construindo **da forma certa** (qualidade, escalabilidade) |
| **Processo**      | Dono do processo de **Discovery**                          | Dona do processo de **Delivery**                                                   |
| **Facilitação**   | Facilita rituais de Produto                                | Facilita rituais de Engenharia e do Processo                                       |
