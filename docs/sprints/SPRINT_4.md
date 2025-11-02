# Documentação - Sprint 4

**Período:** 15/10/2025 a 29/10/2025
**Meta da Sprint:** Implementar ferramentas avançadas de auditoria (Log de Ações) e o Dashboard de Relatórios de Desempenho da Staff para a liderança.

---

## Histórias de Usuário e Tarefas Planejadas

| ID | Descrição da Tarefa | Status |
| :--- | :--- | :---: |
| **NEX-11** | Como Liderança, eu quero um **Dashboard de Relatórios** para monitorar a produtividade e o desempenho da Staff. | Concluída |
| **NEX-12** | Como Administrador, eu quero um **Histórico de Auditoria** (Log de Ações) para rastrear alterações críticas no sistema. | Concluída |
| **NEX-13** | Como Staff, eu quero **Filtros Avançados** no Histórico Disciplinar para facilitar a pesquisa. | Concluída |
| **(DOC-04)** | Documentação de APIs (Swagger/OpenAPI) do módulo de Relatórios. | Concluída |

---

## Detalhamento das Histórias

### NEX-11: Dashboard de Relatórios de Desempenho
**Descrição:** Desenvolver endpoints otimizados para gerar métricas e gráficos no Frontend, exibindo a performance da Staff (Ex: Punições aplicadas, Denúncias fechadas).

**Critérios de Aceitação:**
- Exibição de gráficos de barra e pizza com dados dos últimos 30 dias.
- Filtro por data e por Staff específica.
- Acesso restrito apenas à Staff com permissão de "Liderança" ou "Admin".
- Tempo de carregamento dos relatórios não deve exceder 2 segundos.

### NEX-12: Histórico de Auditoria (Log de Ações)
**Descrição:** Implementar um mecanismo de *logging* no Backend que registre automaticamente ações críticas (Ex: Mudança de Permissão, Edição de Saldo de Jogador) antes que a alteração seja finalizada.

**Critérios de Aceitação:**
- Registro deve capturar: `Staff_ID`, `Ação`, `Timestamp` e `Detalhes da Mudança`.
- O log deve ser imutável (não pode ser alterado após o registro).
- A tela de auditoria deve permitir pesquisa por Staff e por data.

### NEX-13: Filtros Avançados
**Descrição:** Adicionar filtros na tela de Histórico Disciplinar do Prontuário para otimizar a pesquisa em grandes volumes de dados.

**Critérios de Aceitação:**
- Filtros disponíveis: Por **Tipo de Punição** (Ban, Mute, Jail), Por **Staff Aplicadora** e Por **Intervalo de Data**.
- A filtragem deve ser executada no Backend para eficiência.
- O Frontend deve ter um componente de filtro claro e intuitivo.

---

## Resultado da Sprint

A meta foi atingida, entregando as ferramentas de **transparência e gestão** para a liderança. O foco principal foi a **performance** das consultas de dados.

- **Desenvolvimento (Performance):** Foram aplicadas otimizações no Entity Framework Core para garantir que as consultas de Relatório (NEX-11) fossem executadas de forma eficiente, evitando problemas de desempenho.
- **Segurança (Auditoria):** O Log de Auditoria (NEX-12) garante a rastreabilidade de todas as ações sensíveis no sistema, um requisito de segurança essencial.

**Destaques:**
- Dashboard de Relatórios fornece *insights* valiosos para a gestão.
- Histórico de Auditoria rastreia ações críticas, aumentando a segurança.
- As APIs foram formalmente documentadas via Swagger/OpenAPI.

**Métricas:**
- 3 histórias de usuário completadas (e 1 tarefa de documentação).
- Tempo médio de resposta da API de Relatórios: 1.2 segundos.
- 100% dos endpoints de alteração crítica estão com o Log de Auditoria ativo.

---

## Retrospectiva

**O que funcionou bem:**
- A otimização proativa das consultas de banco de dados evitou gargalos de desempenho nos relatórios complexos.
- O uso de uma única tabela de Log de Auditoria simplificou a implementação.

**O que pode melhorar:**
- O design do Dashboard de Relatórios exigiu mais iterações do Frontend do que o previsto.
- A comunicação entre a Staff de Desenvolvimento e a Liderança para validar as métricas (KPIs) precisou ser mais detalhada.

**Ações para próxima sprint:**
- Foco total na **Otimização Final** e nos **Testes de Carga** (Sprint 5), garantindo que o sistema seja robusto antes da homologação.
- Revisão completa e final de toda a documentação (NEX-16).
