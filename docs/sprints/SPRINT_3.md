# Documentação - Sprint 3

**Período:** 01/10/2025 a 14/10/2025
**Meta da Sprint:** Finalizar o sistema de Controle Disciplinar, permitindo a aplicação de punições (Ban/Mute/Jail), e implementar a gestão de permissões para Administradores.

---

## Histórias de Usuário e Tarefas Planejadas

| ID | Descrição da Tarefa | Status |
| :--- | :--- | :---: |
| **NEX-09** | Como Staff, eu quero um painel para analisar denúncias e **aplicar punições** (Ban/Mute/Jail) com justificativa obrigatória. | Concluída |
| **NEX-10** | Como Staff, eu quero que toda punição aplicada seja registrada no **Histórico Disciplinar** do jogador. | Concluída |
| **NEX-02** | Como Administrador, eu quero gerenciar os **níveis de permissão** da Staff (Admin/Moderador). | Concluída |
| **(ARC-04)** | Elaborar o Diagrama de Sequência para o fluxo de "Aplicação de Punição". | Concluída |

---

## Detalhamento das Histórias

### NEX-09: Aplicação de Punições
**Descrição:** Desenvolver o formulário de punição no Frontend e a API (`PunicaoController`) que processa a solicitação da Staff, validando os dados e registrando a ação.

**Critérios de Aceitação:**
- O formulário deve ter campos obrigatórios: Tipo de Punição, Duração e **Justificativa** (regra de negócio crítica).
- A API deve validar a permissão da Staff antes de processar a punição (NEX-02).
- Punições devem ser salvas com o ID do Staff que as aplicou.
- Mensagem de sucesso deve ser exibida após a aplicação.

### NEX-10: Histórico Disciplinar
**Descrição:** Integrar o registro de punição com o prontuário do jogador (NEX-05), garantindo que o histórico seja imutável e completo.

**Critérios de Aceitação:**
- A tela de Prontuário deve exibir uma seção dedicada ao Histórico Disciplinar.
- Cada item do histórico deve mostrar: Tipo de Punição, Data, Duração, Staff responsável e Justificativa.
- O histórico deve ser ordenado cronologicamente (mais recente primeiro).

### NEX-02: Gestão de Permissões
**Descrição:** Criar a funcionalidade administrativa que permite definir e alterar os níveis de acesso (Roles) de outros membros da Staff (Ex: Admin pode dar/tirar o cargo de Moderador).

**Critérios de Aceitação:**
- Apenas usuários com a Role "Admin" podem acessar a tela de gestão de Staff.
- Alteração de permissão deve ser persistida no banco de dados.
- O *token JWT* do usuário deve refletir sua nova permissão imediatamente ou após o próximo login.

---

## Resultado da Sprint

A meta foi atingida, entregando o **coração do sistema** de moderação. O foco foi garantir a **integridade dos dados** e a **segurança na ação**.

- **Desenvolvimento (Regra de Negócio):** O `PunicaoService.cs` foi criado com sucesso, implementando a regra de negócio central da Justificativa Obrigatória e o mapeamento de Model/DTOs.
- **Segurança (Autorização):** A autorização baseada em Roles foi aplicada no Backend, restringindo o acesso à gestão de Staff (NEX-02).

O sistema está agora totalmente funcional para o ciclo completo de Moderação: Denúncia -> Análise -> Punição.

**Destaques:**
- Sistema de Punição completo e validado com regras de negócio.
- O histórico disciplinar do jogador é rastreável e auditável.
- Diagrama de Sequência (ARC-04) documenta o fluxo da transação de punição.

**Métricas:**
- 4 histórias de usuário completadas.
- 3 novos endpoints críticos criados (`POST /api/punicoes`, `PUT /api/staff/permissions`).
- 95% de cobertura de testes unitários no `PunicaoService`.

---

## Retrospectiva

**O que funcionou bem:**
- O uso de *DTOs* e o padrão *AutoMapper* (iniciado na Sprint 2) simplificou o envio e recebimento de dados do formulário de punição.
- O trabalho em conjunto do Backend e Frontend para a validação da Justificativa foi eficiente.

**O que pode melhorar:**
- A lógica de *refresh* do token após a alteração de permissão (NEX-02) exigiu ajustes finos.
- O tempo dedicado ao Diagrama de Sequência foi maior que o previsto, mas garantiu a clareza do fluxo.

**Ações para próxima sprint:**
- Iniciar o mapeamento para as métricas da Sprint 4 (Relatórios) imediatamente.
- Foco em otimizar as consultas do SQL Server para os Relatórios, que serão mais pesadas.
