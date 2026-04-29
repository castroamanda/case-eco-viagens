# case-eco-viagens

* Resumo
Este estudo detalha o desenvolvimento de uma solução de inteligência de dados para a EcoViagens, operadora brasileira especializada em ecoturismo. O trabalho abrangeu desde a estruturação do banco de dados até a definição de indicadores estratégicos (KPIs), culminando na criação de dashboards dinâmicos voltados para a otimização da gestão de reservas, clientes e iniciativas sustentáveis.

1. Modelagem de Dados

<img width="1334" height="1049" alt="Diagrama" src="https://github.com/user-attachments/assets/15f94555-076a-469a-91fa-3da631add8c2" />

Descrição das entidades:

|  |
| --- |
| Atributo | Tipo | Descrição |
| id_cliente | INTERGER (PK) | Identificador do cliente |
| nome_completo | VARCHAR | Nome do cliente |
| genero | VARCHAR | Gênero do cliente |
| data_nascimento | DATE | Data de nascimento do cliente |
| e-mail | VARCHAR | E-mail do cliente |
| localidade | VARCHAR | Cidade e estado de residência do cliente |
| data_cadastro | DATE | Data em que o cliente foi cadastrado |
| operador |
| Atributo | Tipo | Descrição |
| id_operador | INTERGER (PK) | Identificador da empresa |
| nome_operador | VARCHAR | Nome da empresa |
| cnpj | VARCHAR | Cadastro da empresa |
| email | VARCHAR | E-mail da empresa |
| localidade | VARCHAR | Cidade e estado de atuação da empresa |
| data_cadastro | DATE | Data em que a empresa foi cadastrada |
| oferta |
| Atributo | Tipo | Descrição |
| id_oferta | INTERGER (PK) | Identificador da oferta |
| tipo_oferta | VARCHAR | Atividade ou hospedagem |
| nome_oferta | VARCHAR | Nome da oferta |
| descricao | TEXT | Descrição do serviço |
| preco | DECIMAL | Valor por pessoa |
| id_operador | INTERGER (FK) | Identificador da empresa |
| atividade (subtipo de oferta) |
| Atributo | Tipo | Descrição |
| id_oferta | INT (PK, FK) | Identificador da oferta (chave estrangeira) |
| nivel | VARCHAR | Fácil, médio, difícil, etc |
| nome_oferta | VARCHAR | Nome da oferta |
| duracao | INTERVAL | Duração da atividade |
| grupo_maximo | INT | Capacidade máxima |
| preco | DECIMAL | Valor por pessoa |
| hospedagem (subtipo de oferta) |
| Atributo | Tipo | Descrição |
| id_oferta | INT (PK, FK) | Identificador da oferta (chave estrangeira) |
| tipo_acomodacao | VARCHAR | Chalé, quarto compartilhado, etc |
| capacidade | INT | Número de pessoas |
| possui_breakfast | BOOLEAN | Sim;Não |
| preco | DECIMAL | Valor por pessoa |
| reserva |
| Atributo | Tipo | Descrição |
| id_reserva | INTERGER (PK) | Identificador da reserva |
| data_reserva | DATE | Data em que a reserva foi realizada |
| id_cliente | INTERGER (FK) | Identificador do cliente (chave estrangeira) |
| id_oferta | INTERGER (FK) | Identificador do serviço (chave estrangeira) |
| data_in | DATE | Primeiro dia da utilização do serviço |
| data_out | DATE | Último dia da utilização do serviço |
| qtde_pessoas | INTERGER | Quantidade de pessoas na reserva |
| status | VARCHAR | Confirmada, cancelada, concluída, etc |
| avaliacao |
| Atributo | Tipo | Descrição |
| id_avaliacao | INTERGER (PK) | Identificador da avaliação |
| id_cliente | INTERGER (FK) | Identificador do cliente (chave estrangeira) |
| Id_oferta | INTERGER (FK) | Identificador da oferta (chave estrangeira) |
| data_avaliacao | DATE | Data em que a avaliação foi feita |
| nota | INTERGER | Nota da avaliação |
| comentarios | TEXT | Comentários da avaliação |
| pratica_sustentavel |
| Atributo | Tipo | Descrição |
| id_pratica | INTERGER (PK) | Identificador da prática |
| descricao | VARCHAR | Nome ou descrição da prática |
| oferta_pratica |
| Atributo | Tipo | Descrição |
| id_oferta | INTERGER (FK) | Identificador da oferta (chave estrangeira) |
| id_pratica | INTERGER (FK) | Identificador da prática (chave estrangeira) |
