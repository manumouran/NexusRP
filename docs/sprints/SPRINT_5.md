# Documentação - Sprint 5

**Período:** 30/10/2025 a 02/11/2025
**Meta da Sprint:** Otimização de performance, implementação de alertas de comunicação e preparação final para o lançamento/homologação.

---

## Histórias de Usuário e Tarefas Planejadas

| ID | Descrição da Tarefa | Status |
| :--- | :--- | :---: |
| **NEX-14** | Como Staff, eu quero **alertas** sobre punições próximas do fim para evitar atrasos na liberação do jogador. | Concluída |
| **NEX-15** | Como Desenvolvedor, eu quero realizar **Testes de Carga** para garantir que a API suporte um alto volume de acessos. | Concluída |
| **NEX-16** | Como Desenvolvedor, eu quero realizar a **Revisão Final da Documentação** e fazer o commit final. | Concluída |
| **(ARC-05)** | Elaborar o Diagrama de Implantação (Deployment). | Concluída |

---

## Detalhamento das Histórias

### NEX-14: Alertas de Punição Expirando
**Descrição:** Desenvolver um sistema de notificação visual no painel para alertar a Staff quando uma punição (Ban ou Jail) estiver perto de expirar.

**Critérios de Aceitação:**
- Alerta deve aparecer na Dashboard com 24 horas de antecedência.
- O alerta deve ser limpo automaticamente após a punição expirar.
- A notificação deve incluir o ID do jogador e o tipo de punição.

### NEX-15: Testes de Carga (Stress Test)
**Descrição:** Realizar testes de desempenho nos endpoints mais críticos (Login, Busca, Relatórios) para identificar e otimizar gargalos.

**Critérios de Aceitação:**
- Endpoint de Login deve responder em menos de 300ms.
- Endpoint de Relatórios (o mais pesado) deve responder em menos de 1500ms sob 50 usuários simultâneos.
- Otimização de consultas lentas identificadas.

### NEX-16: Revisão Final da Documentação
**Descrição:** Realizar o processo de *checklist* final em toda a documentação (incluindo Sprints, DoR/DoD e Manuais) e fazer o commit final no repositório.

**Critérios de Aceitação:**
- Todos os documentos na pasta `docs/` devem estar atualizados.
- O `README.md` deve ter todos os links funcionando.
- Os diagramas devem estar na pasta correta (`diagrams/`).

---

## Resultado da Sprint

A meta foi atingida com sucesso, focando na **qualidade de entrega** e na **preparação para o lançamento**.

- **Performance:** Os testes de carga (NEX-15) garantiram que a API C#/ASP.NET Core está robusta e pronta para produção.
- **Documentação:** A Sprint encerra o ciclo formal do projeto, com todos os artefatos de engenharia entregues.

**Destaques:**
- Sistema de alertas funcional.
- Confirmação de performance e escalabilidade.
- Documentação completa e validada.

**Métricas:**
- 4 histórias de usuário completadas.
- 0 bugs críticos encontrados na homologação final.
- **Data de Entrega Final do Projeto: 02/11/2025.**

---
