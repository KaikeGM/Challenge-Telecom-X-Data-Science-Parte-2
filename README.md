# Challenge Telecom X: Data Science Parte 2/2

# 📊 Predição de Churn com Random Forest

Este projeto tem como objetivo prever o cancelamento de clientes (**churn**) com base em dados de comportamento e serviços contratados, utilizando o algoritmo **Random Forest** em conjunto com técnicas de balanceamento de dados: **BorderlineSMOTE** (oversampling) e **NearMiss** (undersampling).

> Projeto desenvolvido em ambiente Google Colab com foco em classificação binária e avaliação de desempenho por múltiplas métricas.

---

## 🔍 Objetivos

- Prever com precisão os clientes que têm maior probabilidade de cancelar o serviço.
- Tratar o desbalanceamento da variável alvo (`churn`).
- Comparar o desempenho entre diferentes estratégias de amostragem.
- Identificar as variáveis mais importantes para o modelo.

---

## 🧰 Tecnologias e Bibliotecas

- Python 3.11+
- Pandas
- NumPy
- Scikit-learn
- imbalanced-learn
- Matplotlib / Seaborn
- Google Colab

---

## ⚙️ Pipeline do Projeto

1. **Importação e pré-processamento dos dados**
   - Codificação de variáveis categóricas
   - Tratamento de valores ausentes
   - Seleção de features

2. **Divisão dos dados**
   - Treino e teste com `train_test_split`

3. **Balanceamento**
   - **Oversampling com BorderlineSMOTE**
   - **Undersampling com NearMiss**

4. **Modelagem**
   - Algoritmo: `RandomForestClassifier`
   - Pipelines distintas para cada técnica de balanceamento

5. **Avaliação dos Modelos**
   - Acurácia
   - F1-score
   - Curva ROC e AUC
   - Matriz de confusão
   - Importância das variáveis

---

## 📈 Resultados Principais

- **Média de Tenure por Churn:**
  - Churn = 0 → 37.68 meses
  - Churn = 1 → 18.39 meses

- **Top 5 variáveis mais importantes (Oversampling):**
  - `Charges.Total`
  - `Contract_two year`
  - `OnlineSecurity_yes`
  - `Contract_month-to-month`
  - `TechSupport_yes`

- **Top 5 variáveis mais importantes (Undersampling):**
  - `Charges.Total`
  - `Charges.Monthly`
  - `Contract_month-to-month`
  - `Contract_two year`
  - `OnlineSecurity_yes`

> As métricas indicaram que o modelo com **oversampling** obteve melhor recall para a classe minoritária (clientes que cancelam), sendo preferível quando o objetivo é **reduzir churn**.

---

## 📁 Organização dos Arquivos

- `churn_analysis.ipynb` — notebook principal com todo o pipeline
- `dataset.csv` — base de dados (não incluída por padrão)
- `/figuras/` — gráficos e matrizes de confusão gerados

---

## 🚀 Como Executar

1. Acesse o [Google Colab](https://colab.research.google.com/)
2. Faça o upload do notebook `churn_analysis.ipynb`
3. Carregue o arquivo `.csv` da base de dados
4. Execute célula por célula

---

## 🧠 Conceitos Aplicados

- Classificação supervisionada
- Random Forest
- Desequilíbrio de classes
- SMOTE / NearMiss
- Engenharia de atributos
- Interpretação de modelo

---

## 📌 Autor

**Kaike Gabriel Marques de Souza**  
Estudante de Engenharia de Software e Análise de Sistemas  
📫 Contato: [LinkedIn](https://www.linkedin.com/in/seu-perfil) | [Email](mailto:kaike@example.com)

---

## 📄 Licença

Este projeto está sob a licença MIT.  
Sinta-se à vontade para usar, estudar e modificar!

