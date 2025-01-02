# Tabela Restaurante

┌──────────────────┐     ┌───────────────────┐
|     clientes     |     |       mesas       |
|------------------|     |-------------------|
| id_cliente (PK)  |     | id_mesa (PK)      |
| nome             |     | capacidade        |
| telefone         |     | disponibilidade   |
| email            |     └───────────────────┘
└──────────────────┘
          |
          | 1
          |       *       ┌──────────────────┐
          ├──────────────►|      pedidos     |
          |               |------------------|
          |               | id_pedido (PK)   |
          |               | id_cliente (FK)  |
          |               | id_mesa (FK)     |
          |               | data_pedido      |
          |               | status_pedido    |
          |               └──────────────────┘
          |                         |
          |                         |
          |                         | 1
          |                         |       *      ┌──────────────────────┐
          |                         └─────────────►|   pedidos_itens_menu |
          |                                        |----------------------|
          |                                        | id_pedido (FK)       |
          |                                        | id_item (FK)         |
          |                                        | quantidade           |
          |                                        | preco_unitario       |
          |                                        └──────────────────────┘
          |
          |                                        ┌──────────────────┐
          |                                        |    itens_menu    |
          └────────────────────────────────────────|------------------|
                                                   | id_item (PK)     |
                                                   | nome             |
                                                   | descricao        |
                                                   | preco            |
                                                   └──────────────────┘
