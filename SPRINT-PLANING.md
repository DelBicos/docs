# SPRINT PLANNING - DELBICOS SEGUNDO SEMESTRE 2026

## Equipe e Capacidade

- **Total de desenvolvedores:** 7
- **Horas disponíveis por desenvolvedor/semana:** 3 a 5 horas
- **Média de horas por desenvolvedor/semana:** 4 horas
- **Total de horas/semana da equipe:** 28 horas (7 × 4h)
- **Duração da sprint:** 2 semanas = 10 dias úteis
- **Total de horas por sprint:** 56 horas (28h × 2 semanas)

---

## SPRINT 1: FUNDAÇÃO (24/08 a 04/09)

### Objetivo da Sprint
Estabelecer a base do sistema com correções críticas, plano de testes e setup inicial.

### Itens do Backlog

| ID | História de Usuário | Estimativa (horas) | Prioridade |
|----|---------------------|-------------------|------------|
| AG-01 | Como cliente, quero que meu agendamento tenha um ID curto e aleatório (ex: `#A7F3`) para facilitar sua identificação | 4 | Alta |
| AG-02 | Como desenvolvedor, quero substituir o uso do ID sequencial pelo novo ID curto em todo o backend e frontend | 8 | Alta |
| CHAT-01 | Como cliente, quero informar meu endereço durante o fluxo do chatbot para que o profissional saiba onde ir | 6 | Alta |
| CHAT-02 | Como cliente, quero selecionar minha forma de pagamento no chatbot para concluir a solicitação do serviço | 4 | Alta |
| AG-03 | Como profissional, quero ver o endereço e a forma de pagamento do cliente nos detalhes do agendamento | 4 | Alta |
| AG-04 | Como cliente, quero visualizar todas as informações do agendamento no meu histórico (ID, serviço, data, status, endereço, pagamento) | 6 | Alta |
| QA-06 | Como equipe, quero elaborar o **Plano de Teste** (objetivo, itens, estratégia, critérios, recursos, cronograma) | 6 | Alta |
| QA-07 | Como equipe, quero definir os **papéis envolvidos no teste** (responsável, testador, revisor) | 2 | Média |
| UX-05 | Como desenvolvedor, quero corrigir o fluxo "Ver agenda" que está com problemas de navegação | 6 | Alta |
| QA-02 | Como desenvolvedor, quero escrever testes unitários para o fluxo de agendamento | 8 | Alta |
| QA-14 | Como desenvolvedor, quero definir regras de IA para gerar componentes, stores, utils e testes padronizados | 4 | Alta |
| QA-15 | Como desenvolvedor, quero criar o arquivo `.cursorrules` com regras de geração de código e aplicá-lo na equipe | 2 | Alta |

**Total estimado:** 60 horas

### Tarefas-Chave da Sprint
1. Setup do ambiente de desenvolvimento e repositório
2. Implementação do sistema de IDs curtos e aleatórios
3. Correção do fluxo de agendamento (endereço e pagamento)
4. Criação da estrutura de testes unitários iniciais
5. Elaboração do Plano de Teste completo
6. Criação das regras de padronização (.cursorrules)

### Riscos e Mitigações
| Risco | Impacto | Mitigação |
|-------|---------|-----------|
| Equipe ainda não está alinhada com a stack | Médio | Realizar onboarding rápido e compartilhar documentação |
| Dificuldade na migração do ID sequencial | Alto | Criar script de migração e testar em ambiente de staging |

---

## SPRINT 2: PLN - VOZ + BUSCA SEMÂNTICA (07/09 a 18/09)

### Objetivo da Sprint
Entregar o pipeline completo de PLN com entrada por voz, transcrição, classificação de intenções e busca semântica.

### Itens do Backlog

| ID | História de Usuário | Estimativa (horas) | Prioridade |
|----|---------------------|-------------------|------------|
| PLN-01 | Como cliente, quero usar o microfone para gravar um comando de voz e enviá-lo para processamento | 6 | Crítica |
| PLN-02 | Como desenvolvedor, quero integrar a API do Azure Speech-to-Text para converter áudio em texto em português | 6 | Crítica |
| PLN-03 | Como cliente, quero ver a transcrição da minha fala na tela para confirmar que o sistema entendeu corretamente | 3 | Alta |
| PLN-04 | Como desenvolvedor, quero implementar um pipeline de NLP (normalização, tokenização, stemming) e representação TF-IDF | 8 | Crítica |
| PLN-05 | Como desenvolvedor, quero treinar um classificador SVM sobre o TF-IDF para identificar intenções | 8 | Crítica |
| PLN-06 | Como desenvolvedor, quero extrair entidades (serviço, data, hora) do texto para alimentar o fluxo de agendamento | 6 | Crítica |
| PLN-07 | Como desenvolvedor, quero gerar embeddings do catálogo de serviços para realizar busca por similaridade semântica | 6 | Crítica |
| PLN-08 | Como cliente, quero buscar por "montar armário" e receber serviços relevantes de montagem como resultado | 4 | Crítica |
| PLN-11 | Como desenvolvedor, quero implementar um limiar de confiança para o SVM e um fluxo de fallback para intenções não reconhecidas | 4 | Alta |
| QA-08 | Como desenvolvedor, quero aplicar **Partição de Equivalência** e **Análise de Valor Limite** para o teste de caixa preta | 4 | Alta |
| QA-09 | Como desenvolvedor, quero criar o **Diagrama UML de Estados** do fluxo de Check-in/Check-out | 3 | Alta |
| QA-10 | Como desenvolvedor, quero criar casos de teste para cada estado, transição e caminho do diagrama UML | 4 | Alta |

**Total estimado:** 62 horas

### Tarefas-Chave da Sprint
1. Integração do microfone e captura de áudio
2. Configuração do Azure Speech-to-Text
3. Implementação do pipeline de NLP (TF-IDF)
4. Treinamento e validação do classificador SVM
5. Implementação da busca semântica por embeddings
6. Extração de entidades do texto
7. Criação dos casos de teste de caixa preta e diagrama UML

### Riscos e Mitigações
| Risco | Impacto | Mitigação |
|-------|---------|-----------|
| Atraso na integração do Azure Speech | Alto | Ter fallback de texto; testar API com dados de exemplo |
| Baixa acurácia do SVM | Médio | Aumentar dataset de treino, testar diferentes parametrizações |
| Complexidade na extração de entidades | Médio | Usar expressões regulares como fallback |

---

## SPRINT 3: INFRAESTRUTURA AZURE (21/09 a 02/10)

### Objetivo da Sprint
Provisionar e configurar todos os recursos na Azure para a aplicação em produção.

### Itens do Backlog

| ID | História de Usuário | Estimativa (horas) | Prioridade |
|----|---------------------|-------------------|------------|
| INFRA-01 | Como desenvolvedor, quero provisionar um **Azure App Service** para hospedar o backend Express/Node.js | 4 | Crítica |
| INFRA-02 | Como desenvolvedor, quero provisionar um **Azure Database for PostgreSQL** para os dados estruturados | 4 | Crítica |
| INFRA-03 | Como desenvolvedor, quero provisionar uma instância do **Azure Cosmos DB** para dados não-relacionais | 4 | Crítica |
| INFRA-04 | Como desenvolvedor, quero configurar um **Azure Blob Storage** para armazenar imagens | 4 | Alta |
| INFRA-05 | Como desenvolvedor, quero configurar o **Azure Key Vault** para armazenar credenciais | 6 | Crítica |
| INFRA-06 | Como desenvolvedor, quero configurar um **Azure Static Web App** para publicar o frontend web | 4 | Alta |
| INFRA-07 | Como desenvolvedor, quero criar um **Plano de Serviço de Aplicativo** adequado e estimar custos | 3 | Alta |
| INFRA-09 | Como desenvolvedor, quero configurar o **Azure Application Insights** para monitoramento | 4 | Alta |
| INFRA-11 | Como desenvolvedor, quero configurar as **variáveis de ambiente** no App Service | 4 | Crítica |
| SEC-01 | Como desenvolvedor, quero garantir que todas as chaves de API estejam somente no backend ou no Key Vault | 4 | Crítica |
| SEC-06 | Como desenvolvedor, quero **criptografar dados sensíveis** no banco de dados PostgreSQL | 6 | Alta |

**Total estimado:** 55 horas

### Tarefas-Chave da Sprint
1. Provisionamento do Azure App Service e configuração do backend
2. Provisionamento do PostgreSQL e migração dos dados
3. Provisionamento do Cosmos DB para dados não-relacionais
4. Configuração do Blob Storage para imagens
5. Setup do Key Vault e armazenamento de credenciais
6. Configuração do Static Web App para frontend
7. Configuração do Application Insights
8. Criptografia de dados sensíveis

### Riscos e Mitigações
| Risco | Impacto | Mitigação |
|-------|---------|-----------|
| Conta Azure com limitações de crédito | Médio | Solicitar créditos educacionais; otimizar recursos |
| Dificuldade na configuração do Key Vault | Alto | Seguir tutoriais oficiais; pedir ajuda do professor |
| Atraso na migração de dados | Médio | Ter script de rollback; testar em ambiente menor |

---

## SPRINT 4: CHATBOT COMPLETO + SISTEMA DE CHAMADOS (05/10 a 16/10)

### Objetivo da Sprint
Integrar o classificador de intenções ao fluxo completo de agendamentos e implementar o sistema de chamados.

### Itens do Backlog

| ID | História de Usuário | Estimativa (horas) | Prioridade |
|----|---------------------|-------------------|------------|
| CHAT-04 | Como cliente, quero que o chatbot me guie na coleta de dados para agendar um serviço | 8 | Crítica |
| CHAT-05 | Como cliente, quero consultar meus agendamentos pelo chatbot e ver o ID e status de cada um | 4 | Alta |
| CHAT-06 | Como cliente, quero solicitar o cancelamento de um agendamento via chatbot, confirmando a ação | 4 | Alta |
| CHAT-07 | Como cliente, quero solicitar a alteração de data/horário e validar a nova disponibilidade | 6 | Alta |
| CHAT-11 | Como desenvolvedor, quero conectar as respostas do chatbot às regras de negócio para cada intenção classificada pelo SVM | 6 | Alta |
| TICKET-01 | Como cliente, quero abrir um chamado com título, descrição, categoria e prioridade | 4 | Alta |
| TICKET-02 | Como prestador, quero abrir um chamado com título, descrição, categoria e prioridade | 2 | Alta |
| TICKET-03 | Como cliente/prestador, quero visualizar todos os meus chamados com status atual | 4 | Alta |
| TICKET-04 | Como cliente/prestador, quero visualizar os detalhes de um chamado específico | 3 | Alta |
| TICKET-05 | Como cliente/prestador, quero adicionar uma nova mensagem em um chamado aberto | 3 | Alta |
| TICKET-08 | Como admin, quero visualizar todos os chamados em um painel com filtros | 6 | Crítica |
| TICKET-09 | Como admin, quero alterar o status de um chamado (Aberto → Em Análise → Em Atendimento → Resolvido → Fechado) | 4 | Crítica |
| TICKET-10 | Como admin, quero responder a um chamado adicionando uma mensagem | 4 | Crítica |
| TICKET-16 | Como desenvolvedor, quero criar o modelo de dados para chamados | 2 | Crítica |

**Total estimado:** 60 horas

### Tarefas-Chave da Sprint
1. Integração do SVM com as regras de negócio do chatbot
2. Fluxo completo de criação de agendamentos via chat
3. Fluxos de consulta, cancelamento e alteração
4. Criação do modelo de dados para chamados
5. Implementação da abertura de chamados (cliente/prestador)
6. Painel administrativo para gestão de chamados
7. Fluxo de alteração de status e respostas

### Riscos e Mitigações
| Risco | Impacto | Mitigação |
|-------|---------|-----------|
| Complexidade na integração do SVM com o chatbot | Alto | Criar camada intermediária de orquestração |
| Frontend do painel admin muito extenso | Médio | Priorizar funcionalidades básicas; entregar extras na Sprint 6 |
| Falta de tempo para testes do sistema de chamados | Médio | Incluir testes manuais rápidos; testes automatizados na Sprint 5 |

---

## SPRINT 5: JORNADA DE ATENDIMENTO + CI/CD (19/10 a 30/10)

### Objetivo da Sprint
Implementar geolocalização em tempo real, evidências fotográficas, notificações e pipeline de CI/CD.

### Itens do Backlog

| ID | História de Usuário | Estimativa (horas) | Prioridade |
|----|---------------------|-------------------|------------|
| GEO-01 | Como prestador, quero iniciar o compartilhamento da minha localização ao mudar o status para "A Caminho" | 6 | Crítica |
| GEO-02 | Como cliente, quero visualizar o prestador em um mapa em tempo real | 6 | Crítica |
| GEO-04 | Como desenvolvedor, quero integrar a API do Google Maps ou MapLibre para exibir mapa | 6 | Crítica |
| GEO-05 | Como desenvolvedor, quero implementar WebSockets (Socket.io) para transmitir localização em tempo real | 8 | Crítica |
| GEO-07 | Como desenvolvedor, quero solicitar e registrar o consentimento do usuário para compartilhamento de localização | 3 | Alta |
| EVI-01 | Como prestador, quero tirar uma foto do local antes de iniciar o serviço e anexar ao agendamento | 4 | Crítica |
| EVI-02 | Como prestador, quero tirar uma foto do local depois de concluir o serviço e anexar ao agendamento | 4 | Crítica |
| EVI-04 | Como desenvolvedor, quero integrar a câmera do dispositivo (React Native Camera) | 6 | Crítica |
| NOT-04 | Como desenvolvedor, quero integrar Firebase Cloud Messaging para enviar notificações push | 4 | Alta |
| QA-01 | Como desenvolvedor, quero configurar um workflow no GitHub Actions que execute os testes a cada push/PR | 4 | Crítica |
| QA-03 | Como desenvolvedor, quero criar testes para o fluxo de Check-in/Check-out | 4 | Alta |
| QA-05 | Como desenvolvedor, quero automatizar os casos de teste com Jest, garantindo cobertura mínima de 85% | 6 | Crítica |
| QA-11 | Como desenvolvedor, quero configurar a pipeline para fazer o deploy automático na Azure após os testes passarem | 3 | Alta |
| QA-12 | Como desenvolvedor, quero configurar o GitHub Actions para bloquear merges com cobertura abaixo de 85% | 2 | Crítica |
| QA-16 | Como desenvolvedor, quero configurar GitHub Action para verificar a cobertura de testes | 2 | Crítica |
| JOR-02 | Como prestador, quero alterar o status do agendamento para "A Caminho" e confirmar antes de iniciar o rastreamento | 3 | Alta |
| JOR-03 | Como desenvolvedor, quero expandir o diagrama UML de Estados para incluir o estado "A Caminho" | 2 | Alta |

**Total estimado:** 73 horas (capacidade: 56 horas - **priorizar itens críticos**)

### Itens a Serem Priorizados (Corte)

| ID | Motivo |
|----|--------|
| GEO-06 | Histórico de localização - pode ser adiado para Sprint 6 |
| TICKET-11 | Anexos em chamados - pode ser adiado para Sprint 6 |
| QA-20 | Testes de integração - pode ser iniciado, mas concluído na Sprint 6 |

### Tarefas-Chave da Sprint
1. Implementação do WebSocket para geolocalização em tempo real
2. Integração do mapa (Google Maps/MapLibre)
3. Compartilhamento de localização do prestador
4. Captura e upload de fotos (antes/depois)
5. Configuração do Firebase Cloud Messaging
6. Configuração do pipeline CI/CD no GitHub Actions
7. Configuração do Jest e cobertura mínima de 85%
8. Deploy automático na Azure

### Riscos e Mitigações
| Risco | Impacto | Mitigação |
|-------|---------|-----------|
| WebSocket com problemas de conexão | Alto | Implementar fallback com polling |
| API de mapas com limitações ou custos | Médio | Usar MapLibre (open-source) como alternativa |
| FCM com problemas de configuração | Médio | Implementar notificações por e-mail como fallback |
| CI/CD com configuração complexa | Alto | Seguir templates do GitHub Actions; testar gradualmente |

---

## SPRINT 6: QUALIDADE, ESTABILIZAÇÃO E DEPLOY FINAL (02/11 a 13/11)

### Objetivo da Sprint
Finalizar entregas da disciplina de Qualidade, estabilizar o sistema, documentar e preparar para as apresentações finais.

### Itens do Backlog

| ID | História de Usuário | Estimativa (horas) | Prioridade |
|----|---------------------|-------------------|------------|
| QA-04 | Como desenvolvedor, quero executar testes de regressão antes de cada release | 4 | Média |
| QA-18 | Como desenvolvedor, quero configurar GitHub Action para analisar complexidade ciclomática | 3 | Média |
| QA-19 | Como desenvolvedor, quero integrar SonarQube para monitorar qualidade do código | 4 | Média |
| QA-20 | Como desenvolvedor, quero escrever testes de integração para os endpoints críticos da API | 8 | Alta |
| QA-22 | Como desenvolvedor, quero planejar e executar um teste de carga básico | 4 | Baixa |
| SEC-05 | Como desenvolvedor, quero implementar logs de auditoria para operações críticas | 6 | Média |
| INFRA-08 | Como desenvolvedor, quero documentar a arquitetura de nuvem (diagrama, serviços, variáveis, deploy) | 6 | Alta |
| INFRA-10 | Como desenvolvedor, quero configurar backup automatizado do PostgreSQL e Cosmos DB | 3 | Média |
| DOC-01 | Como desenvolvedor, quero documentar a arquitetura, as rotas da API, o pipeline e o manual do usuário | 8 | Alta |
| CHK-06 | Como desenvolvedor, quero garantir que códigos inválidos ou já utilizados sejam rejeitados | 2 | Média |
| CHK-07 | Como desenvolvedor, quero registrar histórico de Check-in/Check-out para auditoria | 3 | Média |
| TICKET-13 | Como admin, quero fechar um chamado após resolvido e registrar a solução | 2 | Crítica |
| TICKET-17 | Como desenvolvedor, quero registrar um log de auditoria para cada alteração de status do chamado | 3 | Média |
| UX-06 | Como desenvolvedor, quero validar a implementação contra o Figma e ajustar inconsistências | 4 | Média |
| UX-14 | Como desenvolvedor, quero executar testes automatizados de acessibilidade | 3 | Média |
| DOC-02 | Como equipe, quero elaborar o panfleto (folder) promocional para a "Mostra" | 6 | Média |

**Total estimado:** 68 horas (capacidade: 56 horas - **priorizar itens críticos**)

### Itens a Serem Priorizados (Corte)

| ID | Motivo |
|----|--------|
| QA-22 | Teste de carga - pode ser opcional/extra |
| QA-18 | Complexidade ciclomática - pode ser configurado, mas não bloqueante |
| INFRA-10 | Backup automatizado - pode ser configurado posteriormente |

### Tarefas-Chave da Sprint
1. Finalização dos testes de integração e cobertura de 85%
2. Correção de bugs e estabilização geral
3. Documentação técnica completa (arquitetura, API, pipeline)
4. Manual do usuário
5. Panfleto promocional
6. Revisão final contra Figma
7. Deploy final em produção
8. Preparação para apresentações (21/11)

### Riscos e Mitigações
| Risco | Impacto | Mitigação |
|-------|---------|-----------|
| Documentação extensa não ser finalizada | Médio | Iniciar documentação desde a Sprint 1, manter atualizada |
| Bugs críticos surgindo no final | Alto | Alocar tempo para testes exploratórios na Sprint 6 |
| Apresentação não estar preparada | Médio | Ensaio da apresentação com 1 semana de antecedência |

---

## SPRINT 7 (BUFFER): AJUSTES FINOS E MOSTRA (16/11 a 04/12)

### Objetivo da Sprint
Buffer para ajustes de última hora, correções não previstas e preparação final para a Mostra.

### Itens do Backlog (Priorizados)

| ID | História de Usuário | Estimativa (horas) |
|----|---------------------|-------------------|
| Correções de bugs críticos identificados nas sprints anteriores | 16 |
| Ajustes finos na interface (UX) | 8 |
| Preparação do ambiente de demonstração (Mostra) | 8 |
| Ensaios da apresentação | 8 |
| Ajustes na documentação com base em feedback | 6 |
| Validação final com a equipe | 10 |

**Total estimado:** 56 horas

---

## RESUMO DE CAPACIDADE E ESTIMATIVAS

| Sprint | Período | Horas Disponíveis | Horas Estimadas | Status |
|--------|---------|-------------------|-----------------|--------|
| **Sprint 1** | 24/08 - 04/09 | 56h | 60h | ⚠️ Ajuste necessário |
| **Sprint 2** | 07/09 - 18/09 | 56h | 62h | ⚠️ Ajuste necessário |
| **Sprint 3** | 21/09 - 02/10 | 56h | 55h | ✅ Dentro da capacidade |
| **Sprint 4** | 05/10 - 16/10 | 56h | 60h | ⚠️ Ajuste necessário |
| **Sprint 5** | 19/10 - 30/10 | 56h | 73h | ⚠️ Priorizar itens críticos |
| **Sprint 6** | 02/11 - 13/11 | 56h | 68h | ⚠️ Priorizar itens críticos |
| **Sprint 7 (Buffer)** | 16/11 - 04/12 | 56h | 56h | ✅ Buffer e Mostra |

---

**www.delbicos.com.br**