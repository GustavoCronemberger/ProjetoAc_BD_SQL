# Modelo Conceitual

## Introdução
Realização do modelo conceitual para capturar os requisitos do sistema e representar a estrutura de dados de forma compreensível para todos os interessados no projeto.

### Entidades e Relacionamentos
Além do já mencionado sobre Entidades e Relacionamentos, especificamente nas entidades ALUGUEL e JOGOS foi decidido a não necessidade de haver uma chave estrangeira da entidade TEMPO_ALUGUEL e DISPONIBILIDADE, pois a relação entre elas é de um para um (1:1). Isso significa que cada registro na entidade ALUGUEL corresponde exatamente a um registro na entidade TEMPO_ALUGUEL e vice-versa, com o mesmo valor de chave primária. Essa abordagem foi escolhida para evitar redundância de dados e manter a integridade referencial.

Exemplo: Quando um novo aluguel de jogo é registrado, um novo registro é criado em ALUGUEL com um código de aluguel único, valor do aluguel, cliente e identificação do funcionário. Simultaneamente, um registro correspondente é criado em TEMPO_ALUGUEL com o mesmo código de aluguel, contendo as datas de início e devolução.

Essa estrutura também permite que o funcionário verifique se o cliente tem aluguéis atrasados antes de permitir novos aluguéis, com uma entidade limpa e de fácil entendimento, garantindo que a lógica de negócio seja respeitada.

### Cardinalidade
1) Funcionario e Cliente:

Funcionario cadastra Cliente;

Um funcionário pode cadastrar muitos clientes (0,n), mas cada cliente é cadastrado por um único funcionário (1,1).

2) Funcionario e Jogo:

Funcionario cadastra Jogos;

Um funcionário pode cadastrar muitos jogos (0,n), mas cada jogo é cadastrado por um único funcionário (1,1).

3) Funcionario e Aluguel

Funcionario registra Aluguel;

Um funcionário pode registrar muitos aluguéis (0,n), mas cada aluguel é registrado por um único funcionário (1,1).

4) Funcionario e Disponibilidade:

Funcionario verifica Disponibilidade;

Um funcionário pode verificar muitas disponibilidades (0,n), mas cada verificação de disponibilidade é feita por um único funcionário (1,1).

5) Cliente e Aluguel:

Cliente realiza Aluguel;

Um cliente pode realizar muitos aluguéis (1,n), mas cada aluguel é realizado por um único cliente (1,1).

6) Aluguel e Jogo:

Jogo é contido em Aluguel;

Um aluguel pode conter um ou mais jogos, mas cada jogo é contido a um único aluguel (1,1).

7) Aluguel e Tempo_Aluguel:

Aluguel tem um Tempo_Aluguel;

Cada aluguel tem um único registro de tempo de aluguel (1,1).

8) Jogo e Disponibilidade:

Jogo tem uma Disponibilidade;

Cada jogo tem uma única disponibilidade registrada (1,1).

9) Disponibilidade e Tempo_Aluguel:

Disponibilidade é referenciada por Tempo_Aluguel;

Status correspondente ao resultado da consulta.