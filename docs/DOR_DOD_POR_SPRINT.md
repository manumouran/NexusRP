# Definition of Ready (DoR) e Definition of Done (DoD) por Sprint - Critérios Específicos de Qualidade NexusRP

Este documento detalha os critérios de Definição de Pronto (DoR) e Definição de Concluído (DoD) específicos aplicados em cada sprint do projeto NexusRP (Gerenciamento Urbano).

---

## 📋 Sprint 1 - Fundação e Autenticação

| Período | 02/09/2025 a 16/09/2025 |
| :--- | :--- |
| **Meta:** | Estabelecer a arquitetura do projeto (C# / SQL Server) e garantir o acesso seguro da Staff ao painel. |

### Definition of Ready (DoR)
* História de usuário clara: Escrita no formato "Como [papel], eu quero [ação] para [benefício]".
* Modelo de Dados Inicial: A estrutura de tabelas de **Staff** e **Permissões** foi definida no Diagrama de Classe (ARC-03).
* Dependências Técnicas: O ambiente de desenvolvimento **C#/.NET Core** e a instância do **SQL Server** estão configurados e acessíveis.
* Critérios de Aceite Definidos: Os requisitos para considerar o login e as permissões completos estão listados.

### Definition of Done (DoD)

**História NEX-01 (Login de Staff):**
* Interface de login implementada no Frontend.
* API de autenticação criada em C# e testada.
* Criptografia de senha **(bcrypt)** implementada no Backend.
* Geração de **Token JWT** para gerenciamento de sessão.
* Testes unitários escritos para a camada de serviço de autenticação.

**Tarefa ARC-03 (Modelagem de Classe):**
* O **Diagrama de Classe** foi finalizado, revisado e exportado para a pasta `docs/diagrams/`.
* O *Schema* inicial do banco de dados (tabelas de usuário e permissões) foi gerado via **EF Core Migrations**.

---

## 📋 Sprint 2 - Prontuário e Controle Disciplinar

| Período | 17/09/2025 a 01/10/2025 |
| :--- | :--- |
| **Meta:** | Implementar a busca rápida de jogadores e estabelecer a infraestrutura para o registro de denúncias via Discord. |

### Definition of Ready (DoR)
* **Back-end da Sprint 1 em `main`:** O módulo de autenticação está aprovado e no branch principal.
* **Design Aprovado:** O *wireframe* da tela de **Prontuário do Cidadão** (NEX-05) foi revisado pela PO.
* **Endpoints de API Documentados:** Os *endpoints* necessários para buscar e exibir o prontuário foram definidos (e.g., `/api/player/{id}`).
* **Credenciais Discord API:** As chaves de acesso para a integração com o Discord foram obtidas e configuradas em ambiente de desenvolvimento.

### Definition of Done (DoD)

**História NEX-05 (Prontuário Completo):**
* A busca rápida (NEX-04) está funcional por ID e Nome.
* A tela exibe dados **estáticos e financeiros** do jogador em tempo real.
* **Tratamento de Erros:** Mensagens amigáveis para jogadores não encontrados.
* Performance: O tempo de carregamento do prontuário é inferior a **2.5s**.

**História NEX-08 (Integração Discord):**
* O serviço de escuta de *Webhooks* ou *Bots* do Discord foi configurado no C#.
* As denúncias são **persistidas** corretamente no banco de dados, incluindo ID do denunciado e prova.
* **Diagrama de Atividade (ARC-02)** finalizado e revisado.

---

## 📋 Sprint 3 - Gestão e Relatórios

| Período | 02/10/2025 a 16/10/2025 |
| :--- | :--- |
| **Meta:** | Finalizar o controle disciplinar (punições) e entregar o Dashboard administrativo com relatórios iniciais. |

### Definition of Ready (DoR)
* **Base de Prontuários Concluída:** A exibição de dados do jogador (NEX-05) está estável.
* **Permissões de Usuário Definidas:** Os níveis de acesso para Administradores e Moderadores foram definidos (NEX-02).
* **Tipos de Punição Mapeados:** O modelo de dados do banco para Punições (Ban, Mute, Jail) está pronto.
* **Fluxo de Punição Validado:** O fluxo de aplicação de punição (NEX-09) foi validado pela PO.

### Definition of Done (DoD)

**História NEX-09 (Aplicação de Punição):**
* O painel de análise de denúncias está funcional.
* A aplicação de punição é registrada corretamente no **Histórico Disciplinar** do jogador (NEX-10).
* O **Diagrama de Sequência (ARC-04)** para o fluxo de busca de player foi finalizado.
* Testes de Regra: A funcionalidade impede que um Moderador aplique um Banimento (regra de negócio).

**História NEX-02 (Gestão de Permissões):**
* A API permite que Administradores concedam/removam permissões para outros membros da Staff.
* A interface de gestão de Staff está implementada.

---

## 📊 Métricas Gerais de Qualidade (Aplicáveis a todos os Sprints)

| Categoria | Critério | Padrão |
| :--- | :--- | :--- |
| **Código** | Cobertura de Testes Unitários | > 80% (Para Classes Críticas) |
| **Segurança** | Criptografia de Senhas | Implementada (bcrypt) |
| **Processo** | Pull Request e Code Review | Abertura de PR e Aprovação obrigatória de 1 revisor |
| **Integração** | Teste E2E | Fluxo de login e busca de player testados após merge |
| **Documentação** | Atualização | Documentação da API (Swagger/OpenAPI) atualizada para novos endpoints |
| **Performance** | Tempo de Resposta API | < 300ms (Para consultas simples) |
