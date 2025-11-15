# Projeto 2: Predição de Prêmios de Seguro Automotivo

Este projeto foca no pré-processamento, limpeza e análise exploratória de um conjunto de dados de seguro automotivo. O objetivo principal é preparar os dados (ETL) para etapas futuras de modelagem e predição de prêmios de seguro, garantindo a qualidade e a integridade dos dados através de um pipeline estruturado.

O pipeline de dados segue a **Arquitetura Medallion** (Bronze, Silver, Gold) para organizar o fluxo de processamento e refinar os dados em etapas.

* **Ações de Limpeza:**
    1.  **Padronização de Colunas:** Nomes de colunas convertidos para `lowercase` e remoção de caracteres especiais (ex: `insurance_premium_` ).
    2.  **Tratamento de Outliers:** Verificação (via IQR e Z-Score) que concluiu a **ausência** de outliers.
    3.  **Tratamento de Missing Values:** Verificação que concluiu a **ausência** de valores nulos.
    4.  **Tratamento de Categóricos:** Verificação que concluiu que o dataset **não possui** dados categóricos.
* **Resultado:** Os dados limpos e validados são salvos como uma tabela Delta (`workspace.silver.t_car_insurance_tr`).

## ⚙️ Pipeline de Processamento e Limpeza

O notebook segue um pipeline estruturado para transformar os dados da camada Bronze para a Silver:

1.  **Carregamento dos Dados:** Importação dos datasets de treino e teste da camada Bronze usando Pandas.
2.  **Padronização de Colunas:**
    * Aplicação de `lowercase` em todos os nomes de colunas.
    * Remoção de caracteres especiais e substituição de espaços por `_` (underline).
3.  **Tratamento de Outliers:**
    * Foi realizada uma análise detalhada usando **IQR (Intervalo Interquartil)** e **Z-Score**.
    * Funções de detecção foram criadas e validadas com dados "fabricados" para garantir seu funcionamento.
4.  **Tratamento de Valores Ausentes (Missing Values):**
    * Foi realizada uma verificação de valores nulos (`.isna().sum()`).
5.  **Tratamento de Dados Categóricos:**
    * Foi realizada uma análise dos tipos de dados (`.dtypes`).

---

## 📊 Análise Exploratória de Dados (EDA)

Após a limpeza, foi realizada uma análise exploratória (EDA) na camada Silver para extrair insights iniciais.

* **Visão Geral:** Utilização de `.info()`, `.shape()` e `.describe()` para entender a estrutura (10.000 linhas, 7 colunas) e as estatísticas descritivas dos dados.
* **Tipos de Dados:** Todas as colunas são numéricas, como `driver_age` (int64), `driver_experience` (int64) e `insurance_premium_` (float64).
* **Correlação:** Um gráfico de dispersão (scatterplot) revelou uma **relação linear clara** entre `driver_experience` (experiência do motorista) e `insurance_premium_` (valor do seguro).
* **Distribuição (Ex: `driver_age`):**
    * **Skewness (Assimetria):** Um valor próximo de `0` indicou uma distribuição **simétrica**.
    * **Kurtosis (Curtose):** Um valor próximo de `-1` indicou uma distribuição **platicúrtica** (pico achatado e caudas leves), o que reforça a ausência de outliers significativos.

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** `Python`
* **Plataforma:** `Databricks`
* **Bibliotecas Principais:**
    * `Pandas`: Para manipulação e análise dos DataFrames.
    * `PySpark`: Para criação de DataFrames Spark e salvamento em tabelas Delta.
    * `Scikit-learn (sklearn)`: Para normalização (`StandardScaler`) na análise de Z-Score.
    * `Seaborn` & `Matplotlib`: Para visualização de dados e EDA.
    * `NumPy`: Para cálculos numéricos e suporte às visualizações.
* **Arquitetura:** `Delta Lake (Arquitetura Medallion)`
