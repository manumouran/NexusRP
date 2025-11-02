# Documentação - Sprint 1

**Período:** 02/09/2025 a 16/09/2025
**Meta da Sprint:** Estabelecer a arquitetura do projeto (C# / SQL Server) e garantir o acesso seguro da Staff ao painel.

---

## Histórias de Usuário e Tarefas Planejadas

| ID | Descrição da Tarefa | Status |
| :--- | :--- | :---: |
| **NEX-01** | Como Staff, eu quero fazer login com credenciais seguras para acessar o painel. | Concluída |
| **NEX-03** | Como Staff, eu quero ter um fluxo de recuperação de senha seguro. | Concluída |
| **(ARC-03)** | Criar a modelagem inicial de classes (Player, Staff, Punicao) no EF Core. | Concluída |
| **(ARC-01)** | Elaborar o Diagrama de Casos de Uso do sistema. | Concluída |

---

## Detalhamento das Histórias

### NEX-01: Login da Staff
**Descrição:** Implementar a API de autenticação no Backend (ASP.NET Core) e o formulário de login no Frontend para garantir acesso exclusivo e seguro à Staff.

**Critérios de Aceitação:**
- Autenticação com email/usuário e senha.
- Criptografia de senha forte (utilizando `Identity` ou `bcrypt`).
- Geração e retorno de token **JWT (JSON Web Token)** no sucesso do login.
- Implementação da camada de `Authorization` no Backend.
- Tratamento de erros de credenciais inválidas.

### NEX-03: Recuperação de Senha
**Descrição:** Criar o fluxo completo de recuperação de senha para evitar bloqueios de acesso da equipe.

**Critérios de Aceitação:**
- API para solicitação de redefinição de token por e-mail.
- Validação de tempo de expiração para o token de redefinição (máximo 1 hora).
- Atualização da senha na base de dados após confirmação.
- Notificação de segurança após a alteração da senha.

### ARC-03: Modelagem de Classes (EF Core)
**Descrição:** Estruturar as classes de entidade principais (`Player`, `Staff`, `Punicao`) e configurar o ORM (Entity Framework Core) para a base de dados SQL Server.

**Critérios de Aceitação:**
- Classes de entidade criadas na pasta `Models/`.
- `ApplicationDbContext` configurado na camada `Data/`.
- Primeira Migração do EF Core (`Add-Migration InitialCreate`) executada com sucesso.

---

## Resultado da Sprint

A meta da sprint foi atingida com sucesso. O trabalho foi focado na **fundação técnica** do projeto:

- **Desenvolvimento (Backend):** A API de autenticação foi implementada, utilizando o padrão de arquitetura de camadas (Controller -> Service -> Repository). Isso garante que o código de negócio (Services) seja isolado e testável.
- **Arquitetura:** A base do banco de dados foi criada via **EF Core**, e a Injeção de Dependência (`DI`) do ASP.NET Core foi configurada para todas as camadas do projeto.

A sprint estabeleceu uma base sólida em C#/ASP.NET Core, crucial para a performance e manutenção futuras.

**Destaques:**
- Sistema de autenticação **JWT** seguro implementado.
- Arquitetura de **Camadas (Clean/Hexagonal)** definida no Backend.
- Diagramas UML de Casos de Uso e Classe prontos e validados.
- 85% de cobertura de testes na camada de `AuthService`.

**Métricas:**
- 4 histórias de usuário completadas.
- 5 endpoints de API criados (Login, Refresh Token, Reset Password, etc.).
- 85% de cobertura de testes na camada de serviço de Autenticação.

---

## Retrospectiva

**O que funcionou bem:**
- Planejamento inicial bem estruturado e focado na arquitetura.
- Divisão clara de responsabilidades (Backend/Frontend) desde o início.
- O uso do `Identity` simplificou a implementação da criptografia de senha e segurança.

**O que pode melhorar:**
- A configuração inicial do **SQL Server e EF Core** consumiu mais tempo que o estimado.
- Estimativas de tempo para tarefas de *infraestrutura* precisam ser mais generosas.

**Ações para próxima sprint:**
- Dedicar uma *spike* (tempo de pesquisa) de 4 horas antes de iniciar tarefas de integração ou infraestrutura.
- Melhorar a comunicação entre Backend e Frontend para consumo de tokens.
- Manter o foco em **TDD (Test-Driven Development)** para todas as novas funcionalidades de serviço.
