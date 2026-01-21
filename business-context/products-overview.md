# Produtos e Domínios Técnicos

Detalhamento técnico dos produtos e domínios mantidos pela área de tecnologia da Gabriel.

> Organização de squads em [organizacao.md](organizacao.md)

## Status de documentação

**Feito (pendente revisão)**:

- [x] Tribo Produtos Digitais (App Gabriel, GabrielOS, Integrações)
- [x] Tribo Borda (Camaleão 3, Camaleão 2, Plataforma Multimídia)
- [x] Tribo Plataforma (Infraestrutura, Dados, Finanças e Contratos, Operações de Campo)

---

## Tribo: Produtos Digitais

### App Gabriel

**Squad**: Aplicativo Gabriel
**PM**: João Gabriel Figueira
Aplicativo mobile que individualiza o poder da Gabriel para os moradores protegidos.
**Plataformas**: iOS, Android
**Stack**: Flutter
**Funcionalidades**:

- Mapa de Camaleões e Alertas da região
- Abertura de chamados para Central 24h
- Feed de casos solucionados e notícias
- Reporte de veículo roubado (com B.O.)
- Visualização de câmeras (ao vivo e histórico)
  **Componentes**:
- BFF Camisa 10 (backend-for-frontend)
  **Integrações**:
- Plataforma de Vídeo

---

### GabrielOS

**Squad**: GabrielOS
**PM**: Beatriz Lima
Plataforma VMS para operadores de centrais 24h e delegacias interagirem com o parque de câmeras da Gabriel. Permite visualização ao vivo e histórica de todas as câmeras, busca analítica de veículos e download de vídeos para envio às autoridades. Reduz custo operacional ao permitir que a própria polícia opere as câmeras diretamente.
**Plataformas**: Web (migração de Windows App)
**Stack**: React
**Funcionalidades**:

- Mapa com todas as câmeras da Gabriel
- Visualização de múltiplas câmeras (ao vivo, histórico e download)
- Busca de rota de veículo (por onde passou na cidade)
- Busca por localidade (quais veículos passaram)
  **Componentes**:
- BFF GabrielOS (backend-for-frontend)
  **Integrações**:
- Plataforma de Vídeo
- Keycloak (autenticação)

---

### Integrações

**Squad**: Integração e Serviços
**PM**: Luiz Torres (Mineiro)
Integrações de analíticos e vídeo com autoridades e sistemas internos da Gabriel.
**Stack**: [ ] A preencher
**Integrações de Analíticos**:
Toda câmera Gabriel lê placas e envia para destinos configurados:

- Autoridades (PM de cada estado) - disparam viatura se veículo está em hotlist policial
- Hotlist Gabriel - lista proprietária de veículos de interesse
- App Gabriel - alerta ao morador quando sua placa roubada é detectada
  **Integrações de Vídeo**:
  Autoridades acessam câmeras Gabriel (ao vivo, histórico, download) em suas próprias plataformas. A squad adapta contratos e APIs para cada integração.
  **Componentes**:
- API Gabriel (API pública, API as a Product)
- Hotlist (listas de veículos/placas de interesse)
- Keycloak (gestão de identidade e acesso)

---

## Tribo: Borda

### Camaleão 3

**Squad**: Camaleão 3
**PM**: Juliana Puterman
Nova geração do dispositivo de monitoramento. Diferente do Camaleão 2 (dois hardwares separados), é um dispositivo unificado 100% Gabriel: PCB com lentes conectadas em um único form factor.
Maior poder computacional para rodar IA na borda e interação com transeuntes via áudio e luz.
**Tipo**: Hardware + Firmware
**Chipset**: Qualcomm QCM6490
**Domínios técnicos**:

- Eletrônica
- Mecânica
- Design Industrial
- Firmware embarcado
- IA na borda
- Visão computacional (edge)
  **Stack**: [ ] A preencher

---

### Camaleão 2

**Squad**: Camaleão 2
**PM**: José Paulo
Produto atual instalado na frente de condomínios residenciais. Composto por dois hardwares:
**Camaleão 2** (parceiro Glory):

- Par de câmeras apontado para a rua
- Hardware da Glory com customizações de firmware
  **Sistema Nervoso 2** (desenvolvimento próprio):
- Gateway de conectividade (modem 4G)
- Configuração das câmeras
- Telemetria
- Placa, componentes e firmware 100% Gabriel
  O Camaleão conecta no Sistema Nervoso via cabo.
  **Tipo**: Hardware + Firmware
  **Domínios técnicos**:
- Eletrônica (Sistema Nervoso)
- Firmware embarcado
- Telemetria
- Provisionamento
  **Stack**: [ ] A preencher

---

### Plataforma Multimídia

**Squad**: Multimídia
**PM**: José Paulo
Gestão de vídeo, analíticos e outros tipos de mídia (áudio). Abrange desde a orquestração em nuvem (Camaleão 2) até o processamento embarcado (Camaleão 3).
**No Camaleão 2 (nuvem)**:

- Orquestração de download de vídeo via API da câmera
- Gestão de streaming ao vivo e histórico
- Resiliência a quedas de conexão
  **No Camaleão 3 (embarcado)**:
- Gestão de vídeo local (armazenamento, histórico, ao vivo)
- Analíticos na borda (LPR, visão computacional)
- Processamento de áudio para interação com transeuntes
  **Domínios técnicos**:
- Streaming e tunelamento
- Armazenamento e indexação
- Visão computacional / AI-ML (LPR)
- Processamento de áudio
  **Stack**: [ ] A preencher
  **Integrações**:
- Camaleão 2 e Camaleão 3
- App Gabriel e GabrielOS
- Squad Integrações (envio para autoridades)

---

## Tribo: Plataforma

### Infraestrutura

**Squad**: Infraestrutura
Infraestrutura cloud que suporta todos os sistemas da Gabriel, incluindo segurança da informação.
**Domínios técnicos**:

- Cloud (AWS)
- DevOps / SRE
- CI/CD
- Observabilidade
- Redes
- InfoSec / Cybersec (adequação ISO 27001)
  **Stack**: [ ] A preencher

---

### Dados

**Squad**: Dados
**PM**: Felipe Araújo
Estruturação de dados para operação e análise. O foco inicial é consolidar o Data Warehouse para que áreas operacionais possam consumir dados estruturados. O próximo passo é transformar dados em inteligência via analytics e ML.
**Data Warehouse**:

- Consolidação de dados para áreas operacionais
- ETL reverso e pipelines de ingestão
- Indexação e enriquecimento
  **Business Analytics**:
- Dashboards e análises (Metabase)
- Análises avançadas com ML (em desenvolvimento)
  **Stack**: [ ] A preencher

---

### Finanças e Contratos

**Squad**: Finanças e Contratos
**PM**: Lucas Agra
Backoffice interno para gestão financeira e de contratos da Gabriel.
**Backoffice Financeiro**:

- Emissão e gestão de boletos
- Ajustes, reemissões, descontos
- Orquestração de movimentos financeiros
  **Backoffice de Contratos**:
- Gestão do que foi contratado em cada venda
- Informações consumidas por ordens de serviço, provisionamento e desinstalação
- Amarração contratual de toda operação Gabriel
  **Stack**: Appsmith (low-code) + APIs backend
  **Componentes**:
- API Finance (operações financeiras)
- API BFirst (gestão de contratos)

---

### Operações de Campo

**Squad**: Operações de Campo
**PM**: Rafael Vaz
Gestão de ordens de serviço e provisionamento de equipamentos.
**Gestão de OS**:

- Organização e acompanhamento de ordens de serviço
- Aplicativos para empresas parceiras de instalação
- Acompanhamento de OS em andamento pelos técnicos
  **Provisionamento**:
- Integração entre instalação física e sistema Gabriel
- Provisionamento do equipamento na localidade
  **Stack**: Appsmith (low-code) + APIs backend
