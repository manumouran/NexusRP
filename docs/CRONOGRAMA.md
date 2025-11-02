# Cronograma - Planejamento de Sprints NexusRP

Este documento detalha as metas e as principais entregas planejadas para cada Sprint do projeto, utilizando as tarefas definidas no Backlog do Produto.

## Sprint 1: Fundação e Autenticação

| Período | **02/09/2025 a 16/09/2025** |
| :--- | :--- |
| **Meta da Sprint** | Estabelecer a arquitetura do projeto (C# / SQL Server) e garantir o acesso seguro da Staff ao painel. |

| ID da Tarefa | Descrição da Entrega |
| :--- | :--- |
| NEX-01 | Implementar a funcionalidade de **login de membros da Staff** (incluindo segurança de credenciais). |
| ARC-03 | Modelagem do **Diagrama de Classe** (Player, Punição, Staff) para estruturação do banco de dados. |
| ARC-01 | Desenvolver o **Diagrama de Casos de Uso** para definir o escopo do sistema. |
| NEX-03 | Criar o fluxo de **recuperação de senha** para membros da Staff. |

## Sprint 2: Prontuário e Controle Disciplinar

| Período | **17/09/2025 a 01/10/2025** |
| :--- | :--- |
| **Meta da Sprint** | Implementar a busca rápida de jogadores e estabelecer a infraestrutura para o registro de denúncias via Discord. |

| ID da Tarefa | Descrição da Entrega |
| :--- | :--- |
| NEX-04 | Implementar a **busca rápida de cidadão** por Nome ou ID. |
| NEX-05 | Desenvolver a tela de **Prontuário Completo** (visualização de bens, finanças e tempo de jogo). |
| NEX-08 | Implementar a **integração com a Discord API** para registro automático de denúncias. |
| ARC-02 | Detalhar o fluxo de **Registro de Denúncia** com o **Diagrama de Atividade**. |

## Sprint 3: Gestão e Relatórios

| Período | **02/10/2025 a 16/10/2025** |
| :--- | :--- |
| **Meta da Sprint** | Finalizar o controle disciplinar (punições) e entregar o Dashboard administrativo com relatórios iniciais. |

| ID da Tarefa | Descrição da Entrega |
| :--- | :--- |
| NEX-09 | Desenvolver o painel da Staff para **análise e aplicação de punições** (Ban/Mute/Jail). |
| NEX-10 | Implementar o registro de todas as punições no **histórico disciplinar** do jogador. |
| NEX-02 | Implementar a **gestão de permissões** para Administradores. |
| ARC-04 | Detalhar a **Busca Rápida de Player** com o **Diagrama de Sequência**. |
