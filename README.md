
# 🚩 Challenge Telecom X: Data Science Parte 2/2

Este projeto visa construir um modelo de Machine Learning robusto para prever o cancelamento de clientes (**Churn**) em uma operadora de telecomunicações. O foco principal foi superar o **desbalanceamento de classes** (apenas 25% Churn) para garantir que os clientes de alto risco sejam capturados de forma eficaz.

-----

## 🚀 Resultados e Impacto Estratégico

O melhor modelo (Random Forest + NearMiss) foi otimizado para um *threshold* de **0.4** para priorizar a identificação de clientes em risco:

| Métrica | Valor (Otimizado) | Implicação Estratégica |
| :--- | :---: | :--- |
| **F1-Score** | **60%** | Máximo equilíbrio entre Precision e Recall. |
| **Recall (Captura)** | **81%** | O modelo consegue identificar **8 em cada 10 clientes** que realmente fariam Churn. |
| **Precision** | **47%** | 47% dos clientes sinalizados para retenção realmente iriam evadir. |

### 💡 Principais Insights de Negócio

  * **Fidelidade é o Chave:** A variável **`Tenure`** (Tempo de Contrato) é o preditor mais importante, seguida por `Charges.Monthly` (Gasto Mensal). Clientes que evadirão têm uma média de **18.39 meses** de contrato, significativamente menor que os **37.68 meses** dos clientes fiéis.
  * **Melhor Abordagem:** O **Random Forest** combinado com **Undersampling (NearMiss)** provou ser a técnica mais eficaz para lidar com o desequilíbrio e maximizar o F1-Score.

-----

## ⚙️ Pipeline de Modelagem

### 1\. Importação e Pré-processamento

  * **Engenharia de Atributos:** Criação da variável **`Tenure`** (`Charges.Total` / `Charges.Monthly`).
  * **Codificação:** Conversão de variáveis categóricas (como `Contract` e `InternetService`) para o formato **One-Hot Encoding** (`pd.get_dummies`).
  * **Seleção de Features:** Utilização das **10 *features* mais importantes** (incluindo `Tenure`, `Charges.Monthly`, `Contract_month-to-month`, e `OnlineSecurity_no`) para simplificar e otimizar o modelo.

### 2\. Balanceamento e Otimização

  * **Estratégias de Imbalance:** Uso de **BorderlineSMOTE (Oversampling)** e **NearMiss (Undersampling)** dentro de *Pipelines* para aplicar o balanceamento apenas no conjunto de treino.
  * **Otimização:** Aplicação de **GridSearchCV** para encontrar a melhor combinação de hiperparâmetros para os modelos **RandomForest** e **DecisionTree**, focando no **F1-Score**.

### 3\. Avaliação e Decisão

  * **Métricas Robustas:** Foco em **Recall** (prioridade no Churn), **Precision** e **F1-Score**, adequadas para desbalanceamento.
  * **Ajuste Fino (Threshold):** Ajuste do *threshold* de probabilidade de **0.5 para 0.4** para maximizar o F1-Score, garantindo que mais clientes em risco sejam sinalizados para retenção.

-----

## 🚀 Como Executar e Testar o Modelo

O modelo final treinado foi serializado (`.pkl`) e está disponível no repositório. Você pode testá-lo em tempo real usando o script de teste interativo:

### Pré-requisito

1.  **URL do Modelo:** O script puxa o modelo `melhor_modelo.pkl` diretamente do GitHub.

### Teste Interativo (Previsão de um Cliente)

Utilize a última célula do notebook para testar a previsão de Churn de um cliente, inserindo seus dados. O script solicitará as informações e aplicará o pré-processamento e o *threshold* de 0.4 automaticamente.

-----

## 🧠 Conceitos Aplicados

  - **Classificação supervisionada** (Churn Prediction)
  - **Random Forest** e **Árvore de Decisão**
  - **Tratamento de Desequilíbrio de Classes** (SMOTE / NearMiss)
  - **Otimização de Hiperparâmetros** (Grid Search)
  - **Engenharia de Atributos** (`Tenure`)
  - **Interpretação de Modelo** (Feature Importance e Threshold Otimizado)

-----

## 📌 Autor

- **Kaike Gabriel Marques de Souza**
- Estudante de Técnico em Desenvolvimento de Sistemas
- 📫 Contato: [LinkedIn](https://www.google.com/search?q=https://www.linkedin.com/in/kaike-gabriel-marques-de-souza-042975333) | [Email](mailto:kaikegmds@gmail.com)

-----

## 📄 Licença

Este projeto está sob a licença MIT.
Sinta-se à vontade para usar, estudar e modificar.
