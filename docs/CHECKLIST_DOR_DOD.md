# Checklist de Definições (DoR & DoD)

Este documento estabelece os critérios de qualidade e os processos que governam o ciclo de vida de uma tarefa no projeto NexusRP.

---

## Definition of Ready (DoR)

Uma História de Usuário (ou Tarefa Técnica) deve atender a **todos os critérios** abaixo antes de ser movida para a coluna **"Em Andamento"** (Iniciada).

### Critérios Essenciais
* **História Clara:** A história de usuário está bem escrita, com um papel, objetivo e valor de negócio claros, baseados nas necessidades da Staff.
* **ID da Tarefa Criado:** A tarefa possui um identificador único no Backlog (ex: NEX-05 ou ARC-03).
* **Estimativa Realizada:** O esforço necessário para a tarefa foi discutido e estimado pela equipe (em horas ou *Story Points*).
* **Dependências Resolvidas:** Nenhuma dependência externa (API de terceiro, configuração de banco de dados, etc.) impede o início do trabalho.

### Critérios de Aceite
* **Requisitos Definidos:** Os requisitos funcionais para considerar a funcionalidade completa estão listados e são compreensíveis.
* **Interface (Se aplicável):** O esboço da tela ou do painel da Staff (se necessário) foi desenhado antes de iniciar o código.

---

## Definition of Done (DoD)

Uma funcionalidade deve atender a **todos os critérios** abaixo para ser considerada **"Concluída"** (Pronta para Homologação).

### Padrões de Código e Testes
* **Código Entregue:** O código foi comitado e enviado (`push`) para sua respectiva branch no repositório.
* **Testes Unitários:** As classes de lógica de negócio críticas (ex: **Serviço de Punição**, **Busca de Player**) possuem cobertura mínima de testes unitários em C#.
* **Configuração de Produção:** Todas as variáveis de ambiente e strings de conexão estão configuradas corretamente para a próxima fase de deploy.

### Padrões de Integração e Deploy
* **Integração Funcional:** Se for uma funcionalidade de integração (e.g., NEX-08), a comunicação com o **Discord API** foi verificada e está estável.
* **Pull Request Aberto:** Um Pull Request (PR) foi criado para mesclar a branch de trabalho.
* **Revisão de Código (Code Review):** Pelo menos um outro membro da equipe revisou e aprovou o PR.
* **Merge Realizado:** O Pull Request foi aprovado e o código foi integrado (`merged`) à branch `main` (branch principal).
