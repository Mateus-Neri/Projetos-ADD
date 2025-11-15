# Projeto: Predição de Sinistros de Seguro Automotivo (Car Insurance Claim)

Este projeto detalha a construção de um pipeline completo de Machine Learning para prever a probabilidade de sinistro (`outcome`) em apólices de seguro automotivo. O processo abrange desde a limpeza de dados brutos (ETL), seguindo a arquitetura Medallion, até a seleção e avaliação de múltiplos modelos preditivos para identificar o de melhor performance.

---

### 📌 Objetivos do Projeto

* Aplicar um pipeline ETL (Extração, Transformação, Carga) seguindo a **Arquitetura Medallion** (Bronze, Silver, Gold).
* Realizar o tratamento de **outliers** (usando IQR) e a imputação de **valores ausentes** (usando a média).
* Codificar variáveis categóricas (ordinais e nominais) para preparar os dados para modelagem.
* Conduzir uma Análise Exploratória de Dados (EDA) para identificar padrões e perfis de risco.
* Utilizar técnicas de **Seleção de Features** (Chi2, ANOVA, XGBoost) para otimizar o modelo e remover ruídos.
* Treinar e comparar múltiplos algoritmos de classificação (DecisionTree, RandomForest, KNN, XGBoost) para selecionar o de melhor performance.

---

### 🛠 Tecnologias Utilizadas

* PySpark (para salvamento nas camadas Medallion)
* Pandas e NumPy
* Scikit-learn (para pré-processamento, métricas e modelagem)
* XGBoost
* Seaborn & Matplotlib
* Databricks

---

### 🔍 Insights Estratégicos (EDA)

A análise exploratória dos dados revelou padrões importantes sobre o risco de sinistro:

* **Idade e Experiência são Fatores Chave:** Motoristas mais velhos e com mais tempo de habilitação (`driving_experience`) apresentam uma correlação negativa clara com a ocorrência de sinistros.
* **Ter Filhos Não Aumenta o Risco:** Embora a quantidade de filhos aumente com a idade, os sinistros diminuem. Isso sugere que motoristas com filhos podem ser mais prudentes ao volante.
* **Infrações e Juventude:** O número de infrações por velocidade (`speeding_violations`) é notavelmente maior em faixas etárias mais jovens, que também concentram a maior proporção de sinistros.
* **Gênero não é Preditivo:** A distribuição de sinistros é quase idêntica entre homens e mulheres, não sendo um fator decisivo isoladamente.

---

### 📂 Arquivo Analisado

* `Car_Insurance_Claim.csv`

---

### 🤖 Seleção de Modelo

Quatro algoritmos de classificação foram treinados e avaliados. O **XGBoost Classifier** foi selecionado como o modelo final devido ao seu desempenho superior em todas as métricas principais.

| Modelo | Acurácia | F1-Score | Recall | MAE |
| :--- | :---: | :---: | :---: | :---: |
| Decision Tree | 0.757 | 0.622 | 0.634 | 0.243 |
| Random Forest | 0.830 | 0.720 | 0.690 | 0.170 |
| K-Neighbors (KNN) | 0.812 | 0.694 | 0.679 | 0.188 |
| **XGBoost** | **0.840** | **0.740** | **0.740** | **0.160** |

**Conclusão:** O XGBoost apresentou o melhor equilíbrio entre identificar corretamente os sinistros (Recall) e manter a precisão geral (Acurácia e F1-Score).

---

### ▶ Execução

* O notebook foi desenvolvido em ambiente **Databricks**, utilizando **Python** e suas principais bibliotecas de Data Science (Pandas, Sklearn, XGBoost).
* O **PySpark** foi utilizado para a persistência dos dados limpos (Silver) e prontos para modelagem (Gold) em Delta Tables.

---

### 📄 Licença

Este projeto destina-se a fins educacionais e de portfólio.
