1. Conexão e Criação do Banco de Dados
O script começa importando a biblioteca sqlite3, usada para se comunicar com o SQLite, e a biblioteca os, que permite manipular arquivos do sistema.

O banco de dados será salvo no arquivo chamado loja.db.

Se o arquivo loja.db já existir, ele é removido para garantir que um novo banco seja criado a cada execução.

Uma conexão com o banco de dados é então estabelecida. Caso o arquivo ainda não exista, o SQLite cria um novo automaticamente.

2. Criação das Tabelas
O código define três tabelas principais:

Clientes: Guarda o ID, nome e e-mail de cada cliente. O campo id é a chave primária.

Produtos: Armazena o ID, nome do produto e preço. O campo id também é a chave primária.

Vendas: Registra as vendas realizadas, com os campos id_venda, id_cliente, id_produto, quantidade e data. Essa tabela possui duas chaves estrangeiras: uma que liga ao cliente e outra ao produto correspondente.

Após a definição das tabelas, o comando commit() é usado para salvar as alterações no banco.

3. Inserção de Dados
O script insere exemplos de dados nas tabelas:

Três clientes são cadastrados na tabela Clientes.

Quatro produtos diferentes são adicionados na tabela Produtos.

Quatro vendas são registradas na tabela Vendas, utilizando os IDs dos clientes e produtos. A data da venda é preenchida automaticamente com a data e hora atuais.

4. Consultas (SELECT)
Várias consultas SQL são realizadas para demonstrar como os dados podem ser acessados:

Consulta Simples: Exibe todos os registros da tabela Clientes.

Consulta com Condição: Mostra apenas os produtos com preço acima de R$ 200,00.

Consulta com JOIN: Junta as tabelas Vendas, Clientes e Produtos para exibir detalhes completos de cada venda — incluindo o nome do cliente, o produto e o valor total da compra.

Consulta com JOIN e Filtro (WHERE): Mostra quais produtos foram comprados pela cliente "Ana Silva".

Consulta com Função de Agregação: Usa SUM e GROUP BY para calcular quanto cada cliente gastou no total, listando os resultados em ordem decrescente.

5. Exibição dos Resultados
Os dados retornados pelas consultas são exibidos diretamente no notebook do Colab. Para isso, os resultados são percorridos com um laço for e impressos na tela.

6. Encerramento da Conexão
Por fim, o banco de dados é desconectado com o comando conn.close(). Essa etapa é importante para liberar recursos e garantir que todas as alterações feitas sejam salvas corretamente.
