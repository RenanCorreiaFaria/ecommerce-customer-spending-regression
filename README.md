# Gasto do Cliente em E-commerce — Regressão Linear (Diagnóstico e Predição)

**[Português](#português) · [English](#english)**

---

## Português

Estudo de caso desenvolvido no **MBA em Analytics e Inteligência Artificial da FIA**, com foco
em regressão linear aplicada à previsão e ao diagnóstico do gasto anual de clientes de e-commerce.

### 🎯 Objetivo

Entender **o que faz um cliente gastar mais ou menos ao longo do ano** e **prever** o gasto
anual de um novo cliente a partir do seu perfil. O trabalho compara, de propósito, dois
caminhos para o mesmo problema — um voltado à interpretação, outro à predição.

### 📊 Base utilizada

Dados consolidados na visão cliente referentes aos últimos 12 meses, com métricas de
comportamento de compra (frequência, ticket médio, recência), canal, engajamento e dados
demográficos. A variável resposta é o `valor_total_gasto` (gasto anual em R$), modelada em
escala log para corrigir a assimetria à direita.

### ❓ Missão da análise

- **Diagnóstico:** quais características mais influenciam o gasto anual e quanto cada uma pesa.
- **Predição:** quanto um novo cliente tende a gastar no ano, dado o seu perfil.

### 🔀 Os dois caminhos

- **Caminho A — Estatística clássica.** Regressão linear (OLS) com seleção manual de variáveis
  via stepwise backward, guiada por p-valores, intervalos de confiança (95%) e controle de
  multicolinearidade (VIF). Foco em interpretar.
- **Caminho B — Machine Learning.** Todas as variáveis entram no modelo e a regularização
  (Ridge/LASSO/ElasticNet via SGDRegressor) decide o peso de cada uma, com busca de
  hiperparâmetros e validação cruzada de 5 folds. Foco em prever.

### 💡 Principais insights

- **Frequência de compra** e **ticket médio histórico** são os maiores direcionadores do gasto
  (correlação de Pearson de 0,626 e 0,580 com a resposta).
- No **teste externo**, os dois caminhos praticamente empatam: R² de 0,864 (Caminho A) contra
  0,853 (Caminho B), ambos sem sobreajuste.
- Numa base de poucas variáveis e sem colinearidade relevante, a **curadoria manual iguala a
  seleção automática** e ainda entrega interpretabilidade — por isso o Caminho A foi adotado
  como modelo final, com o Caminho B documentado como a escolha certa para bases maiores e com
  muitas variáveis correlacionadas.
- Para quem atua em CRM e lifecycle, os direcionadores se traduzem em alavancas acionáveis:
  recorrência (frequência) e valor do pedido (ticket médio).

### 🛠️ Ferramentas utilizadas

- Python
- pandas e numpy — manipulação e análise de dados
- matplotlib e seaborn — visualização
- scikit-learn — validação cruzada, regularização e pré-processamento
- statsmodels — regressão OLS e inferência

### 📁 Estrutura do repositório

```
.
├── 01_caminho_A_estatistica_classica.ipynb   # regressão OLS + seleção manual (diagnóstico)
├── 02_caminho_B_machine_learning.ipynb       # regularização + validação cruzada (predição)
├── Gasto_eCommerce_Dados-1.txt               # base de dados
├── apresentacao_estudo_de_caso.pdf           # apresentação do trabalho
└── README.md
```

### ▶️ Como executar

1. Clone o repositório ou baixe os arquivos.
2. Abra os notebooks no Google Colab ou Jupyter Notebook.
3. Garanta que o arquivo `Gasto_eCommerce_Dados-1.txt` esteja na mesma pasta dos notebooks.
4. Execute as células na ordem.

---

*Case desenvolvido em grupo: Renan Correia (líder), Bruno Higuti, Michelle Tanaka,
Victor Aquino e Hygor Vaz. Agradecimentos ao time e à orientação do MBA em Analytics e IA da FIA.*

---

## English

Case study developed for the **MBA in Analytics and Artificial Intelligence at FIA**, focused
on linear regression applied to predicting and explaining the annual spending of e-commerce
customers.

### 🎯 Objective

Understand **what drives a customer to spend more or less over the year** and **predict** a new
customer's annual spending from their profile. The project deliberately compares two paths to
the same problem — one aimed at interpretation, the other at prediction.

### 📊 Data

Customer-level data consolidated over the last 12 months, with purchase-behavior metrics
(frequency, average ticket, recency), acquisition channel, engagement and demographics. The
target variable is `valor_total_gasto` (annual spending in BRL), modeled on a log scale to
correct its right skew.

### ❓ Mission

- **Diagnosis:** which features most influence annual spending, and how much each one weighs.
- **Prediction:** how much a new customer is likely to spend in the year, given their profile.

### 🔀 The two paths

- **Path A — Classical statistics.** Linear regression (OLS) with manual feature selection via
  backward stepwise, guided by p-values, 95% confidence intervals and multicollinearity control
  (VIF). Focus on interpretation.
- **Path B — Machine Learning.** All features enter the model and regularization
  (Ridge/LASSO/ElasticNet via SGDRegressor) decides each one's weight, with hyperparameter
  search and 5-fold cross-validation. Focus on prediction.

### 💡 Key insights

- **Purchase frequency** and **historical average ticket** are the strongest spending drivers
  (Pearson correlation of 0.626 and 0.580 with the target).
- On the **external test set**, both paths are essentially tied: R² of 0.864 (Path A) vs. 0.853
  (Path B), both without overfitting.
- On a dataset with few features and no relevant collinearity, **manual curation matches
  automatic selection** and still delivers interpretability — so Path A was adopted as the final
  model, with Path B documented as the right choice for larger datasets with many correlated
  features.
- For CRM and lifecycle work, the drivers translate into actionable levers: recurrence
  (frequency) and order value (average ticket).

### 🛠️ Tools

- Python
- pandas and numpy — data manipulation and analysis
- matplotlib and seaborn — visualization
- scikit-learn — cross-validation, regularization and preprocessing
- statsmodels — OLS regression and inference

### 📁 Repository structure

```
.
├── 01_caminho_A_estatistica_classica.ipynb   # OLS + manual selection (diagnosis)
├── 02_caminho_B_machine_learning.ipynb       # regularization + cross-validation (prediction)
├── Gasto_eCommerce_Dados-1.txt               # dataset
├── apresentacao_estudo_de_caso.pdf           # project presentation
└── README.md
```

### ▶️ How to run

1. Clone the repository or download the files.
2. Open the notebooks in Google Colab or Jupyter Notebook.
3. Make sure `Gasto_eCommerce_Dados-1.txt` is in the same folder as the notebooks.
4. Run the cells in order.

---

*Case developed as a group project: Renan Correia (lead), Bruno Higuti, Michelle Tanaka,
Victor Aquino and Hygor Vaz. Thanks to the team and to the guidance of FIA's MBA in Analytics and AI.*
