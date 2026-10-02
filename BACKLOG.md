# PRODUCT BACKLOG DELBICOS - SEGUNDO SEMESTRE 2026 (v7.0)

## Chatbot Multimodal com Geolocalização, Evidências, Sistema de Chamados e Infraestrutura em Nuvem Azure

**Instituição:** Fatec Votorantim - Curso de DSM
**Equipe:** Desenvolvimento DelBicos
**Disciplinas Envolvidas:**
- **Disciplina-Chave:** Laboratório de Desenvolvimento Multiplataforma
- **Disciplinas Satélites:** Computação em Nuvem II, Processamento de Linguagem Natural (PLN), Qualidade e Testes de Software

**Documento:** Product Backlog
**Data de elaboração:** 21/08/2026
**Início do desenvolvimento:** 24/08/2026
**Duração da sprint:** 2 semanas (14 dias)
**Total de sprints:** 6 (mais buffer)
**Término previsto:** 13/11/2026

---

## 1. VISÃO GERAL DO PRODUTO

### 1.1 Problema

Usuários (clientes) têm dificuldade em encontrar o serviço correto sem saber seu nome exato, gerenciar agendamentos de forma rápida e interagir com a plataforma quando não podem ou não querem digitar. Prestadores de serviço precisam de ferramentas para comprovar a realização do trabalho e clientes precisam de transparência sobre a execução do serviço. Além disso, não há um canal estruturado para reportar problemas ou tirar dúvidas sobre a plataforma.

### 1.2 Proposta de Valor

A DelBicos oferece uma plataforma multimodal que conecta clientes e prestadores de serviço. Através de um chatbot inteligente com entrada por texto e voz, os usuários podem buscar serviços por significado, agendar, cancelar e alterar compromissos, além de realizar o check-in/check-out de atendimentos. A plataforma oferece rastreamento em tempo real do prestador, evidências fotográficas do serviço (antes/depois) e um sistema completo de chamados para suporte. Tudo isso construído com uma arquitetura robusta em nuvem na Microsoft Azure.

### 1.3 Objetivos Específicos

| ID | Objetivo |
|----|----------|
| OE-01 | Permitir que clientes e prestadores interajam com a plataforma por meio de comandos de texto e voz |
| OE-02 | Converter fala em texto (Speech-to-Text) em português, fornecendo feedback visual ao usuário |
| OE-03 | Classificar a intenção do usuário e extrair entidades relevantes (serviço, data, hora) usando TF-IDF + SVM |
| OE-04 | Realizar busca semântica no catálogo de serviços a partir da consulta do usuário |
| OE-05 | Gerenciar o ciclo de vida completo de um agendamento (solicitação, confirmação, a caminho, check-in, atendimento, check-out, conclusão/cancelamento) |
| OE-06 | Hospedar a aplicação (backend, bancos de dados, armazenamento e frontend web) em ambiente de produção na nuvem Microsoft Azure |
| OE-07 | Garantir a qualidade do sistema por meio de um plano de testes, testes de caixa preta, diagrama UML de Estados e automação de testes (Jest) integrada a um pipeline de CI/CD |
| OE-08 | Assegurar que a infraestrutura em nuvem seja segura, com credenciais gerenciadas em um cofre (Key Vault) e acessos controlados |
| OE-09 | Permitir que clientes e prestadores abram chamados de suporte e que o admin gerencie e atenda esses chamados |
| OE-10 | Fornecer rastreamento em tempo real do prestador durante o deslocamento e evidências fotográficas do serviço realizado |

---

## 2. MARCOS ACADÊMICOS E ENTREGAS

| Entrega | Disciplina | Data | Descrição |
|---------|------------|------|-----------|
| **Entrega 1 - PI** | Laboratório de Desenvolvimento Multiplataforma | 21/09/2026 | Protótipo funcional: Voz → Transcrição → PLN → Busca Semântica → Resultados. Apresentação do estado do projeto para a banca, com Product Backlog |
| **1ª Entrega - PLN** | Processamento de Linguagem Natural | 21/09/2026 | Implementação do sistema de busca semântica com entrada por voz |
| **1ª Entrega - Qualidade** | Qualidade e Testes de Software | 21/09/2026 | Plano de Teste, Teste de Caixa Preta (Partição de Equivalência/Valor Limite), Diagrama UML de Estados do fluxo de Check-in/Check-out com casos de teste |
| **1ª Entrega - Computação em Nuvem II** | Computação em Nuvem II | **05/10/2026** | Análise situacional da versão atual e proposta para o estado final em produção na Azure |
| **2ª Entrega - Computação em Nuvem II** | Computação em Nuvem II | **16/11/2026** | Documentação técnica (PDF) da versão final do projeto em produção na Azure, permitindo manutenção por outra equipe |
| **Entrega 2 - PI / Entrega Final - PLN** | PI / PLN | 21/11/2026 | Chatbot completo com gestão de agendamentos integrado e classificação de intenções por TF-IDF + SVM. Entrega do panfleto, documentação completa e apresentação no formato "Mostra" |
| **2ª Entrega - Qualidade** | Qualidade e Testes de Software | 21/11/2026 | Pipeline de CI/CD (GitHub Actions) configurado, testes automatizados com Jest e cobertura mínima de 85% |

---

## 3. CRONOGRAMA DE SPRINTS

| Sprint | Início | Término | Foco Principal | Marco Associado |
|--------|--------|---------|----------------|-----------------|
| **Sprint 1** | 24/08/2026 | 04/09/2026 | Fundação: Correções Críticas, Plano de Teste e Setup Inicial | - |
| **Sprint 2** | 07/09/2026 | 18/09/2026 | **PLN: Voz + Busca Semântica + Testes Caixa Preta/UML** | **Entrega 1 (21/09)** |
| **Sprint 3** | 21/09/2026 | 02/10/2026 | **Computação em Nuvem II: Análise e Provisionamento Inicial na Azure** | **Entrega 1 - Cloud (05/10)** |
| **Sprint 4** | 05/10/2026 | 16/10/2026 | **Chatbot Completo (TF-IDF + SVM) + Sistema de Chamados (Tickets)** | - |
| **Sprint 5** | 19/10/2026 | 30/11/2026 | **Jornada de Atendimento (Geolocalização, Evidências, Notificações) + Pipeline CI/CD + Jest** | - |
| **Sprint 6** | 02/11/2026 | 13/11/2026 | **Qualidade, Estabilização, Deploy Final e Documentação** | **Entrega 2 Cloud (16/11) / Entregas Finais (21/11)** |

---

## 4. PRODUCT BACKLOG DETALHADO

### 4.1 ÉPICO 1: Fundação do Agendamento & Chatbot Essencial

**Objetivo:** Corrigir a base do sistema de agendamento, tornando-o identificável com IDs não sequenciais e coletando informações críticas (endereço, pagamento) no fluxo do chatbot.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| AG-01 | Como cliente, quero que meu agendamento tenha um ID curto e aleatório (ex: `#A7F3`) para facilitar sua identificação | Alta | Correção | 1 |
| AG-02 | Como desenvolvedor, quero substituir o uso do ID sequencial pelo novo ID curto em todo o backend e frontend | Alta | Técnica | 1 |
| CHAT-01 | Como cliente, quero informar meu endereço durante o fluxo do chatbot para que o profissional saiba onde ir | Alta | Funcional | 1 |
| CHAT-02 | Como cliente, quero selecionar minha forma de pagamento no chatbot para concluir a solicitação do serviço | Alta | Funcional | 1 |
| AG-03 | Como profissional, quero ver o endereço e a forma de pagamento do cliente nos detalhes do agendamento | Alta | Funcional | 1 |
| AG-04 | Como cliente, quero visualizar todas as informações do agendamento no meu histórico (ID, serviço, data, status, endereço, pagamento) | Alta | Funcional | 1 |
| AG-05 | Como desenvolvedor, quero garantir a consistência do ID curto entre o chat, o histórico e o backend | Média | Técnica | 3 |

**Critérios de Aceite:**
- [ ] O ID do agendamento é único, não sequencial e com no máximo 6 caracteres
- [ ] O ID é exibido em todas as telas de detalhes e histórico do agendamento
- [ ] Endereço e forma de pagamento são campos obrigatórios na criação de um agendamento
- [ ] O histórico exibe todas as informações completas do agendamento

---

### 4.2 ÉPICO 2: Núcleo de PLN - Voz & Busca Semântica (Entrega 1)

**Objetivo:** Cumprir o marco acadêmico de 21/09, entregando o pipeline de PLN que recebe voz, transcreve, classifica a intenção (usando TF-IDF + SVM) e realiza busca semântica no catálogo.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| PLN-01 | Como cliente, quero usar o microfone para gravar um comando de voz e enviá-lo para processamento | Crítica | Funcional | 2 |
| PLN-02 | Como desenvolvedor, quero integrar a API do Azure Speech-to-Text para converter áudio em texto em português | Crítica | Técnica | 2 |
| PLN-03 | Como cliente, quero ver a transcrição da minha fala na tela para confirmar que o sistema entendeu corretamente | Alta | Funcional | 2 |
| PLN-04 | Como desenvolvedor, quero implementar um pipeline de NLP (normalização, tokenização, stemming) e representação TF-IDF | Crítica | Técnica | 2 |
| PLN-05 | Como desenvolvedor, quero treinar um classificador SVM sobre o TF-IDF para identificar intenções (agendar, cancelar, buscar, saudação) | Crítica | Técnica | 2 |
| PLN-06 | Como desenvolvedor, quero extrair entidades (serviço, data, hora) do texto para alimentar o fluxo de agendamento | Crítica | Técnica | 2 |
| PLN-07 | Como desenvolvedor, quero gerar embeddings do catálogo de serviços para realizar busca por similaridade semântica | Crítica | Técnica | 2 |
| PLN-08 | Como cliente, quero buscar por "montar armário" e receber serviços relevantes de montagem como resultado | Crítica | Funcional | 2 |
| PLN-09 | Como desenvolvedor, quero documentar o pipeline de PLN (etapas, bibliotecas, justificativa do uso de TF-IDF+SVM) | Alta | Técnica | 2 |
| PLN-10 | Como desenvolvedor, quero definir o conjunto de intenções e montar as frases de treino para o classificador SVM | Alta | Técnica | 2 |
| PLN-11 | Como desenvolvedor, quero implementar um limiar de confiança para o SVM e um fluxo de fallback para intenções não reconhecidas, exibindo uma mensagem amigável ao usuário | Alta | Técnica | 2 |
| PLN-12 | Como desenvolvedor, quero avaliar a acurácia do classificador SVM com um conjunto de teste e documentar os resultados | Alta | Técnica | 2 |

**Critérios de Aceite:**
- [ ] Ao falar "preciso de alguém para montar um armário", o sistema exibe a transcrição e os serviços de montagem
- [ ] A busca semântica retorna resultados relevantes para buscas não literais
- [ ] O modelo SVM classifica corretamente as intenções de teste com boa acurácia
- [ ] Intenções com baixa confiança disparam o fluxo de fallback
- [ ] Nenhuma chave de API é exposta no frontend
- [ ] A documentação do pipeline de PLN está completa e acessível
- [ ] A acurácia do SVM é medida e documentada

---

### 4.3 ÉPICO 3: Infraestrutura e Hospedagem em Nuvem (Azure) - Computação em Nuvem II

**Objetivo:** Atender aos requisitos da disciplina de Computação em Nuvem II, provisionando e configurando todos os recursos necessários na Microsoft Azure para a aplicação em produção.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| INFRA-01 | Como desenvolvedor, quero provisionar um **Azure App Service** para hospedar o backend Express/Node.js da DelBicos | Crítica | Técnica | 3 |
| INFRA-02 | Como desenvolvedor, quero provisionar um **Azure Database for PostgreSQL** para os dados estruturados (usuários, agendamentos, serviços) | Crítica | Técnica | 3 |
| INFRA-03 | Como desenvolvedor, quero provisionar uma instância do **Azure Cosmos DB** para dados não-relacionais (ex: histórico de conversas, embeddings de PLN) | Crítica | Técnica | 3 |
| INFRA-04 | Como desenvolvedor, quero configurar um **Azure Blob Storage** para armazenar imagens (perfis, catálogo de serviços, evidências) | Alta | Técnica | 3 |
| INFRA-05 | Como desenvolvedor, quero configurar o **Azure Key Vault** para armazenar credenciais (chaves de API, strings de conexão) e referenciá-las no App Service | Crítica | Técnica | 3 |
| INFRA-06 | Como desenvolvedor, quero configurar um **Azure Static Web App** para publicar o frontend web (build do React Native/Expo) | Alta | Técnica | 3 |
| INFRA-07 | Como desenvolvedor, quero criar um **Plano de Serviço de Aplicativo** (App Service Plan) adequado para a carga esperada e estimar os custos mensais de operação | Alta | Técnica | 3 |
| INFRA-08 | Como desenvolvedor, quero documentar a arquitetura de nuvem (diagrama, serviços utilizados, variáveis de ambiente, processo de deploy) para a disciplina | Alta | Técnica | 6 |
| INFRA-09 | Como desenvolvedor, quero configurar o **Azure Application Insights** para monitorar a saúde, desempenho e logs da aplicação em produção | Alta | Técnica | 3 |
| INFRA-10 | Como desenvolvedor, quero configurar **backup automatizado** do PostgreSQL e Cosmos DB com política de retenção de 7 dias | Média | Técnica | 3 |
| INFRA-11 | Como desenvolvedor, quero configurar as **variáveis de ambiente** no App Service para conectar a aplicação ao PostgreSQL, Cosmos DB, Blob Storage e Key Vault | Crítica | Técnica | 3 |

**Critérios de Aceite:**
- [ ] O backend está acessível publicamente via URL do App Service
- [ ] Os bancos de dados (SQL e NoSQL) estão provisionados e com dados migrados
- [ ] O Blob Storage está configurado e o upload de imagens funciona
- [ ] Nenhuma credencial está exposta no repositório ou no frontend
- [ ] O Application Insights está coletando logs e métricas da aplicação
- [ ] Backups automáticos estão configurados e testados
- [ ] Uma análise situacional e uma proposta de arquitetura final foram entregues (05/10)
- [ ] Documentação técnica da infraestrutura está completa (16/11)

---

### 4.4 ÉPICO 4: Gestão Completa no Chatbot

**Objetivo:** Evoluir o protótipo de PLN para um chatbot completo, integrando o classificador de intenções ao fluxo de gestão de agendamentos.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| CHAT-04 | Como cliente, quero que o chatbot me guie na coleta de dados para agendar um serviço (data, hora, endereço, pagamento) | Crítica | Funcional | 4 |
| CHAT-05 | Como cliente, quero consultar meus agendamentos pelo chatbot e ver o ID e status de cada um | Alta | Funcional | 4 |
| CHAT-06 | Como cliente, quero solicitar o cancelamento de um agendamento via chatbot, confirmando a ação | Alta | Funcional | 4 |
| CHAT-07 | Como cliente, quero solicitar a alteração de data/horário e validar a nova disponibilidade | Alta | Funcional | 4 |
| CHAT-08 | Como cliente, quero que o fluxo do chatbot (texto ou voz) seja o mesmo, garantindo consistência | Alta | Técnica | 4 |
| CHAT-09 | Como cliente, quero continuar usando o chat por texto se a voz falhar, sem perder minha sessão | Alta | Funcional | 4 |
| CHAT-10 | Como desenvolvedor, quero implementar idempotência para que reenvios não criem ações duplicadas | Média | Técnica | 4 |
| CHAT-11 | Como desenvolvedor, quero conectar as respostas do chatbot às regras de negócio definidas para cada intenção classificada pelo SVM | Alta | Técnica | 4 |

**Critérios de Aceite:**
- [ ] O chatbot consegue coletar todas as informações para um agendamento
- [ ] "Quais são meus agendamentos?" mostra a lista correta
- [ ] "Cancelar agendamento #A7F3" pede confirmação antes de executar
- [ ] A intenção "Alterar" dispara o fluxo de remarcação
- [ ] O fluxo por voz e por texto é consistente

---

### 4.5 ÉPICO 5: Fluxo de Atendimento - Check-in / Check-out

**Objetivo:** Adicionar a camada de confirmação do serviço, fechando o ciclo do agendamento. Esta funcionalidade é a base para o diagrama UML de Estados da disciplina de Qualidade.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| CHK-01 | Como desenvolvedor, quero gerar um código de confirmação único e seguro (ex: `ABC-123`) para cada agendamento | Alta | Funcional | 5 |
| CHK-02 | Como cliente/profissional, quero visualizar o código de confirmação no agendamento | Alta | Funcional | 5 |
| CHK-03 | Como profissional/cliente, quero validar o código para realizar o Check-in | Crítica | Funcional | 5 |
| CHK-04 | Como profissional/cliente, quero validar o código para realizar o Check-out | Crítica | Funcional | 5 |
| CHK-05 | Como desenvolvedor, quero que o status do agendamento seja atualizado automaticamente para "Em Atendimento" (Check-in) e "Concluído" (Check-out) | Alta | Técnica | 5 |
| CHK-06 | Como desenvolvedor, quero garantir que códigos inválidos ou já utilizados sejam rejeitados | Média | Técnica | 6 |
| CHK-07 | Como desenvolvedor, quero registrar histórico de Check-in/Check-out para auditoria | Média | Técnica | 6 |

**Critérios de Aceite:**
- [ ] O código de confirmação é gerado e associado ao agendamento
- [ ] A validação do código altera o status do atendimento no banco de dados
- [ ] Códigos inválidos ou já usados são rejeitados com uma mensagem de erro clara
- [ ] O histórico de check-in/check-out é registrado com timestamps

---

### 4.6 ÉPICO 6: Qualidade, Testes e CI/CD (Disciplina Qualidade e Testes)

**Objetivo:** Garantir a qualidade do software, cumprindo as duas entregas da disciplina.

#### Subgrupo A — 1ª Entrega (21/09): Plano de Teste, Caixa Preta e UML

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| QA-06 | Como equipe, quero elaborar o **Plano de Teste** (objetivo, itens, estratégia, critérios, recursos, cronograma) | Alta | Técnica | 1 |
| QA-07 | Como equipe, quero definir os **papéis envolvidos no teste** (responsável, testador, revisor) | Média | Técnica | 1 |
| QA-08 | Como desenvolvedor, quero aplicar **Partição de Equivalência** e **Análise de Valor Limite** para o teste de caixa preta da busca semântica e agendamento | Alta | Técnica | 2 |
| QA-09 | Como desenvolvedor, quero criar o **Diagrama UML de Estados** do fluxo de Check-in/Check-out (incluindo o estado "A Caminho") | Alta | Técnica | 2 |
| QA-10 | Como desenvolvedor, quero criar casos de teste para cada estado, transição e caminho do diagrama UML | Alta | Técnica | 2 |

#### Subgrupo B — 2ª Entrega (21/11): Pipeline CI/CD, Jest e Qualidade Automatizada

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| QA-01 | Como desenvolvedor, quero configurar um **workflow no GitHub Actions** que execute os testes a cada push/PR | Crítica | Técnica | 5 |
| QA-02 | Como desenvolvedor, quero escrever testes unitários para o fluxo de agendamento | Alta | Técnica | 1 |
| QA-03 | Como desenvolvedor, quero criar testes para o fluxo de Check-in/Check-out | Alta | Técnica | 5 |
| QA-04 | Como desenvolvedor, quero executar testes de regressão antes de cada release | Média | Técnica | 6 |
| QA-05 | Como desenvolvedor, quero automatizar os casos de teste com **Jest**, garantindo cobertura mínima de 85% do código | Crítica | Técnica | 5 |
| QA-11 | Como desenvolvedor, quero configurar a pipeline para fazer o deploy automático na Azure após os testes passarem | Alta | Técnica | 5 |
| QA-12 | Como desenvolvedor, quero configurar o GitHub Actions para **bloquear merges** com cobertura de testes abaixo de 85% | Crítica | Técnica | 5 |
| QA-13 | Como desenvolvedor, quero criar suites de teste separadas para desktop e mobile | Alta | Técnica | 5 |
| QA-14 | Como desenvolvedor, quero definir regras de IA para gerar componentes, stores, utils e testes padronizados | Alta | Técnica | 1 |
| QA-15 | Como desenvolvedor, quero criar o arquivo `.cursorrules` com regras de geração de código e aplicá-lo na equipe | Alta | Técnica | 1 |
| QA-16 | Como desenvolvedor, quero configurar GitHub Action para verificar a cobertura de testes e bloquear PRs abaixo de 85% | Crítica | Técnica | 5 |
| QA-17 | Como desenvolvedor, quero configurar GitHub Action para verificar o uso de dark mode (`theme.colors`) | Alta | Técnica | 5 |
| QA-18 | Como desenvolvedor, quero configurar GitHub Action para analisar complexidade ciclomática e alertar sobre código complexo | Média | Técnica | 6 |
| QA-19 | Como desenvolvedor, quero integrar **SonarQube** para monitorar qualidade do código e gerar relatórios | Média | Técnica | 6 |
| QA-20 | Como desenvolvedor, quero escrever **testes de integração** para os endpoints críticos da API (criação, check-in, check-out) validando a comunicação com o banco de dados | Alta | Técnica | 5 |
| QA-21 | Como desenvolvedor, quero configurar o Jest para **gerar um relatório de cobertura** e publicá-lo como artefato no GitHub Actions | Média | Técnica | 5 |
| QA-22 | Como desenvolvedor, quero planejar e executar um teste de carga básico para validar a escalabilidade do App Service | Baixa | Técnica | 6 |

**Critérios de Aceite:**
- [ ] O Plano de Teste está documentado e revisado
- [ ] O diagrama UML de Estados está criado e validado
- [ ] A pipeline do GitHub Actions é executada com sucesso a cada push
- [ ] A cobertura de testes é de, no mínimo, 85%
- [ ] Merges com cobertura abaixo de 85% são bloqueados
- [ ] Os testes automatizados são executados como parte do processo de build
- [ ] Testes de integração estão implementados e passando
- [ ] Relatório de cobertura é gerado e publicado como artefato
- [ ] O SonarQube está integrado e gerando relatórios de qualidade

---

### 4.7 ÉPICO 7: Experiência do Usuário & Consistência Visual

**Objetivo:** Garantir que a interface do chatbot esteja alinhada ao design system do Figma.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| UX-01 | Como designer, quero auditar a interface atual do chat e compará-la com o Figma | Alta | Técnica | 5 |
| UX-02 | Como desenvolvedor, quero adaptar layout e componentes ao design system definido | Alta | Técnica | 5 |
| UX-03 | Como desenvolvedor, quero implementar estados de interação (hover, active, disabled) conforme o Figma | Alta | Técnica | 5 |
| UX-04 | Como cliente, quero usar o chat de forma confortável tanto no celular quanto no navegador | Média | Funcional | 5 |
| UX-05 | Como desenvolvedor, quero corrigir o fluxo "Ver agenda" que está com problemas de navegação | Alta | Correção | 1 |
| UX-06 | Como desenvolvedor, quero validar a implementação contra o Figma e ajustar inconsistências | Média | Técnica | 6 |
| UX-07 | Como desenvolvedor, quero adaptar a interface automaticamente ao tema claro/escuro do sistema | Crítica | Técnica | 4 |
| UX-08 | Como usuário, quero alternar manualmente entre dark mode e light mode com a preferência persistida | Alta | Funcional | 4 |
| UX-09 | Como desenvolvedor, quero criar um sistema de temas centralizado com paleta de cores para definir variantes claro/escuro | Crítica | Técnica | 4 |
| UX-10 | Como desenvolvedor, quero refatorar todos os componentes para usar o sistema de temas e suportar dark mode | Alta | Técnica | 4 |
| UX-11 | Como desenvolvedor, quero criar o hook `useTheme` para acessar o tema atual e permitir que componentes reajam a mudanças | Alta | Técnica | 4 |
| UX-12 | Como desenvolvedor, quero testar todos os componentes em dark mode, garantindo legibilidade e contraste | Alta | Técnica | 5 |
| UX-13 | Como desenvolvedor, quero configurar Storybook para visualizar componentes em ambos os temas | Média | Técnica | 5 |
| UX-14 | Como desenvolvedor, quero executar testes automatizados de acessibilidade (ex.: axe-core) nos componentes principais para garantir conformidade com WCAG 2.1 AA | Média | Técnica | 6 |

**Critérios de Aceite:**
- [ ] O chat é funcional e visualmente alinhado ao Figma
- [ ] Fluxos críticos testados e responsivos (web e mobile)
- [ ] Navegação corrigida após pagamento
- [ ] Dark mode e light mode funcionam em todos os componentes
- [ ] A preferência do usuário é persistida entre sessões
- [ ] Os testes de acessibilidade são executados no pipeline

---

### 4.8 ÉPICO 8: Segurança e Documentação

**Objetivo:** Garantir a segurança da aplicação e a documentação completa.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| SEC-01 | Como desenvolvedor, quero garantir que todas as chaves de API estejam somente no backend ou no Key Vault | Crítica | Técnica | 3 |
| SEC-02 | Como desenvolvedor, quero implementar autenticação JWT e rate limit nas rotas críticas | Alta | Técnica | 2 |
| SEC-03 | Como desenvolvedor, quero garantir que áudio, transcrição e dados sensíveis não sejam logados em texto plano | Alta | Técnica | 2 |
| SEC-04 | Como desenvolvedor, quero implementar RBAC (Role-Based Access Control) com permissões para cliente, prestador e admin | Crítica | Técnica | 4 |
| SEC-05 | Como desenvolvedor, quero implementar **logs de auditoria** para operações críticas (acesso a agendamentos, alterações de status, check-in/out) | Média | Técnica | 6 |
| SEC-06 | Como desenvolvedor, quero **criptografar dados sensíveis** (endereço, forma de pagamento) no banco de dados PostgreSQL usando criptografia em repouso | Alta | Técnica | 3 |
| DOC-01 | Como desenvolvedor, quero documentar a arquitetura, as rotas da API, o pipeline de CI/CD e o manual do usuário | Alta | Técnica | 6 |
| DOC-02 | Como equipe, quero elaborar o panfleto (folder) promocional para a "Mostra" | Média | Técnica | 6 |

**Critérios de Aceite:**
- [ ] Nenhuma chave ou credencial exposta no frontend ou repositório
- [ ] Autenticação JWT funcionando em todas as rotas protegidas
- [ ] RBAC implementado: admin tem acesso total, usuários veem apenas seus próprios dados
- [ ] Logs de auditoria registram todas as operações críticas
- [ ] Dados sensíveis estão criptografados no banco de dados
- [ ] Documentação completa (técnica, desenvolvimento, usuário) entregue em PDF
- [ ] Panfleto promocional elaborado e impresso para a Mostra

---

### 4.9 ÉPICO 9: Jornada de Atendimento com Geolocalização e Evidências

**Objetivo:** Expandir o fluxo de check-in/check-out com funcionalidades de rastreamento em tempo real, notificações de status e registro fotográfico de antes/depois, melhorando a transparência e a confiança entre cliente e prestador.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| GEO-01 | Como prestador, quero iniciar o compartilhamento da minha localização ao mudar o status para "A Caminho" para informar o cliente sobre minha localização | Crítica | Funcional | 5 |
| GEO-02 | Como cliente, quero visualizar o prestador em um mapa em tempo real e ver o status "A Caminho" para saber quando ele vai chegar | Crítica | Funcional | 5 |
| GEO-03 | Como prestador, quero parar o compartilhamento de localização ao realizar o check-in para encerrar o rastreamento | Alta | Funcional | 5 |
| GEO-04 | Como desenvolvedor, quero integrar a API do Google Maps ou MapLibre para exibir mapa e atualizar a posição do prestador em tempo real | Crítica | Técnica | 5 |
| GEO-05 | Como desenvolvedor, quero implementar WebSockets (Socket.io) para transmitir a localização do prestador para o cliente em tempo real | Crítica | Técnica | 5 |
| GEO-06 | Como desenvolvedor, quero armazenar o histórico de localização do prestador para auditoria e rastreabilidade | Média | Técnica | 6 |
| GEO-07 | Como desenvolvedor, quero solicitar e registrar o consentimento do usuário para compartilhamento de localização antes de iniciar o rastreamento, em conformidade com a LGPD | Alta | Técnica | 5 |
| NOT-01 | Como cliente, quero receber uma notificação push quando o prestador mudar o status para "A Caminho" para saber que ele está vindo | Alta | Funcional | 5 |
| NOT-02 | Como cliente, quero receber uma notificação push quando o prestador realizar o check-in para saber que ele chegou | Alta | Funcional | 5 |
| NOT-03 | Como cliente, quero receber uma notificação push quando o serviço for concluído com as fotos do antes/depois anexadas para validar o resultado | Alta | Funcional | 6 |
| NOT-04 | Como desenvolvedor, quero integrar um serviço de notificações (Firebase Cloud Messaging) para enviar notificações push para os dispositivos | Alta | Técnica | 5 |
| EVI-01 | Como prestador, quero tirar uma foto do local antes de iniciar o serviço e anexar ao agendamento para registrar o estado inicial | Crítica | Funcional | 5 |
| EVI-02 | Como prestador, quero tirar uma foto do local depois de concluir o serviço e anexar ao agendamento para comprovar a realização | Crítica | Funcional | 5 |
| EVI-03 | Como cliente, quero visualizar as fotos de antes e depois no detalhe do agendamento para validar o serviço realizado | Alta | Funcional | 5 |
| EVI-04 | Como desenvolvedor, quero integrar a câmera do dispositivo (React Native Camera) para capturar e fazer upload das fotos para o Azure Blob Storage | Crítica | Técnica | 5 |
| EVI-05 | Como desenvolvedor, quero validar que a foto do "antes" foi tirada antes do check-in e a do "depois" antes do check-out para garantir a ordem correta | Média | Técnica | 6 |
| EVI-06 | Como desenvolvedor, quero definir uma política de retenção para as fotos de evidência (ex.: 90 dias) e implementar a exclusão automática no Blob Storage | Média | Técnica | 6 |
| EVI-07 | Como desenvolvedor, quero implementar tratamento de erros para falhas na captura ou upload de fotos, exibindo mensagens claras ao usuário | Alta | Técnica | 5 |
| JOR-01 | Como cliente, quero visualizar uma linha do tempo da jornada do atendimento (Solicitado → Confirmado → A Caminho → Check-in → Em Atendimento → Check-out → Concluído) para acompanhar o progresso | Alta | Funcional | 6 |
| JOR-02 | Como prestador, quero alterar o status do agendamento para "A Caminho" e confirmar antes de iniciar o rastreamento | Alta | Funcional | 5 |
| JOR-03 | Como desenvolvedor, quero expandir o diagrama UML de Estados (QA-09) para incluir o novo estado "A Caminho" e atualizar os casos de teste | Alta | Técnica | 5 |

**Critérios de Aceite:**
- [ ] Ao mudar o status para "A Caminho", o prestador inicia o compartilhamento de localização e o cliente vê sua posição no mapa em tempo real
- [ ] A posição do prestador é atualizada a cada 5 segundos no mapa do cliente
- [ ] O compartilhamento de localização é interrompido automaticamente após o check-in
- [ ] O cliente recebe notificação push quando o status muda para "A Caminho", "Check-in" e "Concluído"
- [ ] O prestador consegue tirar e anexar fotos "antes" e "depois" do serviço
- [ ] O cliente visualiza as fotos de antes/depois no detalhe do agendamento
- [ ] A linha do tempo da jornada exibe todos os status com timestamps precisos
- [ ] O diagrama UML de Estados é atualizado com o estado "A Caminho"
- [ ] O consentimento para compartilhamento de localização é solicitado e registrado
- [ ] Falhas na captura ou upload de fotos são tratadas com mensagens amigáveis

---

### 4.10 ÉPICO 10: Sistema de Chamados (Tickets de Suporte)

**Objetivo:** Implementar um sistema completo de chamados (tickets) que permita a clientes e prestadores abrir, acompanhar e interagir com solicitações de suporte, e que forneça ao admin um painel para gerenciar e atender esses chamados de forma eficiente.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| TICKET-01 | Como cliente, quero abrir um chamado com título, descrição, categoria e prioridade para reportar um problema ou tirar uma dúvida | Alta | Funcional | 4 |
| TICKET-02 | Como prestador, quero abrir um chamado com título, descrição, categoria e prioridade para reportar um problema ou tirar uma dúvida | Alta | Funcional | 4 |
| TICKET-03 | Como cliente/prestador, quero visualizar todos os meus chamados com status atual para acompanhar o andamento | Alta | Funcional | 4 |
| TICKET-04 | Como cliente/prestador, quero visualizar os detalhes de um chamado específico com todas as interações para ver o histórico | Alta | Funcional | 4 |
| TICKET-05 | Como cliente/prestador, quero adicionar uma nova mensagem em um chamado aberto para fornecer mais informações | Alta | Funcional | 4 |
| TICKET-06 | Como cliente/prestador, quero receber uma notificação quando o chamado for atualizado pelo admin para saber que houve progresso | Alta | Funcional | 5 |
| TICKET-07 | Como cliente, quero avaliar o atendimento após o chamado ser resolvido para dar feedback sobre o suporte | Média | Funcional | 6 |
| TICKET-08 | Como admin, quero visualizar todos os chamados em um painel com filtros por status, prioridade, categoria e data para gerenciar o suporte | Crítica | Funcional | 4 |
| TICKET-09 | Como admin, quero alterar o status de um chamado (Aberto → Em Análise → Em Atendimento → Resolvido → Fechado) para atualizar o progresso | Crítica | Funcional | 4 |
| TICKET-10 | Como admin, quero responder a um chamado adicionando uma mensagem para comunicar com o usuário | Crítica | Funcional | 4 |
| TICKET-11 | Como admin, quero anexar arquivos/imagens à resposta do chamado para compartilhar evidências ou documentos | Média | Funcional | 5 |
| TICKET-12 | Como admin, quero atribuir um chamado a um membro da equipe de suporte para distribuir o trabalho | Média | Funcional | 5 |
| TICKET-13 | Como admin, quero fechar um chamado após resolvido e registrar a solução para finalizar o atendimento | Crítica | Funcional | 5 |
| TICKET-14 | Como admin, quero reabrir um chamado resolvido se o problema persistir para continuar o atendimento | Média | Funcional | 6 |
| TICKET-15 | Como admin, quero visualizar métricas de atendimento (tempo médio de resposta, chamados por categoria) para avaliar a eficiência | Baixa | Funcional | 6 |
| TICKET-16 | Como desenvolvedor, quero criar o modelo de dados para chamados com todos os campos necessários para estruturar o sistema | Crítica | Técnica | 4 |
| TICKET-17 | Como desenvolvedor, quero registrar um **log de auditoria** para cada alteração de status do chamado, armazenando usuário, data/hora e mudança | Média | Técnica | 6 |
| TICKET-18 | Como desenvolvedor, quero configurar o envio de **notificações por e-mail** para o usuário quando o chamado for atualizado, como fallback para push | Média | Técnica | 5 |

**Critérios de Aceite:**
- [ ] Clientes e prestadores podem abrir chamados com todos os campos necessários
- [ ] O painel administrativo exibe todos os chamados com filtros funcionais
- [ ] O admin pode alterar status, responder e atribuir chamados
- [ ] O usuário recebe notificações (push e/ou e-mail) quando o chamado é atualizado
- [ ] O histórico de interações é preservado e exibido
- [ ] O log de auditoria registra todas as alterações de status
- [ ] O sistema de avaliação pós-resolução está funcionando

---

## 5. RESUMO DE MÉTRICAS E CRITÉRIOS DE QUALIDADE

| Métrica | Critério | Como Será Verificado |
|---------|----------|----------------------|
| Cobertura de Testes | ≥ 85% | Relatório do Jest no GitHub Actions |
| Complexidade Ciclomática | ≤ 10 por função | Análise no GitHub Actions / SonarQube |
| Dark Mode | Todos os componentes suportam | Verificação automatizada no pipeline |
| Acessibilidade | WCAG 2.1 AA | Testes com axe-core |
| Acurácia do SVM | ≥ 85% em conjunto de teste | Relatório de métricas do classificador |
| Performance da API | < 500ms para 95% das requisições | Testes de carga com k6 ou similar |
| Disponibilidade | 99.5% uptime | Application Insights |

---

## 6. RISCOS E MITIGAÇÕES

| Risco | Probabilidade | Impacto | Mitigação |
|-------|---------------|---------|-----------|
| Atraso na configuração da infraestrutura Azure | Média | Alto | Iniciar provisionamento na Sprint 3, ter conta Azure configurada com antecedência |
| Falha na integração do Speech-to-Text | Média | Alto | Ter fallback para entrada por texto, testar API com antecedência |
| Baixa acurácia do classificador SVM | Média | Médio | Aumentar conjunto de treino, testar diferentes kernels |
| Dificuldade na integração de geolocalização e WebSockets | Alta | Alto | Estudar Socket.io com antecedência, ter plano B com polling |
| Cobertura de testes abaixo de 85% | Média | Médio | Priorizar testes desde a Sprint 1, fazer revisões diárias de cobertura |
| Problemas de deploy na Azure | Baixa | Alto | Configurar deploy automático (CI/CD) com rollback automatizado |

---

## 7. GLOSSÁRIO

| Termo | Definição |
|-------|-----------|
| **Backlog** | Lista priorizada de requisitos e funcionalidades a serem desenvolvidas |
| **Sprint** | Período fixo de 2 semanas para desenvolvimento de um conjunto de itens do backlog |
| **TF-IDF** | Técnica de representação textual que pondera a importância de termos em um documento |
| **SVM (Support Vector Machine)** | Algoritmo de machine learning para classificação de dados |
| **Azure** | Plataforma de computação em nuvem da Microsoft |
| **CI/CD** | Prática de integração contínua e entrega contínua |
| **Jest** | Framework de testes para JavaScript |
| **RBAC** | Controle de acesso baseado em papéis |
| **JWT** | JSON Web Token para autenticação |
| **WebSocket** | Protocolo de comunicação bidirecional em tempo real |
| **FCM** | Firebase Cloud Messaging - serviço de notificações push |
| **LGPD** | Lei Geral de Proteção de Dados Pessoais |
| **WCAG** | Web Content Accessibility Guidelines - diretrizes de acessibilidade |


**Delbicos.com.br**