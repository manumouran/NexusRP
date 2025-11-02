# Backlog do Produto - NexusRP (Gerenciamento Urbano)

Este documento centraliza todas as funcionalidades e tarefas planejadas para o projeto, priorizadas com base na necessidade da equipe de administração (*Staff*).

## Épica 1: Autenticação e Gestão de Acesso (Staff)

| ID | História de Usuário | Prioridade |
| :--- | :--- | :--- |
| NEX-01 | Como um **Membro da Staff**, eu quero fazer login com minhas credenciais exclusivas para acessar o painel administrativo. | **Alta** |
| NEX-02 | Como um **Administrador**, eu quero poder visualizar e gerenciar as permissões dos demais membros da Staff para garantir a segurança dos dados. | **Alta** |
| NEX-03 | Como um **Membro da Staff**, eu quero poder recuperar minha senha via e-mail ou sistema de segurança para garantir o acesso ininterrupto. | Média |

## Épica 2: Cadastro e Monitoramento de Cidadãos (Players)

| ID | História de Usuário | Prioridade |
| :--- | :--- | :--- |
| NEX-04 | Como um **Membro da Staff**, eu quero ter uma função de busca rápida por **Nome ou ID do jogador** para localizar prontamente qualquer cidadão. | **Alta** |
| NEX-05 | Como um **Membro da Staff**, eu quero poder visualizar um **prontuário completo** do cidadão (bens, status financeiro, tempo de jogo) em uma única tela. | **Alta** |
| NEX-06 | Como um **Membro da Staff**, eu quero poder **editar o status VIP, o dinheiro em conta ou o inventário** de um jogador para correções administrativas e compensações. | Média |
| NEX-07 | Como um **Membro da Staff**, eu quero ter acesso ao histórico completo de **logins e tempo jogado** do cidadão para monitorar a atividade. | Baixa |

## Épica 3: Gestão de Denúncias e Punições

| ID | História de Usuário | Prioridade |
| :--- | :--- | :--- |
| NEX-08 | Como um **Membro da Staff**, eu quero que **denúncias feitas via Discord** sejam automaticamente registradas no NexusRP, com dados do denunciante e denunciado. | **Alta** |
| NEX-09 | Como um **Membro da Staff**, eu quero ter um painel para **analisar denúncias abertas** e aplicar punições (ban/mute/jail) diretamente pelo sistema. | **Alta** |
| NEX-10 | Como um **Membro da Staff**, eu quero que todas as punições aplicadas fiquem registradas no **histórico disciplinar** do jogador para consultas futuras. | Média |
| NEX-11 | Como um **Jogador**, eu quero poder consultar meu histórico de punições no sistema para entender as decisões da Staff (visão limitada). | Baixa |

## Épica 4: Arquitetura e Modelagem Técnica 

| ID | Tarefa Técnica | Prioridade |
| :--- | :--- | :--- |
| ARC-01 | Definir o escopo do sistema através do **Diagrama de Casos de Uso** (Staff, Player, Sistema Discord). | **Alta** |
| ARC-02 | Detalhar o fluxo de **Registro de Denúncia** com o **Diagrama de Atividade**. | **Alta** |
| ARC-03 | Modelar a estrutura de dados e relacionamentos com o **Diagrama de Classe** (Player, Punição, Bens, Staff). | **Alta** |
| ARC-04 | Detalhar a interação entre objetos para a **Busca Rápida de Player** com o **Diagrama de Sequência**. | Média |
| ARC-05 | Modelar a arquitetura física (Servidor, Banco de Dados, Discord Bot) com o **Diagrama de Componentes** e **Implantação**. | Média |
| ARC-06 | Organizar as classes em grupos lógicos (Segurança, Cidadãos, Disciplinar) com o **Diagrama de Pacotes**. | Baixa |
