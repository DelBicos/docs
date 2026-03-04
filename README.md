#  Delbicos (Docs)

Plataforma mobile para conexão entre **Clientes** e **Parceiros** (prestadores de serviços), focada em agilidade, segurança e praticidade.

---

## 📌 Visão Geral do Projeto
Este repositório armazena a documentação técnica e o mapeamento de requisitos do ecossistema.

---

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
| **RNF02** |  **Persistência Local** | Uso de **SQLite** para armazenamento offline de rascunhos e agenda. |
| **RNF03** |  **Sincronização** | Upload automático via API assim que a conexão for restabelecida.  |
| **RNF04** |  **Segurança JWT** | Controle de acesso (Roles) nos endpoints do Backend. |
| **RNF05** |  **Performance Mídia** |Compressão automática de imagens antes do upload. |
| **RNF06** |  **Validação Robusta** | Uso de **Zod/Yup** (Front) e **Express Validator** (Back). |
| **RNF07** |  **Cloud Sync** | Latência de sincronização com a nuvem inferior a 2 segundos. |
| **RNF08** |  **Acessibilidade** | A interface deve possuir suporte a intérprete virtual de Libras e manter um contraste no modo escuro. |

---
