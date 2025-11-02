# Documentação - Sprint 2

**Período:** 17/09/2025 a 30/09/2025
**Meta da Sprint:** Implementar a busca rápida de jogadores e estabelecer a infraestrutura para o registro automático de denúncias via Discord.

---

## Histórias de Usuário e Tarefas Planejadas

| ID | Descrição da Tarefa | Status |
| :--- | :--- | :---: |
| **NEX-04** | Como Staff, eu quero uma barra de busca rápida de cidadão por Nome ou ID. | Concluída |
| **NEX-05** | Como Staff, eu quero ver um **Prontuário Completo** do cidadão (bens, finanças, histórico) ao pesquisar. | Concluída |
| **NEX-08** | Como Staff, eu quero que as denúncias abertas no Discord sejam **registradas automaticamente** no painel. | Concluída |
| **(ARC-02)** | Elaborar o Diagrama de Atividade para o fluxo de "Registro de Denúncia". | Concluída |

---

## Detalhamento das Histórias

### NEX-04: Busca Rápida de Cidadão
**Descrição:** Implementar uma API eficiente de busca que permita à Staff localizar qualquer jogador do servidor por diferentes critérios (ID, Nome Completo).

**Critérios de Aceitação:**
- Busca por ID deve ser exata e instantânea.
- Busca por Nome Completo deve suportar busca parcial (Ex: "João" encontra "João da Silva").
- O resultado da busca deve direcionar a Staff para o Prontuário (NEX-05).

### NEX-05: Prontuário Completo do Cidadão
**Descrição:** Desenvolver a interface (Frontend) e a API (Backend) para consolidar todas as informações do jogador em uma única tela.

**Critérios de Aceitação:**
- Exibição de dados financeiros (saldo bancário, dinheiro em mãos).
- Exibição de bens (veículos e propriedades) mapeados para o jogador.
- Exibição de estatísticas gerais (Tempo de Jogo Total, Último Login).
- Tela deve ser responsiva e carregar em menos de 1 segundo (performance).

### NEX-08: Integração Discord para Denúncias
**Descrição:** Configurar um serviço de *webhook* ou *bot* no ASP.NET Core que receba e processe dados de denúncias abertas no Discord, salvando-as no banco de dados.

**Critérios de Aceitação:**
- Serviço de escuta (`DiscordService.cs`) deve estar ativo.
- O registro no banco deve incluir: ID do denunciante, ID do denunciado, Provas (link ou anexo) e o texto da denúncia.
- Tratamento de falhas de conexão ou envio de dados inválidos.

---

## Resultado da Sprint

A meta da sprint foi totalmente atingida. O foco desta fase foi a **consolidação de dados** e a **comunicação externa**.

- **Integração:** A integração com o Discord foi um ponto de atenção e foi isolada em um serviço próprio (`Integrations/DiscordService.cs`), garantindo que a lógica de negócio principal ficasse limpa.
- **Desenvolvimento (Dados):** O Prontuário (NEX-05) exigiu a criação de *DTOs* e *ViewModels* complexos para exibir a vasta quantidade de dados de forma organizada na interface.

A base de dados agora suporta a recuperação de todas as informações críticas de um jogador.

**Destaques:**
- Prontuário do Cidadão centraliza todas as informações para a Staff.
- Integração de denúncias automatizada, reduzindo a carga de trabalho manual.
- Diagrama de Atividade (Registro de Denúncia) documenta o novo fluxo.

**Métricas:**
- 4 histórias de usuário completadas.
- 6 novos endpoints criados (Busca, Get Prontuário, Webhook Denúncia).
- Tempo médio de carregamento do Prontuário: 850ms.

---

## Retrospectiva

**O que funcionou bem:**
- A decisão de isolar a complexa lógica do Discord em um serviço dedicado facilitou a manutenção e testes.
- A comunicação entre Backend e Frontend sobre os formatos de dados do Prontuário foi eficiente.

**O que pode melhorar:**
- A criação da estrutura de DTOs para o Prontuário gerou alguma complexidade inicial; padronizar a nomenclatura pode ajudar.
- A cobertura de testes na camada de Integração precisa ser aumentada na próxima Sprint.

**Ações para próxima sprint:**
- Foco total nos testes unitários e de integração para a camada de `PunicaoService` (Sprint 3).
- Implementar o padrão *AutoMapper* (ou similar) para simplificar a conversão entre Model e DTO.
