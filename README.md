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
