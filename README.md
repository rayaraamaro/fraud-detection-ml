# Detecção de Fraudes com Machine Learning

Este projeto tem como objetivo analisar e comparar diferentes abordagens de Machine Learning aplicadas à detecção de fraudes em transações financeiras, utilizando técnicas supervisionadas e não supervisionadas.

---

## Sobre o Projeto

Este trabalho foi desenvolvido para a disciplina de Inteligência Artificial & Machine Learning, ministrada pelo professor Danilo Rodrigues de Assis Elias.

A proposta é colocar em prática os conceitos vistos em aula, explorando diferentes modelos de aprendizado de máquina para entender como eles se comportam em um problema real de detecção de fraudes.

---

## Objetivos

- Explorar e compreender o dataset de transações
- Lidar com o problema de classes desbalanceadas
- Treinar modelos de Regressão Logística
- Aplicar técnicas de detecção de anomalias (Isolation Forest)
- Avaliar o impacto da redução de dimensionalidade (PCA)
- Comparar modelos em diferentes cenários
- Desenvolver uma abordagem híbrida (extra)

---

## Dataset

O dataset contém transações financeiras anonimizadas, onde:

- As variáveis V1 a V28 são resultado de uma transformação por PCA
- A variável Amount representa o valor da transação
- A variável Class indica:
  - 0 → transação normal  
  - 1 → fraude  

O dataset utilizado neste projeto não está incluído no repositório devido ao seu tamanho.

Ele pode ser encontrado em:
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

Após o download, o arquivo `creditcard.csv` deve ser colocado na pasta:

data/

---

## Desafio do Problema

O dataset apresenta alto desbalanceamento, com poucas fraudes em relação às transações normais.

Isso torna o problema mais complexo, pois:
- A acurácia não é uma boa métrica
- O foco deve ser em falsos negativos (fraudes não detectadas)

---

## Modelos Utilizados

### Regressão Logística (Supervisionado)

- Regularizações testadas:
  - L1
  - L2
  - ElasticNet
- Ajuste do hiperparâmetro C
- Uso de class_weight='balanced'

---

### Isolation Forest (Não Supervisionado)

- Parâmetros testados:
  - n_estimators
  - contamination
- Conversão das predições para comparação com os rótulos reais

---

### PCA (Com e sem redução de dimensionalidade)

- Aplicação de PCA com redução de componentes
- Comparação do impacto nos modelos

---

### Modelo Híbrido (Extra)

- Combinação de:
  - Regressão Logística
  - Isolation Forest
- Estratégia:
  - Classificar como fraude apenas quando ambos concordam (AND)
- Ajuste do parâmetro contamination para melhorar a detecção

---

## Avaliação

Os modelos foram avaliados utilizando:

- Matriz de confusão
- Análise de:
  - Falsos positivos (FP)
  - Falsos negativos (FN)
- Trade-off entre precisão e recall

---

## Principais Resultados

- A Regressão Logística apresentou o melhor desempenho geral
- O Isolation Forest teve dificuldade em detectar fraudes sozinho
- O PCA não melhorou os resultados, pois o dataset já estava transformado
- O modelo híbrido mostrou-se uma alternativa interessante, reduzindo falsos negativos

---

## Aplicações no Mundo Real

Este problema se conecta com diversas áreas de detecção de anomalias, como:

- Segurança da informação
- Monitoramento de sistemas
- Detecção de falhas industriais
- Análise de comportamento de usuários

---

## Estrutura do Projeto

01_eda.ipynb  
02_logistic_regression.ipynb  
03_isolation_forest.ipynb  
04_model_comparison.ipynb  
05_pca_analysis.ipynb  
06_final_analysis.ipynb  

---

## Integrantes

ERICK MOLINA - RM 553852  
FELIPE CASTRO SALAZAR - RM 553464  
MARCELO VIEIRA DE MELO - RM 552953  
RAYARA AMARO FIGUEIREDO - RM 552635  
VICTOR RODRIGUES - RM 554158  

---

## Conclusão

O projeto demonstrou que modelos supervisionados tendem a apresentar melhor desempenho quando há dados rotulados disponíveis. No entanto, abordagens não supervisionadas e híbridas podem complementar a análise, especialmente na detecção de padrões desconhecidos.
