# Happiness :grin:

## Table of contents

- [Introdução](#introdução)
- [Estrutura de pastas](#estrutura-de-pastas)
- [Requisitos](#requisitos)
- [Instruções](#instruções)

---
### Introdução

Este repositório foi criado com a intenção de armazenar o notebook contendo a análise da base de dados e as respostas aos questionamentos levantados, bem como os arquivos consumidos e gerados no processo.
Aqui você encontrará instruções sobre os requisitos necessários para replicar o ambiente de execução desta análise.

---

### Estrutura de pastas
Neste repositório você encontrará duas pastas:
- data
  - onde se encontram os arquivos com os datasets
- catboostinfo
  - onde se encontram os arquivos gerados automaticamente pelo catboost
<br>

Os arquivos gerados durante a análise serão salvos na raiz, sendo eles:
- case_bornlogic_gabriel_costa.ipynb:
  - o jupyter notebook
- case_bornlogic_gabriel_costa.html:  
  - um export do arquivo após a execução de todas as células, em formato 'html'
- datasets de tratamento parcial:
  - df_com_zonas.csv:
    - Dataset com os dados inputados e importação de zonas de outras fontes
  - df_preenchido_descarte.csv:
    - Dataset com os dados inputados e importação de zonas de outras fontes, após o descarte dos casos singulares
- Arquivos com datasets de preparação para aplicação dos modelos:
  - descarte_balanceado_catboost.csv:
    - Dataset com as classes balanceadas, do tratamento pré-aplicação do modelo catboost.
  - descarte_balanceado_catboost_sem_paises.csv:
    - Dataset com as classes balanceadas, do tratamento pré-aplicação do modelo catboost após remoção dos nomes dos países.
  - descarte_balanceado_rf.csv:
    - Dataset com as classes balanceadas, e com a aplicção de dummy encoding ao atributo "Country name". Dados de tratamento pré-aplicação do modelo Random Forest.
- Arquivos de comparação de resultados:
  - rf_resultados_tabela.csv:
    - Resultado da aplicação do Random Forest para estimar Regional indicator, após descarte de dados singulares balanceamento de classes (dataset balanceado + predições).
  - rf_comp_direta.csv:
    - Dataset com as colunas referentes a regiões, apenas, incluindo as previsões do Random Forest sobre Regional indicator, para comparação direta do resultados das previsões com dados esperados.
  - catboost_comp_direta.csv:
    - Dataset com as colunas referentes a regiões, apenas, incluindo as previsões do Catboost sobre Regional indicator, para comparação direta do resultados das previsões com dados esperados.
  - catboost_sem_paises_comp_direta.csv:
    - Dataset com as colunas referentes a regiões, apenas, incluindo as previsões do Catboost sobre Regional indicator quando aplicado sem o atributo Country name, para comparação direta do resultados das previsões com dados esperados.
  - comparcao_direta_ls_extra_trees.csv:
    - Comparação direta dos resultados da aplicação do modelo de regressão Extra Trees para deterimnação dos valores de Ladder Score.
  - comparcao_direta_ls_catboost.csv:
    - Comparação direta dos resultados da aplicação do modelo de regressão Catboost para deterimnação dos valores de Ladder Score.
- Arquivos de exportação de modelos:
  - rf0.joblib:
    - Random Forest para previsão de Regional indicator, com todos os atributos.
  - cb0.joblib:
    - Catboost para previsão de Regional indicator, com todos os atributos.
  - cb1_sem_paises.joblib:
    - Catboost para previsão de Regional indicator, sem Country name.
  - extra_trees_ladder_score.joblib:
    - Extra Trees para previsão de Ladder Score.
  - catboost_ladder_score.joblib:
    - Catboost para previsão de Ladder Score.
- Gráficos
  - indicadores_global_norm_faltantes.html:
    - Gráfico com dados faltantes, normalizados, mostrando a evolução dos atributos de todos os países pelos anos.
  - indicadores_global_norm_descarte.html:
    - Gráfico com dados descartados e sem dados faltantes, normalizados, mostrando a evolução dos atributosde todos os países pelos anos.
  - indicadores_br_raw_faltantes.html:
    - Gráfico com dados faltantes, sem normalização, mostrando a evolução dos atributos do Brasil pelos anos.
  - indicadores_br_raw_descarte.html:
    - Gráfico com dados descartados e sem dados faltantes, sem normalização, mostrando a evolução dos atributos do Brasil pelos anos.
- Perfil dos dados:
  -  profile_com_descartados.html:
    -  Arquivo do gerado pelo pandas-profiling contendo estatísticas sobre os atributos, bem como gráficos de interação e correlação entre atributos. Usado para facilitar o entendimento dos atributos.
- README.md
  - Este.

---
### Requisitos
- Python versão 3.7.9
- pandas versão 1.3.5
- pandas_profiling versão 3.1.0
- plotly versão 5.5.0
- imbalanced-learn versão 0.7.0
- scikit-learn versão 1.0.2
- catboost versão 1.0.6
---

### Instruções
O arquivo principal, com o código, as perguntas e as respostas, é o "case_bornlogic_gabriel_costa.ipynb". Através dele é possível reproduzir todos os passos que percorri até as conclusões.<br>
Porém, caso não seja interessante executar todo o código, o arquivo "case_bornlogic_gabriel_costa.html" contém uma impressão interativa do notebook com todas as células já executadas.



