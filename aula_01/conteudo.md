-> Aula expositiva sobre a ementa da disciplina

Ex de uso dos BD's:

Aplicações comerciais:
    -> Inserir
    -> Atualizar
    -> Excluir
    -> Consultar
    Aplicções essas que formam o CRUD

Para poder garantir a não redundância, se usa algum dado que é único, tal como CPF ou matrícula

⚠⚠ REDUNDANCIA CAUSA INCONSISTÊNCIA DE DADOS ❗❕❗❕❗❕❗❕

A não redundancia deve ser resolvida pelo desenvolvedor do banco de dados durante a fase de projeto do BD

Projeto de BD tem algumas fases:
    |-> Conceitual (Modelo/diagrama de entidade e relacionamento e modelo de classes UML representado pelo diagrama de classes)
        |-> Lógico (modelo relacional de dados)
            |-> Físico (SQL)

O que é um banco de dados?
    É uma coleção de dados relacionados logicamente. Representação de forma abstrata uma parte do mundo real (minimundo/universo). 

Para o que é projetado um BD?
    ele é usado para atender uma proposta específica para seu uso

Sistema gerenciador de banco de dados (SGBD): Coleção de programas que permitem a criação e gerência de bases de dados
Sistema de banco de dados: Banco de dados+ SGBD

Serviço de um SGBD
    |-> Redundância controlada de dados
    |-> Compartilhamento de dados multi-usuário
    |-> Concorrência para acessos simultâneos
    |-> Reconstrução de dadospós pane
    |-> Acesso controlado
    |-> Restrição de integridade
    |-> Distribuição para acessos remotos

Esquema da base de dados: descrição de uma base de dados (Resmido: estrutura lógica do BD)
Instância da base de dados: Dados da base de dados em um momento do tempo (Resumido: conteúdo real do BD)

