[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-blue.svg)](https://creativecommons.org/licenses/by/4.0/)

# Modelagem Preditiva da Produção de Arroz na América do Sul com Machine Learning

Este repositório contém os códigos, dados derivados e resultados utilizados no estudo:

> **GRION, R. F.; KOIFMAN, A. B.; MORAES, L. O.; FERREIRA, M. S. L.** *Modelagem preditiva da produção de arroz na América do Sul com Machine Learning.* 

---

## 🎯 Objetivo

Desenvolver modelos de aprendizado de máquina capazes de prever a **produção anual de arroz na América do Sul** (2004–2023), integrando variáveis agrícolas e climáticas para apoiar políticas públicas, planejamento sustentável e segurança alimentar.

O estudo compara os algoritmos **Regressão Linear**, **Support Vector Regression (SVR)** e **XGBoost Regressor**, com dados da **FAOSTAT** (produção) e **NASA POWER** (variáveis climáticas).


## Estrutura do Repositório

mlarrozprevisao/
├── [Tratados]Datasets_FAOSTAT_Rice_South_America/ # Dados tratados da FAOSTAT (América do Sul)
├── [Tratados]Datasets_FAOSTAT_Rice_Biggest_Producers/ # Dados tratados da FAOSTAT (maiores produtores mundiais)
├── Datasets_NASA_FAOSTAT/ # Dados climáticos integrados com FAOSTAT
├── Experimentos_Preliminares/ # Notebooks e testes iniciais
├── API_NASA_Power_South_America.ipynb # Extração de variáveis climáticas via API NASA POWER
├── Treinamento_Rice_South_America_2011_a_2020_3anos.ipynb # Treinamento dos modelos com dados agrícolas
├── Treinamento_Rice_NASA_Clima_South_America_2011_a_2020_3anos.ipynb # Treinamento com integração climática
├── LICENSE
├── README.md
├── requirements.txt

---

## 📘 Fontes de Dados

### 🟢 FAOSTAT – Food and Agriculture Organization (FAO)
- Dados de produção agrícola, área colhida e rendimento de arroz (Oryza sativa).  
- Acesso: [https://www.fao.org/faostat/en/](https://www.fao.org/faostat/en/)  
- Licença: [CC BY-NC-SA 3.0 IGO](https://creativecommons.org/licenses/by-nc-sa/3.0/igo/)

### 🔵 NASA POWER – Prediction of Worldwide Energy Resources
- Dados climáticos (precipitação e temperatura média anual).  
- Acesso: [https://power.larc.nasa.gov/](https://power.larc.nasa.gov/)  
- Licença: domínio público.

---

## ⚙️ Modelos e Metodologia

- **Modelos aplicados:**  
  - Linear Regression (LR)  
  - Support Vector Regression (SVR – RBF kernel)  
  - XGBoost Regressor (árvores de gradiente)

- **Etapas principais:**  
  1. Análise exploratória e limpeza dos dados  
  2. Integração FAOSTAT + NASA POWER  
  3. Treinamento com múltiplas janelas temporais (5, 10 e 15 anos)  
  4. Avaliação por MAPE e validação cruzada (k-fold)

- **Métrica principal:**  
  - MAPE (Mean Absolute Percentage Error)

- **Resultado principal:**  
  - O modelo **XGBoost** apresentou o melhor equilíbrio entre acurácia e estabilidade (MAPE médio ≈ 11%).

---

## 🧠 Requisitos e Execução

Os experimentos podem ser reproduzidos diretamente em ambiente **Jupyter Notebook**.

### 🔧 Dependências principais

- Python ≥ 3.10  
- Jupyter Notebook ou JupyterLab  
- Bibliotecas:
  - `pandas`
  - `numpy`
  - `xgboost`
  - `scikit-learn`
  - `matplotlib`
  - `requests` (para a API NASA POWER)

### ▶️ Execução

1. Clone ou baixe o repositório:
   ```bash
   git clone https://github.com/usuario/mlarrozprevisao.git
   cd mlarrozprevisao
   ```

2. Instale as dependências:

   ```bash
   pip install -r requirements.txt
