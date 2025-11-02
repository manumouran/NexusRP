# Manual de Usuário - Guia de Uso da Plataforma NexusRP

Este documento é um guia de referência para os membros da Equipe Administrativa (Staff) e para futuros desenvolvedores que precisam entender o uso e a execução da plataforma NexusRP.

## 1. Configuração do Ambiente de Desenvolvimento

Instruções detalhadas para a instalação de dependências e configuração do banco de dados (SQL Server) estão centralizadas em um documento específico.

* **Para Pré-requisitos e Setup:** Consulte o arquivo **[COMO_EXECUTAR.md](COMO_EXECUTAR.md)** para verificar a lista completa de tecnologias necessárias (.NET SDK, SQL Server, etc.).

## 2. Como Executar o Projeto

Instruções sobre como iniciar os servidores de Backend (ASP.NET Core API) e Frontend (Painel Web) para rodar a aplicação localmente.

* **Para Execução Local:** Consulte o arquivo **[COMO_EXECUTAR.md](COMO_EXECUTAR.md)**, Seções 2 e 3, para obter o passo a passo de inicialização via `dotnet run`.

## 3. Guia de Funcionalidades (Uso pela Staff)

Esta seção detalha o uso prático de cada módulo do NexusRP, alinhado com as histórias de usuário definidas no Backlog.

### 3.1. Autenticação e Acesso
* **Login:** Utilize suas credenciais exclusivas para acessar o painel, conforme a história **NEX-01**.
* **Recuperação de Senha:** O fluxo de recuperação está disponível para garantir o acesso ininterrupto (NEX-03).

### 3.2. Prontuário do Cidadão (Monitoramento)
* **Busca:** Utilize a barra de pesquisa para localizar o jogador por Nome ou ID (NEX-04).
* **Visualização Completa:** O painel exibe um prontuário unificado, mostrando bens, finanças e histórico de logins do player (NEX-05).

### 3.3. Controle Disciplinar
* **Registro Automático:** Denúncias feitas via Discord são integradas automaticamente (NEX-08) e aparecem no painel de moderação.
* **Aplicação de Punição:** O sistema permite analisar denúncias e aplicar punições (Ban, Mute, Jail) diretamente, registrando a ação no histórico do jogador (NEX-09, NEX-10).

---

## 4. Próximos Passos
Este guia será atualizado à medida que novas funcionalidades, como gestão de permissões avançadas (NEX-02) e relatórios financeiros, forem liberadas para a Staff.
