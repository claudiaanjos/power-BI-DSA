# Scripts SQL

# SELECIONE TUDO DA TABELA TB_DSA_CLIENTES;
SELECT * FROM TB_DSA_CLIENTES;


SELECT ID_Cliente,
       Nome_Cliente,
       Cidade,
       Estado,
       Pais,
       Regiao,
       Mercado,
       Segmento
FROM TB_DSA_CLIENTES;


SELECT ID_Cliente,
       Nome_Cliente,
       Cidade
FROM TB_DSA_CLIENTES;


SELECT *
FROM TB_DSA_CLIENTES
LIMIT 10;


SELECT DISTINCT segmento
FROM TB_DSA_CLIENTES;


SELECT *
FROM TB_DSA_PEDIDOS;


SELECT *
FROM TB_DSA_PEDIDOS
WHERE ano = 2014;


SELECT *
FROM TB_DSA_VENDAS;


SELECT *
FROM TB_DSA_VENDAS
WHERE Quantidade_Vendida = 5;


SELECT *
FROM TB_DSA_VENDAS
WHERE Quantidade_Vendida > 10;


SELECT *
FROM TB_DSA_VENDAS
WHERE Quantidade_Vendida <= 2;


SELECT *
FROM TB_DSA_VENDAS
WHERE Quantidade_Vendida <= 2 AND Valor_Venda > 900;


SELECT *
FROM TB_DSA_VENDAS
WHERE Quantidade_Vendida <= 2 OR Valor_Venda > 900;


SELECT *
FROM TB_DSA_VENDAS
WHERE Quantidade_Vendida <= 2  OR  Valor_Venda > 10000;


SELECT *
FROM TB_DSA_VENDAS
WHERE Valor_Venda BETWEEN 310 AND 320;


SELECT *
FROM TB_DSA_PRODUTOS;


SELECT *
FROM TB_DSA_PRODUTOS
WHERE Nome_Produto LIKE '%Clock%';


SELECT DISTINCT Categoria
FROM TB_DSA_PRODUTOS;


SELECT * 
FROM TB_DSA_PRODUTOS
WHERE Categoria IN ('Moveis', 'Tecnologia');


SELECT * 
FROM TB_DSA_PRODUTOS
WHERE Categoria NOT IN ('Moveis', 'Tecnologia');


SELECT * 
FROM TB_DSA_PRODUTOS
ORDER BY Nome_Produto;


SELECT *
FROM TB_DSA_VENDAS;


SELECT MIN(Valor_Venda), MAX(Valor_Venda), AVG(Valor_Venda), SUM(Valor_Venda), COUNT(Valor_Venda)
FROM TB_DSA_VENDAS;


SELECT Produto, MIN(Valor_Venda), MAX(Valor_Venda), AVG(Valor_Venda), SUM(Valor_Venda), COUNT(Valor_Venda)
FROM TB_DSA_VENDAS
GROUP BY Produto;


SELECT Produto, 
       MIN(Valor_Venda) AS Valor_Minimo, 
       MAX(Valor_Venda) AS Valor_Maximo, 
       AVG(Valor_Venda) AS Valor_Medio, 
       SUM(Valor_Venda) AS Valor_Total, 
       COUNT(Valor_Venda) AS Contagem
FROM TB_DSA_VENDAS
GROUP BY Produto;


SELECT Produto, 
       ROUND(MIN(Valor_Venda), 2) AS Valor_Minimo, 
       ROUND(MAX(Valor_Venda), 2) AS Valor_Maximo, 
       ROUND(AVG(Valor_Venda), 2) AS Valor_Medio, 
       ROUND(SUM(Valor_Venda), 2) AS Valor_Total, 
       COUNT(Valor_Venda) AS Contagem
FROM TB_DSA_VENDAS
GROUP BY Produto;


SELECT Produto, 
       ROUND(MIN(Valor_Venda), 2) AS Valor_Minimo, 
       ROUND(MAX(Valor_Venda), 2) AS Valor_Maximo, 
       ROUND(AVG(Valor_Venda), 2) AS Valor_Medio, 
       ROUND(SUM(Valor_Venda), 2) AS Valor_Total, 
       COUNT(Valor_Venda) AS Contagem
FROM TB_DSA_VENDAS
GROUP BY Produto
ORDER BY Contagem DESC;


SELECT Nome_Produto, 
       ROUND(MIN(Valor_Venda), 2) AS Valor_Minimo, 
       ROUND(MAX(Valor_Venda), 2) AS Valor_Maximo, 
       ROUND(AVG(Valor_Venda), 2) AS Valor_Medio, 
       ROUND(SUM(Valor_Venda), 2) AS Valor_Total, 
       COUNT(Valor_Venda) AS Contagem
FROM TB_DSA_VENDAS, TB_DSA_PRODUTOS
WHERE TB_DSA_VENDAS.Produto = TB_DSA_PRODUTOS.ID_Produto
GROUP BY Produto
ORDER BY Contagem DESC;


SELECT Nome_Produto, 
       ROUND(MIN(Valor_Venda), 2) AS Valor_Minimo, 
       ROUND(MAX(Valor_Venda), 2) AS Valor_Maximo, 
       ROUND(AVG(Valor_Venda), 2) AS Valor_Medio, 
       ROUND(SUM(Valor_Venda), 2) AS Valor_Total, 
       COUNT(Valor_Venda) AS Contagem,
       Ano
FROM TB_DSA_VENDAS, TB_DSA_PRODUTOS, TB_DSA_PEDIDOS
WHERE TB_DSA_VENDAS.Produto = TB_DSA_PRODUTOS.ID_Produto
AND TB_DSA_VENDAS.Pedido = TB_DSA_PEDIDOS.ID_Pedido
GROUP BY Produto, Ano
ORDER BY Contagem DESC;






























