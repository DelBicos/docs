<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="assets/DelBicos_git.png">
      <source media="(prefers-color-scheme: light)" srcset="assets/DelBicos_LogoH.png">
      <img alt="Shows a black logo in light color mode and a white one in dark color mode." src="assets/DelBicos_git.png">
    </picture>
</p>

<p align="center">
  <a href="#-about">About</a> |
  <a href="#-arquitetura">Arquitetura</a> |
  <a href="#-documentação">Documentação</a> |
  <a href="#-entregas-de-sprints">Sprints</a> |
  <a href="#-prototype">Protótipo</a> |
  <a href="#️-tecnologies">Tecnologias</a> |
  <a href="#-team">Time</a> |
  <a href="#-requisitos-funcionais-rf">Requisitos</a> |
  <a href="https://github.com/fershibli/DelBicosV2">App</a> |
  <a href="https://github.com/DelBicos/backend">API</a>
</p>

# 💻 About

DelBicos (Delivery de Bicos) conecta clientes e trabalhadores informais da mesma vizinhança. O produto em execução é um aplicativo Expo (React Native) para Android, iOS e web, com uma API em Node.

Profissionais informais, de diversas vertentes, têm muita dificuldade para adquirir clientes na sua região de atuação, muitas vezes tendo que se deslocar por longas distâncias para chegar aos seus clientes, quando não o inverso. Enquanto que na outra ponta, clientes que se mudaram há pouco tempo para a região encontram muita dificuldade e insegurança ao procurar por profissionais confiáveis para realizar tarefas em suas residências.

Ao solucionar esse problema, notaria-se também os seguintes benefícios para a sociedade:

- A diminuição do translado entre cliente e profissional, que causaria a redução da emissão de gases do efeito estufa nesta atividade;
- O aumento de demanda para profissionais de diversas comunidades, contribuindo com a redução da desigualdade social;
- A integração de indivíduos no ciclo de consumo de serviços locais, levando à melhora na qualidade de vida;
- O acompanhamento das atividades e avaliações, levando a melhor confiabilidade e segurança.

> Os dois grupos destacados no problema descrito, compõem o público-alvo deste projeto.

> > 📌 **Status:** $\color{Apricot}{Em\ desenvolvimento}$

## 🏗️ Arquitetura

Dois repositórios de código e este, de documentação.

| Parte | Repositório | O que é |
| --- | --- | --- |
| App | [DelBicosV2](https://github.com/fershibli/DelBicosV2) | Expo 54, React Native e TypeScript. Telas em `public` e `private` (cliente, profissional, admin e chat). Só as stores Zustand chamam a API. |
| API | [DelBicos/backend](https://github.com/DelBicos/backend) | Express e TypeScript. Rotas entregam o pedido ao controller. Regra de negócio e integração externa ficam em `services`. Postgres (Sequelize) guarda o negócio. MongoDB guarda chat e log de login. |
| NLP | pasta `nlp-service` da API | Classificador em Python (TF-IDF + SVM) e busca semântica. Não é um modelo generativo. |
| Tempo real | API + app | Socket.io no mesmo servidor HTTP da API. Pagamentos no Stripe. Arquivos no Azure Blob Storage. |

O app não é fronteira de segurança: a API repete a validação e protege a regra de negócio. O detalhe das camadas está em `docs/architecture.md` de cada repositório de código.

## 📄 Documentação

Os arquivos deste repositório, por semestre:

| Semestre | Arquivos |
| --- | --- |
| 1 | [Entrega](semester1/DOC_ENTREGA.pdf) |
| 2 | [Entrega](semester2/DOC_ENTREGA.pdf) · [Apresentação](semester2/APRESENTATION.pptx) |
| 3 | [Gestão ágil](semester3/DOC_GESTAO_AGIL.docx) · [IHC](semester3/DOC_IHC.docx) · [Técnicas de programação](semester3/DOC_TECNICAS_PROGRAMACAO.docx) · [Avaliação heurística](semester3/DOC_AVAL_HEURISTICA.docx) |
| 4 | [Projeto](semester4/DOC_PROJETO.docx) · [UX](semester4/DOC_UX.docx) · [Apresentação](semester4/APRESENTATION.pptx) |
| 5 | [Apresentação](semester5/APRESENTATION.pptx) |
| 6 | [Usuário](semester6/DOC_USUARIO.pdf) · [Técnica](semester6/DOC_TECNICA.pdf) · [Projeto](semester6/DOC_PROJETO.pdf) · [Desenvolvimento](semester6/DOC_DESENVOLVIMENTO.pdf) |

Os requisitos também estão em [RF_RNF.pdf](RF_RNF.pdf).

```
Delbicos-Docs
├── semester1 … semester6   # entregas das disciplinas
├── assets                  # logo e imagens de sprint
├── RF_RNF.pdf
└── README.md
```

<br>

## 🏁 Entregas de Sprints

| Sprint |    Período    | Entregas                                                                                                                                                                                                                                                                              |    Status    |
| :----: | :-----------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :----------: |
|   01   | 04/06 - 20/06 | Figma do protótipo de agendar e pagar serviço, Página de Feed, Header, Endpoint GET de profissionais com filtros opcionais `<br>` (termo pesquisado, localização, categoria, subcategoria, data_inicio, data_fim) e com ordenação (relevância, avaliação, distância, disponibilidade) | ✅ Concluído |
|   02   | 10/06 - 17/06 | Página de Meus Agendamentos, Figma do protótipo de Página de Login, Página de Login por E-mail e Senha,`<br>` dois endpoints POST de login por senha, endpoint POST de cadastro, endpoint POST de cancelar agendamento                                                                | ✅ Concluído |
|   03   | 17/06 - 24/06 | Interações do protótipo do Figma, endpoint POST de cadastro de parceiro,`<br>` endpoint POST de aceitar agendamento, endpoint POST de editar disponibilidade                                                                                                                          | ✅ Concluído |
|   04   | 24/06 - 25/08 | Implementação de Envio de E-mails Automatizados                                                                                                                                                                                                                                       | ✅ Concluído |
|   05   | 26/08 - 08/09 | Implementação de Sistema de Agendamento com Calendário                                                                                                                                                                                                                                | ✅ Concluído |
|   06   | 09/09 - 15/09 | Implementação de Geolocalização e Mapas                                                                                                                                                                                                                                               | ✅ Concluído |
|   07   | 16/09 - 22/09 | Implementação de Upload e Armazenamento de Arquivos                                                                                                                                                                                                                                   | ✅ Concluído |
|   08   | 23/09 - 06/10 | Implementação de Sistema de Avaliações ou Comentários                                                                                                                                                                                                                                 | ✅ Concluído |
|   09   | 07/10 - 13/10 | Implementação de Geração de Entrega de Relatórios em PDF                                                                                                                                                                                                                              | ✅ Concluído |
|   10   | 14/10 - 20/10 | Implementação de Envio de Notificações em Tempo Real                                                                                                                                                                                                                                  | ✅ Concluído |
|   11   | 21/10 - 03/11 | Implementação de Integração com API de Pagamentos                                                                                                                                                                                                                                     | ✅ Concluído |
|   12   | 04/11 - 10/11 | Implementação de IExportação de Dados para Excel/CSV                                                                                                                                                                                                                                  | ✅ Concluído |
|   13   | 11/11 - 17/11 | Implementação de Visualização com Gráficos                                                                                                                                                                                                                                            | ✅ Concluído 

## 🎨 Prototype

O protótipo no Figma cobre a entrada, a busca de profissionais, o cadastro, o login, o agendamento e o pagamento. O produto em execução é o aplicativo e a API da seção de arquitetura, não um site ainda por fazer.

🔗 👉 [![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white)](https://www.figma.com/proto/1xZfYHmDwbr9aaqoh5ddxN/DelBicosV2?node-id=1364-969&t=tZpzceJg13szkrPk-1)

<br>

## 🛠️ Tecnologies

App: Expo, React Native, TypeScript e Zustand. API: Node, Express, Sequelize, PostgreSQL e MongoDB. Em volta: Stripe, Socket.io, Azure Blob Storage, Docker e o serviço de NLP em Python.

![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white) ![Expo](https://img.shields.io/badge/Expo-000020?style=for-the-badge&logo=expo&logoColor=white) ![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB) ![Node](https://img.shields.io/badge/Node%20js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white) ![Express](https://img.shields.io/badge/Express%20js-000000?style=for-the-badge&logo=express&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

<br>

## 👥 Team

|                        Nome                        | Função                                 |
| :------------------------------------------------: | -------------------------------------- |
|  [Fernando Chibli](https://github.com/fershibli)   | _CTO e Desenvolvedor FullStack_        |
| [Douglas Wenzel](https://github.com/douglaswenzel) | _Scrum Master e Desenvolvedor FullStack_ |
|   [Isabel Maito](https://github.com/isabelmaito)   | _Designer e Desenvolvedora FullStack_  |

<br>

## 🚀 Requisitos Funcionais (RF)

| ID | Funcionalidade | Descrição Detalhada |
| :---: | :--- | :--- |
| **RF01** |  **Alternância de Perfil** | Troca rápida entre a visão 'Cliente' e 'Parceiro' via Switch no Menu. |
| **RF02** |  **Onboarding Parceiro** | Cadastro completo: especialidades, bio e envio de documentos profissionais. |
| **RF03** |  **Gestão de Bicos** | CRUD completo (Criar, Listar, Editar e Deletar) dos serviços oferecidos. |
| **RF04** |  **Filtro de Geolocalização** | Definição de raio de atuação (KM) para recebimento de pedidos próximos. |
| **RF05** |  **Gestão de Status** | Fluxo: Aceitar → A Caminho → Iniciar → Concluir. |
| **RF06** |  **Agenda Dinâmica** | Visualização de serviços confirmados em lista ou calendário.  |
| **RF07** |  **Chat Contextual** | Canal de texto entre as partes após a confirmação do serviço. |
| **RF08** |  **Check-out de Segurança** | Finalização via código OTP ou confirmação mútua. |
| **RF09** |  **Portfólio (Mídia)** | Upload e exibição de fotos de serviços realizados no perfil. |
| **RF10** |  **Relatórios de Ganhos** | Exportação de histórico e valores em formatos PDF ou Excel. |

---

## ⚙️ Requisitos Não-Funcionais (RNF)

| ID | Atributo | Premissa Técnica |
| :---: | :--- | :--- |
| **RNF01** |  **Responsividade** | Interface adaptável para telas de 5" até 11" (Tablets). |
| **RNF02** |  **Persistência Local** | Rascunho e sessão no aparelho com Async Storage (Zustand persist). |
| **RNF03** |  **Sincronização** | Upload automático via API assim que a conexão for restabelecida.  |
| **RNF04** |  **Segurança JWT** | Controle de acesso (Roles) nos endpoints do Backend. |
| **RNF05** |  **Performance Mídia** |Compressão automática de imagens antes do upload. |
| **RNF06** |  **Validação Robusta** | Formulário no app com react-hook-form. A API valida de novo; o cliente não é fronteira de segurança. |
| **RNF07** |  **Cloud Sync** | Latência de sincronização com a nuvem inferior a 2 segundos. |
| **RNF08** |  **Acessibilidade** | A interface deve possuir suporte a intérprete virtual de Libras e manter um contraste no modo escuro. |

---
