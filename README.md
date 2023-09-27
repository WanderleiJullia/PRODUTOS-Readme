# Banco de Dados - PRODUTOS
 # O exercicio abaixo tem o objetivo de estar demonstrando como foi a realizado a criação de de uma tabela de produtos, utilizando as seguintes informações; id_produtos, nome, preço, estoque, perecivel, não perecivel, marca e nacionalidade. Atribuindo cada campo seu respectivo tipo, segue abaixo os códigos que foram utilizados e esclarecendo o que está sendo feito no bloco de códigos. 
 
# Contrução da Tabela. 
    create table Produtos(
    id_produto int primary key,
    nome varchar(255) not null, 
    preco decimal(11,2) not null, 
    estoque int not null,
    perecivel varchar(80) not null, 
    marca varchar(255),
    nacionalidade varchar(255)
    );
    
    insert into Produtos (id_produto, nome, preco, estoque, perecivel, marca, nacionalidade) values (1,'Macarrão', 8.99, 87, 'não-pereciveis', 'Adria', 'Italiano');
    insert into Produtos (id_produto, nome, preco, estoque, perecivel, marca, nacionalidade) values (2,'Feijão', 10.99, 60, 'não-pereciveis', 'Santo dia ', 'Brasileiro');
    insert into Produtos (id_produto, nome, preco, estoque, perecivel, marca, nacionalidade) values (3, 'Atum', 2.30, 40, 'perecivel', 'Gomes da costa', 'Brasileiro');
    insert into Produtos (id_produto, nome, preco, estoque, perecivel, marca, nacionalidade) values (4,'Milho enlatado', 5.30, 25, 'perecivel', 'Quero', 'Brasileiro');
    insert into Produtos (id_produto, nome, preco, estoque, perecivel, marca, nacionalidade) values (5,'Achocolatado', 10.00, 108, 'não-pereciveis', 'Nescau', 'Brasileiro');

  ºA principio foi realizado a criação da tabela de produtos, utilizando as informações que se encontra na descrição do exercicio. 
 
# Gere um relatório informando quantos produtos estão cadastrados;
    select * from Produtos; 
    
  ![image](https://github.com/WanderleiJullia/PRODUTOS-Readme/assets/144744092/606fbfc7-684f-4c1c-95f4-93c87b195eaf)

º No código e Imagem, está demonstrando todos os itens que foram cadastrados na tabela principal. 

# Gere um relatório informando o preço médio dos produtos;
    select avg(preco)as preco_medio from Produtos; 
    
   ![image](https://github.com/WanderleiJullia/PRODUTOS-Readme/assets/144744092/d2399d6d-6bcb-4314-bfe7-993c1a95fa18)

º Selecionando a junção de todos os preços e demostrando qual é a media de preço de todos os itens da tabela. 

º Foi utilizado a função AVG que usamos para retornar uma média aritmérica de um conjunto numérico.


# Selecione a média dos preços dos produtos em 2 grupos: perecíveis e não perecíveis;
    select preco 
    from Produtos
    where perecivel in ('não-perecivel', 'perecivel'); 

  ![image](https://github.com/WanderleiJullia/PRODUTOS-Readme/assets/144744092/aa33a966-3bbd-417c-af9e-4bfd314fe6ec)

 º Nesse código foi utilizdo para procurar a média de dois tipos de produtos que possuimos na nossa tabela, perecivel e não-perecivel. 

# Selecione a média dos preços dos produtos agrupados pelo nome do produto;
    select nome, avg(preco) as media_preco
    from Produtos 
    group by nome; 
  
 ![image](https://github.com/WanderleiJullia/PRODUTOS-Readme/assets/144744092/4b675c20-26d8-4fa7-b175-551d3a151790)


º Nesse código utilizamos a clásula 'GROUP BY' , juntando com a função de 'AVG'.

º'GROUP BY' - Tem a função de agrupar os resultados pelo "nome", obtendo a média de preço para cada produto. 

 
# Selecione a média dos preços e total em estoque dos produtos;
    select avg(preco) as media_preco, sum(estoque) as total_estoque
    from Produtos; 
![image](https://github.com/WanderleiJullia/PRODUTOS-Readme/assets/144744092/1a3e1c1a-41aa-4eea-9ffc-13394ce1cc86)

º 'AVG' - Para calcular a média de preços.

º 'SUM' - Total de estoque, utilizamos essa função, pois , somamos a quantidade e a média de todos os itens do estoque para ser feita a junção, sem agrupalos individualmente.  
    

# Selecione o nome, marca e quantidade em estoque do produto mais caro;
    select nome, marca, estoque
    from Produtos
    order by preco desc
    limit 1;
   ![image](https://github.com/WanderleiJullia/PRODUTOS-Readme/assets/144744092/2492d986-dabc-4dbf-bc6b-16f15135aad3)

º 'ORDER BY' - Foi utilizado para classificar os produtos em ordem decrescentes.

º 'LIMIT 1' - Para obter apenas o primeiro resultado, que será o produto mais caro.


# Selecione os produtos com preço acima da média;
    select nome, preco 
    from Produtos
    where preco > (select avg(preco) from Produtos);
   ![image](https://github.com/WanderleiJullia/PRODUTOS-Readme/assets/144744092/8e4f1a78-8e37-4ab2-9146-a36a182581af)

º WHERE preco > (SELECT AVG(preco) FROM produtos) para filtrar os produtos com preço superior à média de preços. A subconsulta (SELECT AVG(preco) FROM produtos) calcula a média dos preços na tabela "produtos" e, em seguida, o preço de cada produto com essa média. 


# Selecione a quantidade de produtos de cada nacionalidade;
    select nacionalidade, count(*) as quantidades 
    from Produtos
    group by nacionalidade; 
![image](https://github.com/WanderleiJullia/PRODUTOS-Readme/assets/144744092/1a7da0d8-4416-48f6-9359-c9b5a478d980)

º 'GROUP BY'- Obtendo a nacionalidade de cada produto;

º 'COUNT'- Para contar o número de produtos para cada nacionalidade. 


# Autor

Jullia Santos Wanderlei 

Bancos de Dados.
