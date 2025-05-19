# 🎓 Admission Prediction (Previsão de Admissão)

## 📌 Sobre o projeto
Este projeto tem como objetivo prever se um aluno será **admitido em uma faculdade** usando **Regressão Logística**.  

### 🔎 Contexto  
Somos alunas de **Mestrado** e estamos cursando a disciplina de **Machine Learning**. A ideia é pegar o que já nos foi ensinado, juntamente com conteúdos públicos da Internet e criar um modelo usando Regressão Logística. 

Utilizamos o **dataset público** disponível no GitHub de ["KatePril"](https://github.com/KatePril/admission-prediction), e o **pré-processamento** foi baseado no código de:  
📌 [Notebook de KatePril](https://github.com/KatePril/admission-prediction/blob/main/notebook.ipynb).  

---

## 📊 Estrutura do modelo
Inicialmente, planejamos trabalhar com **variáveis categóricas e numéricas**, mas após diversas tentativas de tratamento dos dados categóricos, decidimos focar apenas em **variáveis numéricas**.  

### 🔹 **Variáveis utilizadas**
- **GMAT** → Graduate Management Admission Test, exame padronizado para MBA e pós-graduações em negócios. Mede habilidades **quantitativas, verbais e analíticas**.  
- **work_asp** → Abreviação para "Work Aspirations" (aspirações profissionais), podendo representar metas de carreira ou experiência no mercado de trabalho.  
- **GPA** → Grade Point Average (Média de Notas), sistema de avaliação acadêmica usado em escolas e universidades, principalmente nos EUA.  

---

## 🔬 Divisão do modelo
O modelo foi estruturado em **três conjuntos de dados**:

✅ **Treino** → Para ajustar os pesos da regressão logística.  
✅ **Validação** → Para testar e melhorar os hiperparâmetros.  
✅ **Teste** → Para avaliar a performance do modelo com dados nunca vistos.  

---

## 🎯 Resultados
Como trabalhamos com **apenas três variáveis**, era esperado que nosso modelo não tivesse um desempenho ideal.  

📌 **Acurácia do modelo**: **47% (0.47096774193548385)**  
🔎 **O que isso significa?**  
Nosso modelo está treinado tanto quanto uma escolha aleatória – equivalente a jogar uma moeda para decidir entre **"admitido"** ou **"não admitido"**. Isso mostra que, nesse estágio, **ele ainda não está bem implementado** para previsões confiáveis.  

---

## 📈 Visualizações e métricas
🔹 **Curva ROC** → Avalia a capacidade do modelo de **diferenciar as classes**.  
![image](https://github.com/user-attachments/assets/37cd0293-f907-4456-bc09-067c628c2f25)

### 🔍 Interpretação:

- Uma curva ROC ideal se aproxima do canto superior esquerdo (alta TPR e baixa FPR).
- A **linha tracejada diagonal** representa o desempenho de um modelo aleatório (AUC = 0.5).
- Quanto mais **acima dessa linha**, melhor o desempenho do modelo.

### ⚠️ Observações:

- AUC (Área sob a Curva): **0.41**
- Isso indica que o modelo tem **baixa capacidade de diferenciação entre as classes** (pior do que um modelo aleatório).
- Pode estar relacionado a:
  - Dados desbalanceados;
  - Variáveis com pouco poder preditivo;
  - Underfitting (modelo simples demais).

🔹 **Matriz de confusão** → Indica **acertos e erros** nas previsões do modelo.  
![image](https://github.com/user-attachments/assets/16dfd028-c0d1-40e6-95fc-71071aedc7d3)

A matriz de confusão resultante do modelo sobre o conjunto de teste apresentou os seguintes valores:

|                     | **Previsto: 0** | **Previsto: 1** |
|---------------------|----------------|----------------|
| **Real: 0** (Neg.)  | 407 (✅ TN)     | 389 (❌ FP)     |
| **Real: 1** (Pos.)  | 103 (❌ FN)     | 31 (✅ TP)      |

### 🔍 Interpretação:

- **407 Verdadeiros Negativos (TN)**: o modelo acertou ao prever "não admitido".
- **31 Verdadeiros Positivos (TP)**: o modelo acertou ao prever "admitido".
- **389 Falsos Positivos (FP)**: o modelo previu "admitido", mas na verdade não era.
- **103 Falsos Negativos (FN)**: o modelo previu "não admitido", mas a pessoa foi admitida.

### ⚠️ Observações:

- O modelo está com **baixo desempenho na detecção dos casos positivos (admitidos)**.
-  A quantidade de **falsos positivos (389)** e **falsos negativos (103)** é alta, o que indica **baixa precisão e revocação** para a classe positiva.
- É importante considerar o **balanceamento das classes** e talvez aplicar **técnicas de ajuste de limiar, reamostragem ou tuning**.

Este tipo de análise é essencial para entender **como e onde o modelo está errando**, e como ele pode ser melhorado. 

---
### 👥 Autoras: 

- Larissa Soares de Souza 
- Lídia Gabrielly Dutra de Meneses Santos 
  
