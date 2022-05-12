## Comandos CRUD SQL


## Resumo da sigla

- C -> CREAT (INSERT, inserir dados)
- R -> READ (SELECT, leitura de dados)
- U -> UPDATE (UPDATE, atualizar dados)
- D -> DELETE (DELETE, deletar dados)

## INSERT
INSERT INTO fabricante(nome) VALUES('Asus');
INSERT INTO fabricante(nome) VALUES('DELL');
INSERT INTO fabricante(nome) VALUES('Apple');
INSERT INTO fabricante(nome) VALUES('LG');

## INSERT com vários de uma só vez.

INSERT INTO fabricante(nome)
VALUES('Sansung'),('Microssoft'), ('Brastemp');

INSERT INTO fabricante(nome)
VALUES('Motorola'),('Mac'), ('HP');


### PRODUTOS
INSERT INTO produto(nome, preco, quantidade, descricao, fabricante_id)
VALUES('TV Led', 2000, 5, 'TV de última geração', 5 );

INSERT INTO produto(nome, preco, quantidade, descricao, fabricante_id)
VALUES('IPhone XYZ', 5500.79, 8, 'Smartphone caro para caramba',3);

INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id) VALUES


Exemplo do bloco de notas.
(
    'Geladeira',
    1500,
    10,
    'Refrigerador Frost-free com acesso à Internet das Coisas e bla bla bla',
    ? -- Brastemp
),
(
    'iPad Mini',
    5000,
    8,
    'Tablet Apple com tela retina display de 4k, memória interna de 64GB, acesso ao iCloud.',
    ? -- Apple
),
(
    'Xbox',
    2500,
    6,
    'Console de última geração com acesso aos melhores jogos e bla bla',
    ? -- Microsoft
),
(
    'Ultrabook',
    4500.68,
    12,
    'Equipamento com processador AMD Ryzen5, 12GB de RAM, placa de vídeo RTX',
    ? -- Asus
),
(
    'Headset',
    120,
    9,
    'Fone de ouvido USB com alta qualidade',
    ? -- Microsoft
),


Transferência dos dados do bloco de notas para o comando SQL.

INSERT INTO produto(nome, preco, quantidade, descricao, fabricante_id)
VALUES('Geladeira',1500,10,'Refrigerador Frost-free com acesso à Internet das Coisas e bla bla bla', 7),
      ('iPad Mini',5000,8,'Tablet Apple com tela retina display de 4k, memória interna de 64GB, acesso ao iCloud.',3),
      ('Xbox',2500,6,'Console de última geração com acesso aos melhores jogos e bla bla',6),
      ('Ultrabook',4500.68,12,'Equipamento com processador AMD Ryzen5, 12GB de RAM, placa de vídeo RTX',1),
      ('Headset',120,9,'Fone de ouvido USB com alta qualidade',6);

## SELECT - Consultas - buscar dados nas tabelas.

SELECT nome, preco FROM produto;
SELECT preco, nome FROM produto;

SELECT nome, preco FROM produto  WHERE preco < 3000;

SELECT nome, preco FROM produto  WHERE preco < 3000 AND preco > 2000;

SELECT nome, preco FROM produto  WHERE fabricante_id= 3 OR fabricante_id= 1;

<!-- SELECT nome, FROM fabricante  WHERE fabricante_id= 6 AND SELECT nome, FROM produto;  -->

SELECT nome, descricao FROM produto ORDER BY nome;
-- se NÃO COLOCAR NADA o padrão é a ordem CRESCENTE (PADRÃO)


SELECT nome, descricao FROM produto ORDER BY DESC;
-- DECRESCENTE

SELECT nome, descricao FROM produto
ORDER BY preco DESC; 
-- DECRESCENTE


SELECT nome, preco, quantidade, fabricante_id FROM produto; 

SELECT 
        produto.nome,
        fabricante.nome,
        produto.preco,
        produto.quantidade
FROM produto INNER JOIN fabricante
ON produto.fabricante_id = fabricante.id;


