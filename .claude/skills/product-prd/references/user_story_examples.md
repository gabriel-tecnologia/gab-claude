# Exemplos de User Stories & Melhores Práticas

Um guia abrangente para escrever user stories eficazes com exemplos do mundo real em diferentes domínios.

---

## Índice

1. [Formato de User Story](#formato-de-user-story)
2. [Anatomia de Boas User Stories](#anatomia-de-boas-user-stories)
3. [Exemplos por Domínio](#exemplos-por-domínio)
4. [Padrões de Critérios de Aceitação](#padrões-de-critérios-de-aceitação)
5. [Erros Comuns](#erros-comuns)
6. [Divisão de Stories](#divisão-de-stories)

---

## Formato de User Story

### Template Padrão

Aqui está o template padrão para nossas user stories

```
# User Story: [Nome da US]

> **Produto:** [nome do produto]
> **Autor:** [Nome]
> **Criado em:** YYYY-MM-DD
> **Status:** Draft | Under Review | Approved | In Development | Delivered

---

## 1. Descrição do Problema

Contextualize o problema de negócio ou técnico que esta story resolve. Seja específico sobre o impacto atual (ex: taxa de erro, tempo perdido, reclamações) e o cenário desejado após implementação.

## 2. Caso de Uso

Descreva uma situação real ou representativa de um usuário enfrentando o pain point. Inclua: quem é o usuário, o que ele estava tentando fazer, o que deu errado, e como isso o afetou. Isso humaniza o problema e alinha o time na motivação.

## 3. Definition of Ready (DoR)

Estes critérios tendem a não mudar. São checkboxes para garantir que a story está pronta para desenvolvimento.

- [ ] Requisitos claros e sem ambiguidade
- [ ] Protótipos/wireframes aprovados (se aplicável)
- [ ] Critérios de aceitação definidos e validados com stakeholders
- [ ] Estimativa de esforço completada pelo time

## 4. Critérios de Aceitação

Expectativas específicas que definem o comportamento correto da feature, escritas da perspectiva do usuário. Aqui, definimos o que determina que a tarefa está completa.

- [ ] Dado [contexto inicial], quando [ação do usuário], então [resultado esperado]
- [ ] Cenários de erro e edge cases cobertos
- [ ] Requisitos de performance (se aplicável)

## 5. Definition of Done (DoD)

Estes critérios tendem a não mudar. São checkboxes para garantir que a story está verdadeiramente completa em todas suas dimensões, não apenas na escrita do código:

- [ ] Código revisado (code review aprovado)
- [ ] Testes automatizados implementados (unit/integration)
- [ ] Documentação atualizada (API, README, Notion)
- [ ] Deploy em ambiente de staging validado
- [ ] Stakeholders da story notificados / release notes escritas

```

---

## Anatomia de Boas User Stories

### Critérios INVEST

Boas user stories são:

- **Independent:** Podem ser desenvolvidas e entregues separadamente
- **Negotiable:** Detalhes podem ser discutidos e ajustados
- **Valuable:** Entregam valor claro para usuários ou negócio
- **Estimable:** Podem ser dimensionadas/estimadas pelo time
- **Small:** Podem ser completadas em uma iteração/sprint
- **Testable:** Têm critérios de aceitação claros

### Componentes Chave

1. **Tipo de Usuário:** Quem é o usuário? Seja específico.
2. **Ação:** O que eles querem fazer? Uma ação clara.
3. **Valor:** Por que eles querem isso? O benefício ou resultado.
4. **Critérios de Aceitação:** Como sabemos que está pronto? Condições testáveis.

---

## Exemplos por Domínio

### E-Commerce

#### Exemplo 1: Busca de Produto

**User Story:**
```
Como comprador online,
Quero filtrar produtos por faixa de preço,
Para que eu possa encontrar itens dentro do meu orçamento.
```

**Critérios de Aceitação:**
- [ ] Dado que estou na página de listagem de produtos, quando defino um preço mínimo e máximo, então apenas produtos dentro dessa faixa são exibidos
- [ ] Dado que apliquei um filtro de preço, quando limpo o filtro, então todos os produtos são mostrados novamente
- [ ] Dado que defino uma faixa de preço inválida (min > max), quando aplico o filtro, então vejo uma mensagem de erro
- [ ] Filtro de preço persiste quando navego entre páginas de resultados
- [ ] Filtro exibe contagem de produtos correspondentes aos critérios

**Prioridade:** Alta

---

#### Exemplo 2: Checkout como Convidado

**User Story:**
```
Como cliente de primeira vez,
Quero fazer checkout sem criar uma conta,
Para que eu possa completar minha compra rapidamente.
```

**Critérios de Aceitação:**
- [ ] Dado que tenho itens no carrinho, quando clico em checkout, então vejo opções para "Checkout como Convidado" e "Entrar"
- [ ] Dado que escolho checkout como convidado, quando insiro informações de envio e pagamento, então posso completar o pedido
- [ ] Dado que completo um checkout como convidado, quando o pedido é feito, então recebo um email de confirmação
- [ ] Após checkout como convidado, vejo uma opção para criar uma conta com minhas informações do pedido
- [ ] Fluxo de checkout como convidado leva no máximo 3 telas

**Prioridade:** Alta

---

### SaaS / Plataforma B2B

#### Exemplo 3: Colaboração em Time

**User Story:**
```
Como gerente de projeto,
Quero atribuir tarefas a membros do time,
Para que todos saibam suas responsabilidades.
```

**Critérios de Aceitação:**
- [ ] Dado que estou visualizando uma tarefa, quando clico em "Atribuir", então vejo uma lista de membros do time
- [ ] Dado que seleciono um membro do time, quando confirmo a atribuição, então ele recebe uma notificação
- [ ] Dado que uma tarefa está atribuída, quando visualizo a lista de tarefas, então posso ver quem está atribuído a cada tarefa
- [ ] Dado que sou um membro do time, quando sou atribuído a uma tarefa, então ela aparece na minha visualização "Minhas Tarefas"
- [ ] Posso atribuir múltiplas pessoas a uma única tarefa
- [ ] Posso mudar ou remover atribuições de tarefas

**Prioridade:** Alta

---

#### Exemplo 4: Analytics de Uso

**User Story:**
```
Como administrador SaaS,
Quero visualizar analytics de uso do time,
Para que eu possa otimizar nosso plano de assinatura.
```

**Critérios de Aceitação:**
- [ ] Dado que tenho permissões de admin, quando navego para analytics, então vejo métricas de uso dos últimos 30 dias
- [ ] Dashboard mostra: usuários ativos, uso de features, chamadas de API, e storage usado
- [ ] Dado que seleciono um intervalo de datas, quando aplico o filtro, então métricas atualizam conforme
- [ ] Posso exportar dados de analytics como CSV
- [ ] Métricas atualizam em tempo real (máximo 5 minutos de delay)

**Prioridade:** Alta

---

### App Mobile

#### Exemplo 5: Push Notifications

**User Story:**
```
Como usuário de app mobile,
Quero customizar quais notificações recebo,
Para que eu veja apenas atualizações relevantes.
```

**Critérios de Aceitação:**
- [ ] Dado que estou nas configurações, quando navego para notificações, então vejo toggles para cada tipo de notificação
- [ ] Tipos de notificação incluem: mensagens, menções, atualizações, promoções
- [ ] Dado que desabilito um tipo de notificação, quando esse evento ocorre, então não recebo uma push notification
- [ ] Configurações sincronizam entre dispositivos usando a mesma conta
- [ ] Configurações padrão são: mensagens ON, menções ON, atualizações ON, promoções OFF

**Prioridade:** Alta

---

#### Exemplo 6: Modo Offline

**User Story:**
```
Como usuário mobile com conectividade instável,
Quero acessar meu conteúdo visualizado recentemente offline,
Para que eu possa continuar usando o app sem internet.
```

**Critérios de Aceitação:**
- [ ] Dado que visualizei conteúdo enquanto online, quando fico offline, então ainda posso acessar os últimos 50 itens visualizados
- [ ] Dado que estou offline, quando tento acessar novo conteúdo, então vejo uma mensagem "Sem conexão" com conteúdo em cache
- [ ] Dado que estou offline e faço alterações, quando reconecto, então alterações sincronizam automaticamente
- [ ] Indicador de offline aparece no app quando conectividade é perdida
- [ ] Conteúdo em cache é automaticamente limpo após 7 dias

**Prioridade:** Alta

---

### Autenticação & Segurança

#### Exemplo 7: Autenticação de Dois Fatores

**User Story:**
```
Como usuário consciente de segurança,
Quero habilitar autenticação de dois fatores,
Para que minha conta seja protegida de acesso não autorizado.
```

**Critérios de Aceitação:**
- [ ] Dado que estou nas configurações de segurança, quando habilito 2FA, então posso escolher entre SMS e app autenticador
- [ ] Dado que escolho app autenticador, quando escaneio o QR code, então devo inserir um código de verificação para ativar
- [ ] Dado que 2FA está habilitado, quando faço login, então sou solicitado pelo meu segundo fator
- [ ] Recebo códigos de backup quando ativo 2FA
- [ ] Posso desabilitar 2FA com minha senha atual + código 2FA

**Prioridade:** Alta

---

#### Exemplo 8: Reset de Senha

**User Story:**
```
Como usuário que esqueceu minha senha,
Quero resetá-la via email,
Para que eu possa recuperar acesso à minha conta.
```

**Critérios de Aceitação:**
- [ ] Dado que clico em "Esqueci Senha", quando insiro meu email, então recebo um link de reset em até 5 minutos
- [ ] Link de reset expira após 24 horas
- [ ] Dado que clico no link de reset, quando insiro uma nova senha, então ela deve atender aos requisitos de senha (mostrados na tela)
- [ ] Após reset bem-sucedido, sou logado automaticamente
- [ ] Se email não existe no sistema, mostrar mensagem genérica (não revelar se conta existe)

**Prioridade:** Alta

---

### Conteúdo & Mídia

#### Exemplo 9: Upload de Vídeo

**User Story:**
```
Como criador de conteúdo,
Quero fazer upload de vídeos com acompanhamento de progresso,
Para que eu saiba quando meu upload está completo.
```

**Critérios de Aceitação:**
- [ ] Dado que seleciono um arquivo de vídeo, quando clico em upload, então vejo uma barra de progresso mostrando porcentagem completa
- [ ] Formatos suportados: MP4, MOV, AVI (máx 2GB)
- [ ] Dado que upload está em progresso, quando navego para fora, então upload continua em background
- [ ] Dado que upload completa, quando processamento termina, então recebo uma notificação
- [ ] Dado que upload falha, quando erro ocorre, então vejo mensagem de erro específica e posso tentar novamente

**Prioridade:** Alta

---

### Admin & Configuração

#### Exemplo 10: Permissões de Usuário

**User Story:**
```
Como administrador,
Quero atribuir permissões baseadas em role a usuários,
Para que membros do time tenham níveis de acesso apropriados.
```

**Critérios de Aceitação:**
- [ ] Dado que estou visualizando um perfil de usuário, quando clico em "Mudar Role", então vejo roles disponíveis: Admin, Editor, Viewer
- [ ] Dado que atribuo uma role, quando salvo, então usuário imediatamente ganha/perde permissões associadas
- [ ] Admin: acesso total; Editor: criar/editar conteúdo; Viewer: somente leitura
- [ ] Posso criar roles customizadas com combinações específicas de permissões
- [ ] Audit log registra todas as mudanças de permissão com timestamp e admin que fez a mudança

**Prioridade:** Alta

---

## Padrões de Critérios de Aceitação

### Formato Given-When-Then

Formato mais estruturado, excelente para lógica complexa:

```
Dado [contexto/estado inicial],
Quando [ação/evento],
Então [resultado esperado].
```

**Exemplo:**
```
Dado que sou um usuário logado com itens no meu carrinho,
Quando aplico um código de desconto de 20%,
Então o total do carrinho é reduzido em 20% e exibe o desconto.
```

### Formato Checklist

Mais simples, bom para requisitos diretos:

```
- [ ] Requisito 1
- [ ] Requisito 2
- [ ] Tratamento de edge case
```

### Formato Tabela

Ótimo para múltiplos cenários:

| Condição | Ação | Resultado Esperado |
|----------|------|-------------------|
| Email válido | Clicar "Enviar" | Mensagem de confirmação |
| Email inválido | Clicar "Enviar" | Mensagem de erro |
| Campo vazio | Clicar "Enviar" | Erro "Campo obrigatório" |

---

## Erros Comuns a Evitar

### ❌ Muito Técnico

**Ruim:**
```
Como usuário,
Quero que o sistema use cache Redis com TTL de 10 minutos,
Para que carregamentos de página sejam rápidos.
```

**Bom:**
```
Como usuário,
Quero que páginas carreguem em menos de 2 segundos,
Para que eu possa navegar eficientemente.
```

**Por quê:** User stories focam em valor do usuário, não implementação. Deixe engenheiros escolherem a solução.

---

### ❌ Muito Vago

**Ruim:**
```
Como usuário,
Quero que o app seja rápido,
Para que eu tenha uma boa experiência.
```

**Bom:**
```
Como usuário,
Quero que resultados de busca apareçam em menos de 1 segundo,
Para que eu possa rapidamente encontrar o que preciso.
```

**Por quê:** "Rápido" é subjetivo. Seja específico e mensurável.

---

### ❌ Faltando o "Por Quê"

**Ruim:**
```
Como usuário,
Quero fazer upload de fotos de perfil.
```

**Bom:**
```
Como usuário,
Quero fazer upload de uma foto de perfil,
Para que outros usuários possam me reconhecer na comunidade.
```

**Por quê:** Entender o "por quê" ajuda o time a tomar melhores decisões.

---

### ❌ Múltiplas Ações em Uma Story

**Ruim:**
```
Como usuário,
Quero criar uma conta, configurar meu perfil e convidar membros do time,
Para que eu possa começar a usar a plataforma.
```

**Bom:** Divida em três stories:
```
Story 1: Como usuário, quero criar uma conta...
Story 2: Como usuário, quero configurar meu perfil...
Story 3: Como dono de conta, quero convidar membros do time...
```

**Por quê:** Stories devem ser pequenas e focadas em uma capacidade.

---

### ❌ Sem Critérios de Aceitação

**Ruim:**
```
Como usuário,
Quero buscar por produtos,
Para que eu possa encontrar o que preciso.
```

**Bom:** Adicione critérios específicos:
```
Critérios de Aceitação:
- [ ] Busca funciona em nome e descrição do produto
- [ ] Resultados exibem em menos de 2 segundos
- [ ] Exibe "Nenhum resultado encontrado" quando não há correspondências
- [ ] Mostra top 20 resultados com paginação
```

**Por quê:** Critérios de aceitação definem "pronto" e permitem testes.

---

## Técnicas de Divisão de Stories

Quando uma story é muito grande, use estas técnicas para dividi-la:

### 1. Por Etapas do Workflow

**Story Grande:**
```
Como usuário, quero reservar um voo online.
```

**Stories Divididas:**
- Buscar por voos
- Selecionar voo
- Inserir dados do passageiro
- Escolher assento
- Fazer pagamento
- Receber confirmação

---

### 2. Por Persona de Usuário

**Story Grande:**
```
Como usuário, quero gerenciar minhas assinaturas.
```

**Stories Divididas:**
- Como usuário gratuito, quero ver planos disponíveis
- Como usuário pago, quero fazer upgrade do meu plano
- Como admin, quero gerenciar assinaturas do time

---

### 3. Por Regras de Negócio

**Story Grande:**
```
Como usuário, quero aplicar códigos de desconto.
```

**Stories Divididas:**
- Aplicar desconto percentual (ex: 20% off)
- Aplicar desconto de valor fixo (ex: R$10 off)
- Aplicar desconto de frete grátis
- Tratar códigos de desconto expirados
- Limitar um desconto por pedido

---

### 4. Por Variações de Dados

**Story Grande:**
```
Como usuário, quero importar contatos.
```

**Stories Divididas:**
- Importar de arquivo CSV
- Importar do Google Contacts
- Importar do Microsoft Outlook
- Importar do LinkedIn

---

### 5. Por Operações CRUD

**Story Grande:**
```
Como usuário, quero gerenciar meus projetos.
```

**Stories Divididas:**
- Criar um novo projeto
- Visualizar detalhes do projeto
- Atualizar configurações do projeto
- Excluir um projeto

---

### 6. Por Happy Path / Edge Cases

**Story MVP (Happy Path):**
```
Como usuário, quero fazer upload de uma foto de perfil (JPG, < 5MB).
```

**Stories de Follow-up:**
- Suportar formatos adicionais (PNG, GIF)
- Tratar arquivos maiores que 5MB com mensagem de erro
- Auto-crop/redimensionar imagens
- Permitir exclusão de foto

---

## Diretrizes de Dimensionamento de Stories



**1-2 Pontos (Poucas horas):**
- Mudança simples de UI
- Atualização de copy
- Configuração menor

**3-5 Pontos (1-2 dias):**
- Novo formulário com validação
- Endpoint de API simples
- Feature toggle básico

**8 Pontos (3-5 dias):**
- Formulário complexo com lógica de negócio
- Integração com serviço de terceiro
- Novo schema de banco de dados com migração

**13+ Pontos (1+ semanas):**
- Muito grande! Divida a story
- Considere como um Epic

---

## Templates para Cenários Comuns

### Registro/Sign-Up

```
Como novo visitante,
Quero criar uma conta com meu email,
Para que eu possa acessar features personalizadas.

Critérios de Aceitação:
- [ ] Email e senha obrigatórios (senha: min 8 caracteres, 1 número, 1 caractere especial)
- [ ] Validação de email e verificação de duplicidade
- [ ] Email de confirmação enviado após registro
- [ ] Logado automaticamente após confirmação de email
- [ ] Opção de cadastrar com Google/Apple (social auth)
```

### Exportação de Dados

```
Como usuário,
Quero exportar meus dados como CSV,
Para que eu possa analisá-los no Excel.

Critérios de Aceitação:
- [ ] Botão de exportação nas configurações
- [ ] Inclui todos os dados do usuário (especificar campos)
- [ ] Arquivo baixa imediatamente (ou email se > 10MB)
- [ ] Formato do nome do arquivo: "export_[username]_[data].csv"
- [ ] Respeita regulamentações de privacidade de dados (apenas dados próprios do usuário)
```

### Tratamento de Erros

```
Como usuário,
Quero ver mensagens de erro úteis,
Para que eu saiba como corrigir problemas.

Critérios de Aceitação:
- [ ] Mensagens de erro são específicas (não genéricas "Erro ocorrido")
- [ ] Sugerem próximos passos acionáveis
- [ ] Exibem no idioma do usuário
- [ ] Não expõem detalhes técnicos (stack traces)
- [ ] Logam erros para debugging (backend)
```

---

## Resumo de Melhores Práticas

1. **Escreva da perspectiva do usuário**, não da perspectiva do sistema
2. **Foque em valor/benefício**, não apenas funcionalidade
3. **Mantenha stories pequenas** (completáveis em uma sprint)
4. **Faça critérios de aceitação testáveis**
5. **Use formato consistente** em todo seu time
6. **Inclua edge cases** nos critérios de aceitação
7. **Colabore** com engenheiros e designers ao escrever
8. **Refine regularmente** baseado em novos aprendizados
9. **Link para mockups/designs** quando relevante
10. **Priorize impiedosamente** (must/should/nice-to-have)

---

## Recursos Adicionais

### Template de User Story

```
Título: [Nome conciso da feature]

Como [tipo específico de usuário],
Quero [ação/capacidade],
Para que [benefício/valor].

Critérios de Aceitação:
- [ ] [Critério testável 1]
- [ ] [Critério testável 2]
- [ ] [Tratamento de edge case]

Prioridade: [Urgent / High / Medium / Low / No Priority]

Dependências: [Liste se houver]
Design: [Link para mockups]
Notas: [Contexto adicional]
```

### Epic vs Story vs Task

**Epic:** Grande corpo de trabalho (múltiplas sprints)
- Exemplo: "Sistema de Autenticação de Usuário"

**Story:** Valor entregável (uma sprint)
- Exemplo: "Como usuário, quero resetar minha senha..."

**Task:** Passo de implementação (horas/dias)
- Exemplo: "Criar endpoint de API de reset de senha"

---

## Conclusão

User stories eficazes:
- Começam com a perspectiva do usuário
- Articulam valor claramente
- Incluem critérios de aceitação testáveis
- São dimensionadas apropriadamente
- Permitem colaboração do time

Use estes exemplos como templates, mas adapte-os para seu produto e necessidades específicas dos seus usuários!
