# PRODUCT BACKLOG DELBICOS

## 2º Semestre/2026
 
**Equipe:** Desenvolvimento DelBicos  
**Documento:** Product Backlog v1.0  
**Data de elaboração:** 21/08/2026  
**Início do planejamento:** 24/08/2026 
**Duração da sprint:** 15 dias  
**Total de sprints:** 5  
**Término previsto:** 21/11/2026  

---

## 1. VISÃO GERAL

### 1.1 Problema
O usuário pode ter dificuldade para encontrar o serviço correto sem conhecer seu nome exato, gerenciar agendamentos rapidamente e interagir quando não deseja ou não consegue digitar.

### 1.2 Proposta de valor
Para clientes autenticados que precisam contratar e administrar serviços, o Chatbot Multimodal oferece interação por texto ou voz, identifica intenções de agendamento e realiza busca semântica no catálogo. Diferentemente de um chat com IA generativa, as decisões são tomadas por PLN clássico e regras de negócio.

### 1.3 Objetivos específicos

| ID | Objetivo |
|----|----------|
| OE-01 | Permitir comandos por texto e voz |
| OE-02 | Converter fala em texto em português |
| OE-03 | Classificar intenção e extrair dados relevantes para o fluxo |
| OE-04 | Buscar serviços por significado e exibir resultados relevantes |
| OE-05 | Garantir confirmação, segurança e alternativa por texto |

---

## 2. MARCOS ACADÊMICOS

| Entrega | Data | Descrição |
|---------|------|-----------|
| Entrega 1 | 21/09/2026 | Protótipo: Voz → Transcrição → PLN → Busca Semântica → Resultados |
| Entrega 2 | 21/11/2026 | Chatbot completo com gestão de agendamentos |

---

## 3. CRONOGRAMA DE SPRINTS

| Sprint | Início | Término | Foco Principal | Marco |
|--------|--------|---------|----------------|-------|
| Sprint 1 | 24/08/2026 | 07/09/2026 | Fundação e Correções Críticas | - |
| Sprint 2 | 08/09/2026 | 22/09/2026 | PLN: Voz + Busca Semântica | Entrega 1 (21/09) |
| Sprint 3 | 23/09/2026 | 07/10/2026 | Chatbot Completo | - |
| Sprint 4 | 08/10/2026 | 22/10/2026 | Check-in/out + UX/Figma | - |
| Sprint 5 | 23/10/2026 | 06/11/2026 | Qualidade e Estabilização | Preparação Entrega 2 |
| Buffer | 07/11/2026 | 21/11/2026 | Ajustes finais e apresentação | Entrega 2 (21/11) |

---

## 4. PRODUCT BACKLOG

### 4.1 ÉPICO 1: Fundação do Agendamento & Chatbot Essencial

**Objetivo:** Corrigir a base do sistema de agendamento, tornando-o identificável e com informações completas, e evoluir o chatbot para coletar dados críticos que faltam no fluxo principal.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| AG-01 | Como cliente, quero que meu agendamento tenha um ID curto e aleatório para poder identificá-lo facilmente sem expor dados sequenciais. | Alta | Correção | 1 |
| AG-02 | Como desenvolvedor, quero substituir o uso do ID sequencial pelo novo ID curto em todo o backend para garantir a consistência da informação. | Alta | Técnica | 1 |
| CHAT-01 | Como cliente, quero informar meu endereço durante o fluxo de agendamento no chatbot para que o profissional saiba onde ir. | Alta | Funcional | 1 |
| CHAT-02 | Como cliente, quero selecionar minha forma de pagamento no chatbot para concluir a solicitação do serviço. | Alta | Funcional | 1 |
| CHAT-03 | Como profissional, quero ver o endereço e a forma de pagamento do cliente nos detalhes do agendamento para me preparar para o atendimento. | Alta | Funcional | 1 |
| AG-03 | Como cliente, quero ver o ID curto no meu histórico de agendamentos para poder me referir a ele em futuras interações. | Alta | Funcional | 1 |
| AG-04 | Como cliente, quero visualizar todas as informações do agendamento no histórico para ter uma visão completa. | Alta | Funcional | 1 |
| AG-05 | Como desenvolvedor, quero garantir a consistência do ID curto entre chat, histórico e backend. | Média | Técnica | 3 |

**Critérios de aceite:**
- Usuário consegue identificar um agendamento por um código curto e não sequencial
- ID é exibido em todos os pontos relevantes do sistema
- Endereço e pagamento são coletados e exibidos corretamente

---

### 4.2 ÉPICO 2: Núcleo de PLN - Voz & Busca Semântica (Entrega 1)

**Objetivo:** Cumprir o marco acadêmico de 21/09, entregando o pipeline clássico de PLN que recebe voz, transcreve, entende a intenção e realiza busca semântica.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| PLN-01 | Como cliente, quero usar o microfone para gravar um comando de voz e enviá-lo para processamento. | Crítica | Funcional | 2 |
| PLN-02 | Como desenvolvedor, quero integrar um serviço de Speech-to-Text para converter o áudio do usuário em texto em português. | Crítica | Técnica | 2 |
| PLN-03 | Como cliente, quero ver a transcrição da minha fala para confirmar que o sistema entendeu corretamente. | Alta | Funcional | 2 |
| PLN-04 | Como desenvolvedor, quero implementar um pipeline de PLN (normalização, tokenização, stemming, TF-IDF) para processar o texto de forma explicável. | Crítica | Técnica | 2 |
| PLN-05 | Como desenvolvedor, quero criar um modelo de classificação para identificar as intenções de agendar, cancelar, alterar e buscar. | Crítica | Técnica | 2 |
| PLN-06 | Como desenvolvedor, quero extrair entidades como serviço, data e horário do texto para alimentar o fluxo de agendamento. | Crítica | Técnica | 2 |
| PLN-07 | Como desenvolvedor, quero gerar embeddings do catálogo de serviços e das buscas para realizar busca por significado. | Crítica | Técnica | 2 |
| PLN-08 | Como cliente, quero buscar por "montar armário" e receber serviços relevantes de montagem como resultado. | Crítica | Funcional | 2 |
| PLN-09 | Como desenvolvedor, quero documentar o pipeline de PLN para a avaliação acadêmica. | Alta | Técnica | 2 |

**Critérios de aceite:**
- Ao falar "preciso de alguém para montar um armário", o sistema exibe a transcrição e serviços relevantes
- Com permissão negada, o usuário recebe mensagem clara e consegue usar texto
- Fluxo demonstrável em navegador e emulador Android
- Nenhuma chave de transcrição é exposta no frontend

---

### 4.3 ÉPICO 3: Gestão Completa no Chatbot (Entrega 2)

**Objetivo:** Evoluir o protótipo de PLN em um chatbot completo, integrando o fluxo de gestão de agendamentos.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| CHAT-04 | Como cliente, quero que o chatbot me guie na coleta de dados para agendar um serviço, solicitando o que estiver faltando. | Alta | Funcional | 3 |
| CHAT-05 | Como cliente, quero consultar meus agendamentos pelo chatbot, vendo o ID curto e o status de cada um. | Alta | Funcional | 3 |
| CHAT-06 | Como cliente, quero solicitar o cancelamento de um agendamento e confirmar a ação antes que ela seja concluída. | Alta | Funcional | 3 |
| CHAT-07 | Como cliente, quero solicitar a alteração de data/horário e validar a nova disponibilidade antes de confirmar. | Alta | Funcional | 3 |
| CHAT-08 | Como cliente, quero que o fluxo do chatbot (texto ou voz) seja o mesmo, garantindo consistência. | Alta | Técnica | 3 |
| CHAT-09 | Como cliente, quero continuar usando o chat por texto se a voz falhar, sem perder minha sessão. | Alta | Funcional | 3 |
| CHAT-10 | Como desenvolvedor, quero implementar idempotência para que reenvios não criem ações duplicadas. | Média | Técnica | 3 |

**Critérios de aceite:**
- "Quero agendar uma limpeza amanhã às 14h" inicia a coleta de dados e valida disponibilidade
- "Quais são meus agendamentos?" mostra somente os do usuário autenticado
- "Cancelar agendamento 15" pede confirmação antes de alterar o banco
- O mesmo fluxo opera quando a frase vem de voz ou de texto

---

### 4.4 ÉPICO 4: Fluxo de Atendimento - Check-in / Check-out

**Objetivo:** Adicionar a camada de confirmação do serviço, fechando o ciclo do agendamento.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| CHK-01 | Como desenvolvedor, quero gerar um código de confirmação único e seguro para cada agendamento. | Alta | Funcional | 4 |
| CHK-02 | Como cliente/profissional, quero visualizar o código de confirmação do atendimento. | Alta | Funcional | 4 |
| CHK-03 | Como profissional/cliente, quero validar o código para realizar o Check-in. | Alta | Funcional | 4 |
| CHK-04 | Como profissional/cliente, quero validar o código para realizar o Check-out. | Alta | Funcional | 4 |
| CHK-05 | Como desenvolvedor, quero que o status do agendamento seja atualizado automaticamente. | Alta | Funcional | 4 |
| CHK-06 | Como desenvolvedor, quero garantir que códigos inválidos ou reutilizados sejam rejeitados. | Média | Técnica | 5 |
| CHK-07 | Como desenvolvedor, quero registrar histórico de Check-in/Check-out. | Média | Técnica | 5 |

**Critérios de aceite:**
- Código é gerado e associado ao agendamento
- Validação correta altera o status do atendimento
- Códigos inválidos ou já usados são rejeitados

---

### 4.5 ÉPICO 5: Experiência do Usuário & Consistência Visual

**Objetivo:** Alinhar o chatbot ao padrão visual definido no Figma.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| UX-01 | Como designer, quero auditar a interface atual e compará-la com o Figma. | Alta | Técnica | 4 |
| UX-02 | Como desenvolvedor, quero adaptar layout e componentes ao design system. | Alta | Técnica | 4 |
| UX-03 | Como desenvolvedor, quero implementar estados de interação conforme o Figma. | Alta | Técnica | 4 |
| UX-04 | Como cliente, quero usar o chat de forma confortável no celular e navegador. | Média | Funcional | 4 |
| UX-05 | Como desenvolvedor, quero corrigir o fluxo "Ver agenda" que está com problemas. | Alta | Correção | 1 |
| UX-06 | Como desenvolvedor, quero validar a implementação contra o Figma. | Média | Técnica | 5 |
| UX-07 | Como desenvolvedor, quero ajustar inconsistências encontradas. | Média | Técnica | 5 |

**Critérios de aceite:**
- Chat funcional e visualmente alinhado ao Figma
- Fluxos críticos testados e responsivos
- Navegação corrigida após pagamento

---

### 4.6 ÉPICO 6: Qualidade, Segurança & Estabilização

**Objetivo:** Garantir robustez, segurança e qualidade do código.

| ID | História de Usuário | Prioridade | Tipo | Sprint |
|----|---------------------|------------|------|--------|
| QA-01 | Como desenvolvedor, quero configurar pipeline de CI/CD com linters e testes. | Alta | Técnica | 5 |
| QA-02 | Como desenvolvedor, quero escrever testes para o fluxo de agendamento. | Alta | Técnica | 1 |
| QA-03 | Como desenvolvedor, quero criar testes para Check-in/Check-out. | Alta | Técnica | 4 |
| QA-04 | Como desenvolvedor, quero executar testes de regressão. | Média | Técnica | 5 |
| QA-05 | Como desenvolvedor, quero configurar cobertura mínima de testes. | Média | Técnica | 5 |
| SEC-01 | Como desenvolvedor, quero garantir chaves de API somente no backend. | Crítica | Técnica | 2 |
| SEC-02 | Como desenvolvedor, quero implementar autenticação e rate limit nas rotas. | Alta | Técnica | 2 |
| SEC-03 | Como desenvolvedor, quero garantir que áudio e transcrição não sejam logados. | Alta | Técnica | 2 |
| DOC-01 | Como desenvolvedor, quero documentar arquitetura, rotas e pipeline. | Alta | Técnica | 5 |
| UX-08 | Como desenvolvedor, quero definir estratégia para os dois chats existentes. | Média | Estratégica | 5 |

**Critérios de aceite:**
- Pipeline roda automaticamente a cada push/PR
- Cobertura mínima atingida
- Nenhuma chave exposta no frontend
- Documentação completa e atualizada

---

## 5. DEFINIÇÃO DE PRONTO (Definition of Done)

- Código revisado por outro membro da equipe
- Sem segredos ou chaves expostos no código
- Lint e tipagem aprovados
- Teste unitário ou roteiro manual registrado
- Funcionamento validado em web e Android
- Critério de aceite atendido
- Documentação atualizada

---

## 6. RASTREABILIDADE

| História | Requisito Funcional | Requisito Não Funcional |
|----------|---------------------|-------------------------|
| AG-01 a AG-05 | RF-12 | RN-04 |
| CHAT-01 a CHAT-03 | RF-08, RF-11 | - |
| PLN-01 a PLN-09 | RF-V01 a RF-V11 | RNF-V01 a RNF-V10 |
| CHAT-04 a CHAT-10 | RF-C01 a RF-C15 | RNF-C01 a RNF-C10 |
| CHK-01 a CHK-07 | Novo Requisito | Novo Requisito |
| UX-01 a UX-07 | RF-16 | RNF-11 |
| QA-01 a QA-05 | - | RNF-13 |
| SEC-01 a SEC-03 | - | RNF-07, RNF-08, RNF-09 |
| DOC-01 | - | RNF-15 |

---

## 7. RISCOS E MITIGAÇÕES

| Risco | Probabilidade | Impacto | Mitigação |
|-------|---------------|---------|-----------|
| Atraso na integração do Speech-to-Text | Média | Alto | Iniciar Sprint 2 com spike técnico; ter fallback por texto |
| Dificuldade com embeddings e similaridade | Média | Alto | Usar bibliotecas prontas; documentar alternativas |
| Escopo maior que a capacidade da equipe | Alta | Médio | Priorizar histórias Alta/Crítica; cortar Média/Baixa se necessário |
| Problemas com CORS e microfone em mobile | Média | Médio | Testar cedo em dispositivo real; usar HTTPS |
| Falta de alinhamento com Figma | Baixa | Médio | Design review no início da Sprint 4 |

---

## 8. RESUMO POR SPRINT

### Sprint 1 - Fundação e Correções Críticas
**Período:** 24/08/2026 a 07/09/2026

| Épico | Histórias |
|-------|-----------|
| Épico 1 | AG-01, AG-02, AG-03, AG-04, CHAT-01, CHAT-02, CHAT-03 |
| Épico 5 | UX-05 |
| Épico 6 | QA-02 |

**Objetivo da Sprint:** Entregar agendamento com novo ID, histórico funcional, endereço/pagamento funcionando e testes básicos.

---

### Sprint 2 - Entrega de PLN (Marco 1)
**Período:** 08/09/2026 a 22/09/2026

| Épico | Histórias |
|-------|-----------|
| Épico 2 | PLN-01 a PLN-09 (TODAS) |
| Épico 6 | SEC-01, SEC-02, SEC-03 |

**Objetivo da Sprint:** Cumprir o marco acadêmico de 21/09 com o protótipo de voz + PLN + busca semântica funcional e documentado.

---

### Sprint 3 - Chatbot Completo
**Período:** 23/09/2026 a 07/10/2026

| Épico | Histórias |
|-------|-----------|
| Épico 3 | CHAT-04, CHAT-05, CHAT-06, CHAT-07, CHAT-08, CHAT-09, CHAT-10 |
| Épico 1 | AG-05 |
| Épico 6 | DOC-01 (início) |

**Objetivo da Sprint:** Integrar o PLN ao fluxo de agendamento, criando o chatbot completo com gestão de agendamentos e fallback por texto.

---

### Sprint 4 - Atendimento e Experiência do Usuário
**Período:** 08/10/2026 a 22/10/2026

| Épico | Histórias |
|-------|-----------|
| Épico 4 | CHK-01, CHK-02, CHK-03, CHK-04, CHK-05 |
| Épico 5 | UX-01, UX-02, UX-03, UX-04 |
| Épico 6 | QA-03, UX-06 |

**Objetivo da Sprint:** Adicionar o fluxo de atendimento completo (Check-in/Check-out) e alinhar a interface ao padrão Figma.

---

### Sprint 5 - Qualidade e Estabilização
**Período:** 23/10/2026 a 06/11/2026

| Épico | Histórias |
|-------|-----------|
| Épico 4 | CHK-06, CHK-07 |
| Épico 5 | UX-06, UX-07 |
| Épico 6 | QA-01, QA-04, QA-05, DOC-01, UX-08 |

**Objetivo da Sprint:** Garantir qualidade, segurança e documentação. Pipeline automatizado, testes de regressão e cobertura mínima.

---

### Buffer e Apresentação Final
**Período:** 07/11/2026 a 21/11/2026

- Correções de bugs encontrados nos testes de regressão
- Ajustes finais de documentação
- Preparação da apresentação para a banca
- Entrega 2: 21/11/2026

---

## 9. APROVAÇÃO

| Papel | Nome | Data | Assinatura |
|-------|------|------|------------|
| Product Owner | _________ | ___/___/____ | _____________ |
| Scrum Master | _________ | ___/___/____ | _____________ |
| Equipe de Desenvolvimento | _________ | ___/___/____ | _____________ |

---

**Documento elaborado conforme norma ABNT NBR 14724:2011 para trabalhos acadêmicos.**

**Fim do Documento**