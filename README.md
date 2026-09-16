# 💳 Detecção de Fraudes em Transações Financeiras

Projeto de Machine Learning focado em identificar transações de cartão de crédito fraudulentas, lidando com o desafio do extremo desbalanceamento de dados e priorizando a taxa de detecção (Recall).

---

## 📌 Visão Geral do Problema
Em dados financeiros reais, as fraudes representam uma fração mínima do total de transações (geralmente menos de 0,2%). O objetivo central deste projeto é construir um classificador capaz de capturar o maior número possível de fraudes (minimizar Falsos Negativos), sem gerar um volume excessivo de alarmes falsos para os clientes legítimos.

## 🛠️ Tecnologias e Bibliotecas
- **Linguagem:** Python
- **Ambiente:** Google Colab
- **Manipulação de Dados:** Pandas, NumPy
- **Visualização:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-Learn (Logistic Regression, Random Forest, Pipeline, GridSearchCV)
- **Algoritmo Avançado:** XGBoost
- **Tratamento de Desbalanceamento:** Imbalanced-learn (SMOTE, Undersampling)
- **Explicabilidade (XAI):** SHAP (*SHapley Additive exPlanations*)

## 🔄 Fluxo de Desenvolvimento
1. **Pré-processamento:** Padronização de escala com `StandardScaler` e divisão dos dados com amostragem estratificada (`stratify`).
2. **Tratamento do Desbalanceamento:** Avaliação comparativa entre *Undersampling*, *Oversampling* (SMOTE) e ajuste de pesos de classe (`class_weight='balanced'`, `scale_pos_weight`).
3. **Modelagem:** Treinamento e avaliação de Regressão Logística, Random Forest e XGBoost.
4. **Ajuste de Limiar de Decisão:** Otimização do *Threshold* para elevar a sensibilidade (Recall) do sistema.
5. **Ajuste de Hiperparâmetros:** Busca exaustiva com `GridSearchCV` focado na métrica de Recall.
6. **Interpretabilidade (XAI):** Uso do SHAP para auditar o impacto de cada variável na decisão final do modelo.

## 📈 Resultados e Avaliação
- **Métricas Chave:** Foco em **Recall**, **Curva ROC-AUC** e **Curva Precision-Recall**.
- **Desempenho:** O modelo XGBoost com ajuste de pesagem de classe e limiar customizado obteve a melhor performance para captura de transações suspeitas.

## 🚀 Como Executar
1. Clone este repositório ou abra o notebook diretamente no [Google Colab](https://colab.research.google.com/).
2. Garanta a instalação das dependências executando no notebook:
   ```bash
   pip install shap xgboost imbalanced-learn
