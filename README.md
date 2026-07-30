# EasyPoint Admin

Painel administrativo web do **EasyPoint — Ponto Fácil**, destinado ao gerenciamento das operações e informações do estabelecimento.

## 🎯 Propósito

O `easypoint-admin` fornece uma interface web para administradores e gestores controlarem os dados e operações do EasyPoint.

## 📊 Principais responsabilidades

* Gerenciamento de produtos
* Alteração de preços
* Controle de estoque
* Consulta de vendas
* Visualização de relatórios
* Gerenciamento de caixas
* Gerenciamento de usuários
* Configuração do estabelecimento
* Visualização de informações operacionais

## 🏗️ Arquitetura

```text
             EasyPoint Admin
                    │
                    │ HTTP/HTTPS
                    ▼
              EasyPoint API
                    │
                    ▼
                PostgreSQL
```

O painel não acessa diretamente o banco de dados. Todas as operações são realizadas através da API do EasyPoint.

## 🛠️ Tecnologias

* React
* TypeScript
* Vite
* HTTP/REST API

## 📌 Responsabilidade

O painel administrativo é responsável pela **gestão e visualização das informações do sistema**.

Por exemplo, ao alterar o preço de um produto:

```text
Administrador
      ↓
EasyPoint Admin
      ↓
EasyPoint API
      ↓
Banco de dados
      ↓
Novo preço disponível
      ↓
EasyPoint PDV
```

Dessa forma, os caixas sempre consultam as informações centralizadas no backend.

## 🚧 Status

Em desenvolvimento.

## 🔗 Projetos relacionados

* `easypoint-api` — backend central da plataforma
* `easypoint-pdv` — aplicação desktop para operação do caixa
