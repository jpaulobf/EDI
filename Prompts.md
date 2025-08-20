# **Cenário:**





O objetivo deste sistema é proporcionar uma solução eficiente e intuitiva para o processo de vendas em nossa empresa, visando melhorar a experiência do cliente e otimizar a gestão de produtos e vendas.



Escopo

O sistema de PDV abrangerá as seguintes funcionalidades:



* Registro de Vendas
* Gestão de Produtos
* Gestão de Clientes
* Relatórios de Vendas
* Integração com o Sistema de Contabilidade





----- Usando a IA para construir a solução demandada ------





###### Prompt 1



Crie um modelo de dados para um sistema de comércio eletrônico com produtos, fornecedores, estoque, clientes (contemple endereços e telefones), pedidos e pagamentos.



Mostre primeiro em formato relacional (tabelas SQL com atributos e chaves primárias/estrangeiras). 



Mostre, em formato não-relacional (estrutura de documentos JSON para MongoDB).





###### Prompt 2



Explique as vantagens e desvantagens de armazenar dados de um e-commerce no Postgres (relacional) versus no MongoDB (não-relacional).



Considere aspectos de consistência, escalabilidade, velocidade de desenvolvimento e análise. 



Faça a comparação em uma tabela.





###### Prompt 3



Prepare um relatório, somente com as principais diferenças, e uma 2ª tabela com os pontos fortes e desvantagens do uso de cada modelo.



O cenário é de um sistema de comércio eletrônico com 100.000 a 1.000.000 de compras diárias. 



Qual seria sua recomendação?





###### Prompt 4



Suponha que tenhamos optado pelo cenário do Postgres. 

Utilizando o modelo de dados criado anteriormente, crie um script reprodutível (Python) que gere 1000 registros fictícios de pedidos de e-commerce em formato CSV, além disso, gere os dados das demais tabelas relacionadas.



Instruções:



a) Use a biblioteca Faker para gerar 'nomes dos clientes' e 'nome dos produtos' mais próximos dos reais.



b) Inclua "Fraldas" como um dos nomes dos produtos.



c) Inclua na sua amostra dados inconsistentes como:



\- CPFs Nulos

\- Idades negativas ou muito altas (mais de 100 anos)

\- Produtos sem preço

\- E-mails Nulos e/ou inválidos (sem a @ por exemplo)



###### 

###### Prompt 5



Crie um Script Python que leia os arquivos CSVs em memória e que realize a correção dos dados:



a) Preprocessamento



b) Limpeza



c) Normalização



d) Tornar os dados interoperáveis



e) Redução da Dimensionalidade



Depois exporte os arquivos com o prefixo bronze\_\[nome do arquivo].CSV (inclua uma coluna flag, em cada arquivo, contendo o campo "registro válido" (1/0)





###### Prompt 6



Crie um script Python para inserir dados dos CSVs bronze em um banco Postgres (usando psycopg2). 



Nossa database se chamará: comercio.

Host: localhost

Porta: 5432



Instruções:



a) Não inclua as colunas de validação dos dados, nem de normalização, nem de flags de dados inválidos.



b) Exclua todos os registros marcados como inválidos.



c) Respeite a integridade relacional (pode tentar inserir em um try/catch e se falhar gravar em uma tabela de inconsistências)





###### Prompt 7



Escreva 3 queries SQL para um banco Postgres de e-commerce:



a) Top 10 clientes por valor total de compras



b) Produtos mais vendidos



c) Média de idade dos clientes que compraram fraldas





###### Prompt 8



Gere um Notebook Jupyter, que use as bibliotecas Pandas, Numpy, Matplotlib, scikit-learn, psycopg2, que identifique, entre as compras realizadas, o padrão de compras (variáveis explicativas: sexo e idade) do produto Fralda.



Identifique potenciais outliers (pessoas muito novas \[10 anos ou menos] ou muito velhas \[60 anos ou mais] que tenham comprado fraldas).



Plote alguns gráficos de Distribuição por Idade e Sexo de Compradores de Fraldas, destacando os outliers.





