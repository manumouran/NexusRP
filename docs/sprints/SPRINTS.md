# Relatório de Sprint 3: Controle Disciplinar e Gestão de Acesso

| Período | 02/10/2025 a 16/10/2025 |
| :--- | :--- |
| **Meta da Sprint** | Finalizar o sistema de Controle Disciplinar, permitindo a aplicação de punições, e implementar a gestão de permissões para Administradores. |
| **Status Final** | Concluída com sucesso. Funcionalidades centrais de moderação (Punição e Histórico) estão prontas. |

---

## 1. Definições de Qualidade Aplicadas

### DoR (Definição de Pronto)
* **API Definida:** O endpoint de `POST /api/punicoes` foi definido e revisado para garantir a consistência dos dados.
* **Modelo Atualizado:** A entidade `Punicao` no `EF Core` foi finalizada para suportar campos como `staff_id`, `justificativa` e `duracao`.

### DoD (Definição de Concluído)
* **Regra de Negócio Implementada:** A regra de obrigatoriedade de **Justificativa** ao aplicar uma punição foi codificada na camada de *Service*.
* **Revisão de Código:** O código da Gestão de Permissões (NEX-02) foi revisado com foco em segurança (autorização baseada em *Roles*).
* **Documentação:** O manual de usuário foi atualizado com o passo a passo de como aplicar punições.

---

## 2. Histórico de Entregas

| ID | História de Usuário/Tarefa | Status | Comentários |
| :--- | :--- | :--- | :--- |
| **NEX-09** | Painel para análise e aplicação de punições (Banimento, Mute, Jail). | **Concluído** | Interface de aplicação de punição integrada à tela de prontuário. |
| **NEX-10** | Registro da punição no **Histórico Disciplinar** do jogador em tempo real. | **Concluído** | Punições aplicadas são salvas e exibidas no prontuário. |
| **NEX-02** | Gestão de permissões, permitindo que Administradores concedam/revoguem acessos de Staff. | **Concluído** | Implementação de níveis de acesso (Admin/Moderador). |
| **ARC-04** | Elaboração do Diagrama de Sequência para o fluxo de "Aplicação de Punição". | **Concluído** | Diagrama finalizado e anexado à pasta `diagrams/`. |

---
