# Projeto Final: Classificador de Notícias Falsas com Machine Learning

Repositório desenvolvido para a entrega do **Projeto Final de Fundamentos em Inteligência Artificial.**

---

## 1. Visão Geral e Objetivo
O objetivo deste projeto é desenvolver, treinar e comparar modelos de aprendizado de máquina tradicionais capazes de classificar notícias automaticamente, determinando se uma notícia é verdadeira ou falsa (*fake news*).

* **Tipo da Tarefa:** Classificação Binária (`0` para Notícia Real/Verdadeira e `1` para Fake News).
* **Atributo-Alvo:** `Label` (categórico binário).
* **Atributos Preditivos:** `Noticia` (texto contendo o conteúdo avaliado).

---

## 2. Integrantes do Grupo
* **Bruno Lopes dos Santos**
* **Nayara Oliveira Santos**
* **Pericles dos Santos Leite**

---

## 3. Fonte dos Dados
* **Dataset Utilizado:** `fakerecogna2.csv` (localizado no diretório `./data/`).
* **Carregamento:** Realizado com tratamento de codificação (`encoding='latin-1'`) para garantir a leitura correta de caracteres e acentuações da língua portuguesa.

---

## 4. Organização do Repositório
```text
├── sample_data/
│   └── fakerecogna2.csv
├── fake-news.ipynb
└── README.md
```

---

## 5. Instruções para Execução no Google Colab
Execução no Google Colab:

1. Acessar [Google Colab](https://colab.research.google.com/).
2. Fazer upload do notebook e do conjunto de dados `fakerecogna2.csv` nos arquivos na pasta content/sample_data/.
3. Executar.

---

## 6. Análise Exploratória e Pré-processamento
* **Análise Exploratória:** Plotagem da distribuição das classes do atributo-alvo (`Label`).
  
* **Divisão dos Dados:** Utilização de `train_test_split` com proporção de 70% para treino e 30% para teste (`test_size=0.3`), empregando o parâmetro `stratify=labels` para preservar a proporção entre as classes e fixando `random_state=42`.
  
* **Vetorização (TF-IDF):** Conversão dos textos em matrizes numéricas por meio do `TfidfVectorizer`.

---

## 7. Modelos Utilizados
Conforme os requisitos experimentais, foram empregados os seguintes classificadores lineares:
* **SGD Classifier (`SGDClassifier`):** Modelo linear otimizado via Gradiente Descendente Estocástico.
* **Random Forest (`RandomForestClassifier`):** Modelo baseado em conjunto de árvores de decisão (`n_estimators=100`), útil para capturar interações não-lineares entre os termos preditivos.

---

## 8. Principais Resultados e Métricas
* **Matriz de Confusão:** Visualizada via mapas de calor (`seaborn.heatmap`) para análise de falsos positivos e falsos negativos, os resultados encontram-se na pasta (`Resultados\`).
* **Acurácia:** Taxa geral de acertos do modelo (SGD: 94,54%, RandomForest: 93,28%).
  $$\text{Acurácia} = \frac{TP + TN}{TP + TN + FP + FN}$$
* **Precisão:** Proporção de predições corretas para notícias falsas (SGD: 95,58%, RandomForest: 94,84%).
  $$\text{Precisão} = \frac{TP}{TP + FP}$$
* **Revocação:** Capacidade do modelo de identificar todas as notícias falsas reais (SGD: 93,40%, RandomForest: 91,53%).
  $$\text{Revocação} = \frac{TP}{TP + FN}$$
* **F1-Score:** Média harmônica entre precisão e revocação (SGD: 94,48%, RandomForest: 93,16%).
  $$\text{F1-Score} = 2 \times \frac{\text{Precisão} \times \text{Revocação}}{\text{Precisão} + \text{Revocação}}$$
**Em que:**
* **TP (Verdadeiro Positivo):** Casos em que o modelo previu corretamente a classe como positiva (Fake News).
* **TN (Verdadeiro Negativo):** Casos em que o modelo previu corretamente a classe como negativa (Notícia Real).
* **FP (Falso Positivo):** Casos em que o modelo previu incorretamente como positiva (classificou como Fake News uma notícia que era Real).
* **FN (Falso Negativo):** Casos em que o modelo previu incorretamente como negativa (classificou como Real uma notícia que era Fake News).

## 9. Divisão das Contribuições
* **Bruno Lopes dos Santos:** Responsável pela extração de métricas de desempenho, geração das matrizes de confusão e validação dos resultados.
* **Pericles dos Santos Leite:** Responsável pela condução da análise exploratória, pre-processamento e tratamento do dataset.
* **Nayara Oliveira Santos:** Responsável pela arquitetura geral do script e integração com os modelos de machine learning.

## 10. Link para o vídeo 
* **https://youtu.be/9emoJtHiJKE**

## 11. Declaração sobre o uso de IA
* **Neste projeto foi utilizado a IA generativa Gemini para estruturação do README.**
