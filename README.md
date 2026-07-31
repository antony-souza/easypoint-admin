# EasyPoint Admin

Painel administrativo web do EasyPoint, responsável pelo gerenciamento centralizado dos estabelecimentos e das operações do sistema.

## Responsabilidade

O EasyPoint Admin é utilizado por administradores e gestores para controlar o sistema através de uma interface web.

É responsável por disponibilizar recursos para:

* Gerenciamento de produtos
* Gerenciamento de preços
* Controle de estoque
* Entradas e saídas de estoque
* Gerenciamento de lotes
* Consulta de vendas
* Relatórios
* Gerenciamento de lojas
* Gerenciamento de caixas
* Gerenciamento de usuários
* Permissões de acesso
* Configurações do sistema
* Acompanhamento da operação

## Comunicação

O painel não acessa diretamente o PostgreSQL.

Toda operação passa pela API:

```text
Administrador
      ↓
EasyPoint Admin
      ↓
HTTPS
      ↓
EasyPoint API
      ↓
PostgreSQL
```

Por exemplo, quando um administrador altera o preço de um produto:

```text
Admin
 ↓
API
 ↓
PostgreSQL
 ↓
Evento de sincronização
 ↓
PDV
 ↓
SQLite local
```

Dessa forma, o painel controla os dados centralizados enquanto a API é responsável por aplicar as regras de negócio e distribuir as alterações aos PDVs.

## Stack

* **React**
* **TypeScript**
* **TanStack Query**
* **TanStack Router**
* **REST API**
* **HTML / CSS**

## Princípio

> **O Admin gerencia a operação central do EasyPoint através da API, sem acessar diretamente os bancos dos PDVs.**
