<h1>Análise de dados ulizando PostgreSQL</h1>

<h2><ol><li>Introdução</li></ol></h2>

<ul>
<li>O objetivo deste projeto é análisar uma base dados relacional de um e-commerce automotivo (Similar ao webmotors). A base utilizada nesse projeto é fictícia, utilizada apenas para fins de aprendizado.</li>

<li>Como já destacado no inicío desde documento, nesso projeto foi utilizado a linguagem SQL e o gerenciador de bando de dados PostgreSQL. A base de dados, está organizada conforme a imagem do diagrama abaixo, onde temos dois Schemas, sales e temp_tables,  o Schema sales é o principal.</li>


<img src="https://user-images.githubusercontent.com/73189777/173167367-02b1efda-0597-40e4-9826-b10f326859d2.png">

  <li>Aparti dessa análise iremos responder as seguintes perguntas:</li>
  
  
</ul>
<ol start = "1">
    <li>Quais estados que mais venderam no último mês ?</li>
    <li>Quais as 5 Marcas de carro mais vendidas no último mês ?</li>
    <li>Quias as 5 lojasque mais venderam carro no último mês ?</li>
    <li>Quantas vezes por dia da semana o site foi visitado no último mês ?</li>
  </ol>

<ul>
  <li>Este projeto foi criado, com intuito de colocar em pratica os conhecimentos básicos desenvolvidos no CURSO: SQL para Análise de dados, da Udemy.Uma plataforma EAD, que oferece cursos de diversas aréas. Neste curso, ao final de cada módulo foi proposto desafios onde os alunos aplicavam os conceitos apreendidos no modulo. No final do curso também foi proposto um desafio de criar querys para criação de dashboard dos principais indicadores de desempenho com os principais drives de vendas do mês. O curso oferece a "Solução" dos projetos guiados pelo instrutor do curso, como estou iniciando sentir a nessecidade em alguns momentos de recorrer a solução apresentada pelo instrutor.  </li>
</ul>
<h2> Respondedo as perguntas sobre o e-commerce automotivo</h2>

<h3>2.1. Quais estados que mais venderam no último mês ?</h3>

<p>Para responder essa pergunta foi nessecessario escrever uma query que filtrasse na tabela sales.funnel os datas de vendas, para chegar a ter a coluna STATE utilizei o LEFT JOIN passanto pela tabela CUSTOMERS e utilizando a chave estrangeira customer_i. Utilizei a função agregada COUNT para calcular o número de vendas, como eu quero saber o número de vendas do ultimo mês( que nesse caso é agosto)
Utilizei também a função WHERE, e BETEWEEN para filtrar a data entre os dias 2021-08-01 e 2021-08-31. A query também agrupa o resultado por pais e estado, ordenado pelo numero de vendas descrecente. Utilei também a função Limit para tarzer os 5 primeriros resultados.</p>

Query:

![image](https://user-images.githubusercontent.com/73189777/173209930-22da9d38-d699-4e93-8a21-02a906f8c090.png)

Retorno:

![image](https://user-images.githubusercontent.com/73189777/173210052-2351a20a-64ad-4ccb-b164-7110941ec842.png)


Dashboard:

![image](https://user-images.githubusercontent.com/73189777/173210045-3a239fd1-7ba4-4fa3-9c64-d2bd55fb246a.png)




Repositório criado com intuido de aprensentar conhecimentos basicos na linguagem SQL. 
