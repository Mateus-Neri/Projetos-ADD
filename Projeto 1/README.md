# Projeto: Análise da Base de Dados SUSEP (Auto)

Este projeto realiza análises exploratórias e consultas SQL sobre
diversas tabelas relacionadas a seguros automotivos provenientes da
SUSEP. O objetivo é identificar padrões, perfis de segurados e insights
estratégicos.

## 📌 Objetivos do Projeto

- Criar views temporárias a partir de arquivos CSV.
- Explorar variáveis como idade, prêmio (premio1), número de sinistros
  e ano do modelo.
- Correlacionar informações demográficas e regionais com indicadores
  estatísticos.
- Gerar insights relevantes para estratégias de seguros.

## 🛠 Tecnologias Utilizadas

- **PySpark**
- **SQL (Spark SQL)**
- **Databricks**

## 🔍 Insights Estratégicos

- **O mercado feminino é subexplorado**: apesar de mulheres
  representarem 58% das compras de veículos no Brasil, elas aparecem
  em menor proporção nos dados de segurados.
- **Regiões metropolitanas são mais sinistradas**, o que exige
  precificação diferenciada.
- **Veículos antigos podem indicar nichos específicos**, como
  colecionadores.
- **Perfis predominantes**: homens acima dos 36 anos representam a
  maior parte dos segurados.

## 📁 Arquivos Analisados

- `auto_cau.csv`
- `auto_cat.csv`
- `auto_cep.csv`
- `auto_cidade.csv`
- `auto_cob.csv`
- `auto_idade.csv`
- `auto_reg.csv`
- `auto_sexo.csv`
- `auto2_grupo.csv`
- `auto2_vei.csv`
- `PremReg.csv`
- `arq_casco_comp.csv`
- `arq_casco3_comp.csv`
- `arq_casco4_comp.csv`
- `SinReg.csv`

## ▶ Execução

O notebook foi desenvolvido em **Databricks**, utilizando células Python
e SQL intercaladas.

## 📄 Licença

Este projeto é apenas para fins acadêmicos/educacionais.
