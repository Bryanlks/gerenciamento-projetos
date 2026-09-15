# gerenciamento-projetos

# Gerenciamento de Projetos - Banco de Dados Relacional

Repositório desenvolvido como parte da atividade prática de banco de dados utilizando o SGBD PostgreSQL. O projeto simula o ciclo de vida completo do desenvolvimento de um banco de dados relacional para controle de projetos, equipes e tarefas.

---

## 1. Apresentação do Projeto

* **Tema:** Gerenciamento de Projetos
* **Objetivo Geral:** Centralizar o controle de projetos, atribuição de tarefas e acompanhamento de prazos, permitindo que equipes gerenciem suas atividades diárias e o progresso de entregas de forma eficiente.
* **Público-alvo:** Gerentes de projetos, líderes técnicos e membros de equipes de desenvolvimento.

---

## 2. Modelo de Dados Relacional

Abaixo está o diagrama entidade-relacionamento que representa a estrutura lógica do banco de dados:

```mermaid
erDiagram
    usuario {
        int id PK
        string nome
        string email
    }
    projeto {
        int id PK
        string titulo
        date data_inicio
        date data_termino
    }
    tarefa {
        int id PK
        int projeto_id FK
        int responsavel_id FK
        string descricao
        string status
    }
    usuario ||--o{ tarefa : executa
    projeto ||--|{ tarefa : possui

## 3. Estruturação do Repositório

Os scripts de criação, manipulação e manutenção do banco de dados estão organizados na pasta scripts/:

scripts/01__create_table_usuario.sql - Criação da tabela de usuários.

scripts/02__create_table_projeto.sql - Criação da tabela de projetos.

scripts/03__create_table_tarefa.sql - Criação da tabela de tarefas (com chaves estrangeiras).

scripts/04__insert_dados_iniciais.sql - Inserção de dados de exemplo (DML).

scripts/05__update_status_tarefa.sql - Atualização de status de registros (DML).

scripts/06__delete_tarefa_obsoleta.sql - Remoção de registros de teste (DML).
