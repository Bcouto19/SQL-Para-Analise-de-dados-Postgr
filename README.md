<h1>Análise de dados utilizando PostgreSQL</h1>

<h2><ol><li>Introdução</li></ol></h2>

<ul>
<li>O objetivo deste projeto é análisar uma base dados relacional de um e-commerce automotivo (Similar ao webmotors). A base utilizada nesse projeto é fictícia, utilizada apenas para fins de aprendizado.</li>

<li>Como já destacado no inicío desde documento, nesso projeto foi utilizado a linguagem SQL e o gerenciador de bando de dados PostgreSQL. A base de dados, está organizada conforme a imagem do diagrama abaixo, onde temos dois Schemas, sales e temp_tables,  o Schema sales é o principal.</li>


<img src="https://user-images.githubusercontent.com/73189777/173167367-02b1efda-0597-40e4-9826-b10f326859d2.png">

  <li>Aparti dessa análise iremos responder as seguintes perguntas:</li>
  
  
</ul>
<ol start = "1">
    <li>Quais estados que mais venderam no último mês ?</li>
    <li>Quais as 5 marcas de carros mais vendidas no último mês ?</li>
    <li>Quais as 5 lojas que mais venderam carro no último mês ?</li>
    <li>Quantas vezes por dia da semana o site foi visitado no último mês ?</li>
  </ol>

<ul>
  <li>Este projeto foi criado, com intuito de colocar em pratica os conhecimentos básicos desenvolvidos no CURSO: SQL para Análise de dados, da Udemy.Uma plataforma EAD, que oferece cursos de diversas aréas. Neste curso, ao final de cada módulo foi proposto desafios onde os alunos aplicavam os conceitos apreendidos no modulo. No final do curso também foi proposto um desafio de criar querys para criação de dashboard dos principais indicadores de desempenho com os principais drives de vendas do mês. O curso oferece a "Solução" dos projetos guiados pelo instrutor do curso, como estou iniciando sentir a nessecidade em alguns momentos de recorrer a solução apresentada pelo instrutor.  </li>
</ul>
<h2>2. Respondedo as perguntas sobre o e-commerce automotivo</h2>

<h3>2.1. Quais estados que mais venderam no último mês ?</h3>

<p>Para responder essa pergunta foi nessecessario escrever uma query que filtrasse na tabela sales.funnel as datas de vendas, para chegar a ter a coluna STATE utilizei o LEFT JOIN passanto pela tabela CUSTOMERS e utilizando a chave estrangeira customer_id. Utilizei a função agregada COUNT para calcular o número de vendas, como eu quero saber o número de vendas do último mês( que nesse caso é agosto)
Utilizei também a função WHERE, e BETEWEEN para filtrar a data entre os dias 2021-08-01 e 2021-08-31. A query também agrupa o resultado por país e estado, ordenado pelo número de vendas em ordem decrescente. Utilei também a função  LIMIT para trAzer os 5 primeriros resultados.</p>

Query:

![image](https://user-images.githubusercontent.com/73189777/173209930-22da9d38-d699-4e93-8a21-02a906f8c090.png)

Retorno:

![image](https://user-images.githubusercontent.com/73189777/173210052-2351a20a-64ad-4ccb-b164-7110941ec842.png)


Dashboard:

![image](https://user-images.githubusercontent.com/73189777/173210045-3a239fd1-7ba4-4fa3-9c64-d2bd55fb246a.png)


<h3>2.2. Quais as 5 marcas de carro mais vendidas no ultimo mês ?</h3>


<p>Essa query é bem parecida com a query do questionamento acima. Aqui foi necessario filtrar as datas de vendas na tabela sales.funnel, relacionando com as marcas dos carros, onde utilizei o LEFT JOIN passando pela tabela PRODUCTS e chegando na coluna BRAND, para isso utilizei a chave estrangeira product_id. Utilizei a função agregada COUNT para calcular o número de vendas. Utilizei também a função WHERE, e BETEWEEN para filtrar a data entre os dias 2021-08-01 e 2021-08-31. A query retorna os 5 primeiro resultado, agrupado pela marca.</p>


Query:

![image](https://user-images.githubusercontent.com/73189777/173210191-eaf0205b-faf4-40d5-8054-3ba1835f31f6.png)

Retorno:

![image](https://user-images.githubusercontent.com/73189777/173210204-082610b7-1d91-4e5d-9e17-411c95649548.png)


Dashboard:

![image](https://user-images.githubusercontent.com/73189777/173210221-81e913db-ee00-4a43-a280-b1737b18b760.png)

<h3> 2.3. Quais as 5 lojas que mais venderam carro no último mês ?</h3>

<p> Aqui foi feita uma query, similar as anteriores, selcionando na tabela sales.funnel o número de vendas, e utilizando a função agregada COUNT para fazer o calculo. Para chegar a coluna store_name foi utilizado o LEFT JOIN passanto pela tabela sales.store, utilizando a chave estrangeira store_id. O filtro de data doi feito pelas funções WHERE e BETWEEN, o resultado retorno as informações agrupadas por loja, e os 5 primeiros resultado.</p>

Query:

![image](https://user-images.githubusercontent.com/73189777/173210321-71e31c8d-c8f1-40e2-96fc-e0f888f76879.png)



Retorno:

![image](https://user-images.githubusercontent.com/73189777/173210331-98a8edf0-c3d1-4811-a6a9-b1e64a81503a.png)

 
Dashboard:

![image](https://user-images.githubusercontent.com/73189777/173210340-4970a402-70bc-43ae-9435-7674285e2363.png)


<h3>2.4. Quantas vezes por dia da semana o site foi visitado no último mês ?</h3>

<p>Nessa query, Precisei selecionar e extrair o dia da semana, para isso eu utilizei a função extract e utulizei a expressão DOW que me retorna um valor de 0 a 6 que representa um dia da semana, onde o valor inicial que é  0 = Domigo. Precisei também cria uma nova coluna "dia da semana" que me retorna um valor string, nesse caso utilizei o case when. O resultado está agrupado e ordenado pelo dia da semana.</p>

Query:

![image](https://user-images.githubusercontent.com/73189777/173210578-5c7d5b82-f63a-4c77-969d-f767bc1e8653.png)


Retorno:

![image](https://user-images.githubusercontent.com/73189777/173210605-f8c8cfaa-7578-42cf-b069-1756a431f0fa.png)


Dashboard:

![image](https://user-images.githubusercontent.com/73189777/173210623-a1fc3207-39fe-4882-b178-f1f040c14eac.png)



<h3>3 Considerações Finais</h3>

<p>Após  feita a análise para responder as perguntas propostas, podemos concluir que a marca Fiat é a campeã de vendas de carros, a loja que mais vendeu carros dentro do e-commerce automotivo no último mês(Agosto) foi a loja: "KIYOKO CILEIDI JERY LTDA, o estado de São Paulo é o estado que mais se destacou no mês de agosto em relação ao número de vendas. Descobrimos também que as Segundas-Feiras do mês de agosto foi o dia da semana que mais recebeu visitas no e-commerce.</p>


Repositório criado com intuido de aprensentar conhecimentos basicos na linguagem SQL. 
