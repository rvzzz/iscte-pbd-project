### Introdução e Contextualização

Este trabalho teve como objetivo a aplicação prática de técnicas de processamento de dados em larga escala utilizando a plataforma Apache Spark, com foco na linguagem Python (PySpark). O projeto seguiu uma abordagem modular com três notebooks distintos, abordando desde a ingestão e tratamento dos dados até a aplicação de algoritmos de análise não supervisionada.


### Dataset e Contexto de Negócio

O dataset utilizado foi o ["Big Sales"](https://www.kaggle.com/datasets/pigment/big-sales-data/data) do portal Kaggle. Nele foi escolhido o ficheiro “Liquor_Sales.csv”, com registos de vendas de bebidas alcoólicas no estado de Iowa, EUA (2012-2020), disponibilizado pelo Iowa Department of Revenue, Alcoholic Beverages Division. Este órgão regula a comercialização, fiscalização e distribuição de bebidas alcoólicas no estado.
O dataset possui 24 variáveis que abrangem informações sobre vendas (valores em dólares e volumes), características dos produtos (categorias e embalagens), informações geográficas (endereços, cidades, condados), dados temporais (datas das transações) e informações sobre fornecedores e lojas. Esta diversidade de variáveis permitiu uma análise abrangente do comportamento comercial no setor de bebidas alcoólicas.

### Objetivos do Projeto

O principal objetivo foi segmentar as vendas com base nas características dos produtos e volumes, identificando grupos com padrões comerciais semelhantes. Esta segmentação pode ser útil para apoiar decisões de marketing, gestão de stock e análise de mercado.

### Conclusão

Este projeto consolidou práticas de engenharia de dados e análise de dados em Big Data com Spark. Desde a ingestão, tratamento e análise exploratória até à modelação, o trabalho revelou-se um desafio realista e educativo. As técnicas aplicadas permitiram extrair informação de valor do dataset, identificar padrões e propor segmentações para decisões de negócio.
O uso do PySpark foi essencial para lidar com o volume de dados, e as visualizações trouxeram clareza à interpretação dos clusters. Apesar de limitações computacionais o projeto cumpriu os seus objetivos.



---




Durante o decorrer do projeto, deparámo-nos com uma limitação: ao partilharmos os notebooks entre os elementos do grupo, reparámos que os gráficos Plotly não eram renderizados a menos que o mesmos fossem executados. Isso constitui um problema uma vez que é esperado que os docentes não executem os notebooks para avaliar as análises realizadas.

Após algumas pesquisas online, apercebemo-nos que era um problema já identificado - os gráficos interativos que são gerados não são preservados automaticamente ao partilhar um notebook `.ipynb` entre diferentes computadores. Isto é, os gráficos deixam de aparecer a menos que o notebook seja reexecutado.

Para contornar esta limitação, foi adotada uma das soluções encontrada [neste fórum do StackOverflow](https://stackoverflow.com/questions/52771328/plotly-chart-not-showing-in-jupyter-notebook), onde os gráficos Plotly são exportados em formato HTML e armazenados na pasta `iframe_figures`. Posteriormente, são carregados dinamicamente no notebook, garantindo que as visualizações estejam sempre visíveis mesmo sem reexecutar o código.

Esta abordagem melhora significativamente a portabilidade e a usabilidade do projeto, especialmente em partilha colaborativa como foi o caso no projeto e também em contextos de avaliação, como virá a ser o caso.


Outro cuidado que tivemos, foi o de exportar os notebooks para o formato HTML, caso venha a ser mais cómodo de analisar o mesmo.


O projeto está organizado em pastas e notebooks que refletem cada etapa do pipeline de análise de dados.
Abaixo segue a descrição de cada componente:

	.
	├── 📓 Notebook 01 - Importação e Tratamento de Dados
	│   ├── 01 - Importação e Tratamento de Dados.ipynb         # Notebook principal da fase de ingestão e limpeza
	│   ├── 01 - Importação e Tratamento de Dados.html          # Versão HTML exportada do notebook
	│   ├── distinct_values_analysis/                           # Ficheiros CSV com valores únicos de cada coluna
	│   └── images/                                             # Imagens usadas para complementar comentários em markdown
	│
	├── 📓 Notebook 02 - Análises Exploratórias
	│   ├── 02 - Análises Exploratórias.ipynb                   # Notebook com estatísticas descritivas e visualizações
	│   ├── 02 - Análises Exploratórias.html                    # Versão HTML exportada do notebook
	│   └── iframe_figures/                                     # Gráficos interativos (Plotly) embutidos no notebook
	│
	├── 📓 Notebook 03 - Análise Não Supervisionada - Kmeans
	│   ├── 03 - Análise Não Supervisionada - Kmeans.ipynb      # Notebook com clustering, visualizações e interpretação
	│   ├── 03 - Análise Não Supervisionada - Kmeans.html       # Versão HTML exportada do notebook
	│   ├── iframe_figures/                                     # Gráficos interativos (Plotly) embutidos no notebook
	│   └── images/                                             # Imagens complementares à análise de clustering
	│
	└── 📊 ydata_profiling reports
	    ├── Liquor_Sales_Sample__ydata_profile_report.html      # Relatório de perfil da amostra tratada
	    └── Liquor_Sales__ydata_profile_report.html             # Relatório de perfil do dataset original
