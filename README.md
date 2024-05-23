# Projeto-E-Commerce

Objetivos: 
Cliente PJ e PF – Uma conta pode ser PJ ou PF, mas não pode ter as duas informações;
Pagamento – Pode ter cadastrado mais de uma forma de pagamento;
Entrega – Possui status e código de rastreio;
-------------------------------------------------------------------------------------

Cliente PJ e PF – Uma conta pode ser PJ ou PF, mas não pode ter as duas informações:

Contas é a tabela principal que armazena as informações comuns para todas as contas, incluindo um email único e um tipo que especifica se a conta é PJ ou PF.
PessoaFisica é a tabela que armazena informações específicas para contas de Pessoa Física (PF).
PessoaJuridica é a tabela que armazena informações específicas para contas de Pessoa Jurídica (PJ).
Regras Implementadas:
O campo Email na tabela Contas é único, garantindo que nenhum email seja duplicado entre PJ e PF.
O campo Tipo na tabela Contas tem uma restrição CHECK para garantir que só possa ter os valores 'PJ' ou 'PF'.
As tabelas PessoaFisica e PessoaJuridica usam ID_Conta como chave primária e chave estrangeira, garantindo que uma conta só possa ser associada a uma entrada em uma das tabelas específicas, mas não em ambas.

Pagamento – Pode ter cadastrado mais de uma forma de pagamento:

Pedidos é uma tabela que armazena informações sobre os pedidos feitos pelos clientes. Ela inclui um ID único para cada pedido, o ID do cliente que fez o pedido, a data do pedido e o status do pedido.
Pagamentos é uma tabela que armazena informações sobre os pagamentos associados a cada pedido. Ela inclui um ID único para cada pagamento, o ID do pedido ao qual o pagamento está associado, o método de pagamento, o montante do pagamento e campos adicionais específicos para cada método de pagamento (como número de cartão, agência, etc.).
Dessa forma, cada registro na tabela de pagamentos está vinculado a um pedido específico na tabela de pedidos.

Entrega – Possui status e código de rastreio:

Entregas é uma tabela que armazena informações sobre as entregas relacionadas aos pedidos. Ela inclui um ID único para cada entrega, o ID do pedido ao qual a entrega está associada, a data prevista para a entrega, o status da entrega e um código de rastreamento, se aplicável.
O campo ID_Pedido é uma chave estrangeira que referencia o ID do pedido na tabela Pedidos, estabelecendo assim uma relação entre as entregas e os pedidos.
Isso permite que cada entrega esteja associada a um pedido específico na tabela de pedidos.
