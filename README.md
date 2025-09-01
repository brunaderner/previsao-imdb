# Projeto IMDb – Analise do Sucessos do Cinema

Este projeto foi desenvolvido como parte de um desafio de ciência de dados. O objetivo foi compreender os fatores que influenciam o desempenho de um filme e construir um modelo capaz de prever a nota do IMDb a partir de diferentes variáveis disponíveis.

O trabalho foi dividido em três etapas principais: análise exploratória dos dados (EDA), respostas analíticas para perguntas-chave e modelagem preditiva.


### Descrição dos arquivos

- **README.md**: documento de apresentação do projeto, com objetivo, metodologia, resultados e instruções de uso.  
- **requirements.txt**: lista de bibliotecas necessárias para rodar o projeto de forma reprodutível.  
- **notebooks/LH_CD_BRUNADERNER.ipynb**: notebook principal, contendo a análise exploratória (EDA), a modelagem preditiva e as respostas às perguntas do desafio.  
- **reports/LH_CD_BRUNADERNER.pdf**: relatório em PDF exportado do notebook, consolidando as análises e resultados.  
- **models/model.pkl**: modelo final treinado (XGBoost Regressor), salvo em formato pickle para reutilização sem necessidade de re-treino.  
- **data/desafio_indicium_imdb.csv**: dataset original fornecido no desafio.  
- **data/complementares.csv**: informações complementares coletadas e integradas ao dataset principal.  
- **data/the_oscars_awards.csv**: dataset com dados sobre premiações no Oscar, usado para enriquecer a análise.  

## Análise Exploratória

A análise inicial permitiu identificar padrões relevantes nas variáveis. Entre os resultados, destacam-se:

- Filmes de aventura, ação e ficção científica mostraram maior associação com altos faturamentos.  
- Dramas e romances apresentaram relação negativa.  
- Filmes mais longos e lançados em anos recentes tiveram desempenho superior.  
- A coluna de descrições (Overview) revelou termos que se associam a maior apelo comercial, como referências a super-heróis e ao espaço.
- É importante se atentar à variável `Budget_USD`, que não está originalmente no dataset do desafio, mas pode ser obtida facilmente por buscas pontuais no Google ou, de forma mais estruturada, via API do TMDb.


## Modelagem

O problema foi tratado como regressão supervisionada, pois a variável alvo (IMDB_Rating) é contínua.

Foram testados diferentes modelos, como Regressão Linear Múltipla e Random Forest. O melhor desempenho foi obtido com o XGBoost Regressor, após ajustes de hiperparâmetros. Os resultados foram:

- R²: 52,7%  
- RMSE: 0,191  
- MAE: 0,154  

Esses números indicam que o modelo é capaz de explicar parte significativa da variação da nota, com bom equilíbrio entre precisão e generalização.

## Previsões em Prática

O modelo foi testado com o exemplo fornecido no desafio: The Shawshank Redemption. A previsão resultou em uma nota próxima de 8.8, valor bastante próximo da avaliação real. O modelo final foi salvo em arquivo `.pkl`, permitindo sua reutilização sem necessidade de re-treino.

## Entregáveis

O repositório contém:

- Notebook com a análise completa e a construção dos modelos.  
- Relatório em PDF exportado do notebook.  
- Arquivo `requirements.txt` com as bibliotecas utilizadas.  
- Modelo salvo em `.pkl`, pronto para ser carregado.  
- Este README com a descrição do projeto.

## Como usar

1. Crie um ambiente virtual.  
2. Instale as dependências com:  
   ```bash
   pip install -r requirements.txt
3. Abra o notebook em notebooks/ para explorar a análise.
4. Caso queira testar previsões, carregue o arquivo salvo em models/model.pkl e utilize a função de predição com as variáveis do filme desejado.
