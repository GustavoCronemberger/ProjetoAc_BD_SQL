# Projeto Acadêmico de Banco de Dados SQL

## Introdução
Um cliente, dono de uma locadora de jogos de tabuleiro, quer um sistema para gerenciar o aluguel de jogos. Os processos incluem aluguel, cadastro de clientes e cadastro de jogos.

### Requisitos
Aluguel: Clientes alugam jogos por uma semana a R$10 por jogo. O atendente verifica se há empréstimos atrasados, registra o código do jogo, data do aluguel e número do cliente.

Cadastro de Jogos: O atendente informa código, nome, fabricante, número de jogadores, ano de publicação e número de cópias.

Cadastro de Clientes: O atendente registra CPF, nome completo, telefone, endereço e e-mail.

É essencial registrar qual atendente foi responsável por cada cadastro e aluguel, usando CPF e nome completo para controle.

## Solução
Com base nos requisitos apresentados, a organização ocorreu dispondo as seguintes entidades e respectivas funções:

### Entidades & Funções
1. Cliente
Atributos: CPF (chave primária), Nome completo, Telefone, Endereço, E-mail, Funcionário responsável (CPF do funcionário como chave estrangeira).

Função: Armazena informações pessoais e registra qual atendente foi responsável pelo cadastro do cliente.

2. Jogo
Atributos: Id do jogo (chave primária), Nome do jogo, Nome do fabricante, Número máximo de jogadores, Ano de lançamento, Número de cópias, Funcionário responsável (CPF do funcionário).

Função: Armazena informações sobre os jogos disponíveis para aluguel e registra qual funcionário cadastrou o jogo.

3. Aluguel
Atributos: Id do aluguel (chave primária), CPF do cliente (chave estrangeira), Id do jogo (chave estrangeira), Valor, Funcionário responsável (CPF do funcionário).

Função: Registra cada transação de aluguel e o funcionário responsável.

4. Tempo_Aluguel
Atributos: Id do aluguel (chave primária e estrangeira), Data de início, Data de devolução.

Função: Armazena as datas de início e devolução de cada aluguel.

5. Disponibilidade
Atributos: Id do jogo (chave primária e estrangeira), CPF do cliente (chave estrangeira), Data de devolução (referência ao atributo data_devolucao da entidade Tempo_Aluguel), Status de devolução (‘no prazo’/’atrasado’), CPF do funcionário (chave estrangeira).

Função: Verifica a disponibilidade dos jogos e a situação dos aluguéis.

6. Funcionário
Atributos: CPF (chave primária), Nome completo.

Função: Armazena informações sobre os funcionários e registra suas responsabilidades no cadastro de clientes, jogos e aluguéis.

### Relacionamentos
Funcionário cadastra Jogo

Funcionário cadastra Cliente

Funcionário registra Aluguel

Funcionário verifica Disponibilidade

Jogo tem uma Disponibilidade

Cliente realiza Aluguel

Aluguel contém Jogo

Aluguel tem um Tempo_Aluguel

Disponibilidade referencia Tempo_Aluguel

## Modelos de Banco de Dados
- Modelo Conceitual
- Modelo Lógico
- Modelo Físico