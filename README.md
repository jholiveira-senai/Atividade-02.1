# Atividade-02.1
Modelagem e Implementação de Banco de Dados para um Sistema de E-commerce

- A atividade se constituiu na modelagem, relacionamentos e comandos estabelecidos dentro do Banco de Dados, neste sistema foi inserido tabelas com seus respectivos dados. Segue abaixo o código do Banco de Dados:



   create database ecommerce_db2;
use ecommerce_db2;


create table clientes(
id int auto_increment primary key,
nome varchar(100) not null,
email varchar(100) unique not null,
telefone varchar(20),
data_cadastro date not null
);


create table pedidos(
id int auto_increment primary key,
valor decimal(10,2) not null,
data_desc date not null,
cliente_id int,
foreign key (cliente_id) references clientes(id)
);


create table itens_pedidos(
id int auto_increment primary key,
produtos varchar(300) not null,
categorias varchar(300) not null,
pedido_id int,
foreign key (pedido_id) references pedidos(id)
);


insert into clientes(nome, email, telefone, data_cadastro) values
('Jhenyfer Oliveira', 'jhenyfer@gmail.com', '71999999999', '2008-09-06'),
('Lucas Nogueira', 'lucas@gmail.com', '71988888888', '2008-07-15'),
('Murilo Costa', 'murilo@gmail.com', '71977777777', '2008-07-16'),
('Geovana Santana', 'geovana@gmail.com', '71966666666', '2008-07-16'),
('Benjamim Souza', 'benjamim@gmail.com', '71955555555', '2009-08-19'),
('Ana Victoria Capistrano', 'anavictoria@gmail.com', '71944444444', '2008-06-23'),
('Trícia Britto', 'tricia@gmail.com', '71933333333', '2008-02-13'),
('Isabella Almeida', 'isabella@gmail.com', '71922222222', '2008-09-27'),
('Valdevino Oliveira', 'valdevino@gmail.com', '71911111111', '1978-08-05'),
('Janicleia Oliveira', 'janicleia@gmail.com', '71900000000', '1976-10-28');


insert into pedidos(valor, data_desc, cliente_id) values
(4999.00, '2026-08-08', 1),
(200.00, '2026-07-10', 2),
(6700.00, '2026-10-28', 3),
(1400.00, '2026-02-03', 4),
(80.00, '2026-09-11', 5),
(970.00, '2026-09-14', 6),
(2300.00, '2026-12-07', 7),
(876.00, '2026-03-05', 8),
(10.00, '2026-05-06', 9),
(100.00, '2026-05-13', 10);


insert into itens_pedidos(produtos, categorias, pedido_id) values
('iPhone 16 Pro', 'Tecnologia', 1),
('Fones de Ouvido Bluetooth', 'Tecnologia', 2),
('Notebook', 'Tecnologia', 3),
('Placa de Vídeo', 'Tecnologia', 4),
('Livro', 'Ficção', 5),
('Aparelho de Jantar', 'Cerâmica', 6),
('Geladeira', 'Eletrodomésticos', 7),
('Air Fryer', 'Eletrodomésticos', 8),
('Película', 'Tecnologia', 9),
('Gift Card', 'Jogos', 10);


select*from clientes;

select*from clientes
limit 5;


select*from itens_pedidos;

update clientes
set email = 'jhenyferoliveira@gmail.com'
where id = 1;

delete from pedidos
where id = 3;

select produtos, categorias
from itens_pedido
order by nome asc;

-- ASC Crescente
-- DESC Descrecente
