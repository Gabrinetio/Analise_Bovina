# 🐮 AgroTech: Predição de Peso Bovino com Deep Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0%2B-orange)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)

## 📄 Sobre o Projeto

No agronegócio, o peso do animal é a métrica mais importante para definir o ponto de abate e o valor de venda. No entanto, pesar gado exige infraestrutura pesada (balanças de curral), estressa o animal (perda de peso) e exige mão de obra.

Este projeto propõe uma **solução de "Balança Digital"**: uma Rede Neural Profunda (Deep Learning) capaz de estimar o peso do animal com alta precisão utilizando apenas duas medidas corporais simples: **Perímetro Torácico** e **Comprimento Corporal**.

O modelo simula a aplicação em um aplicativo mobile, onde o produtor insere as medidas e obtém o peso instantaneamente.

## 🚀 Destaques Técnicos

* **Dados Sintéticos Realistas:** Geração de um dataset com 5.000 animais baseado na *Fórmula de Schaeffer* e adição de ruído estocástico para simular erros reais de campo.
* **Feature Engineering:** Otimização do modelo através da criação de variáveis físicas (Volume Estimado e Área Corporal) para acelerar a convergência da Rede Neural.
* **Deep Learning Otimizado:** Uso de arquitetura MLP (Multi-Layer Perceptron) com *BatchNormalization*, *Dropout* e *Learning Rate Decay*.
* **MLOps & Deploy:** Pipeline completo de salvamento do modelo (`.keras`) e dos escaladores (`.pkl`) para simulação de produção.

## 🛠 Tecnologias Utilizadas

* **Linguagem:** Python
* **Machine Learning:** TensorFlow, Keras, Scikit-Learn
* **Manipulação de Dados:** Pandas, NumPy
* **Visualização:** Matplotlib, Seaborn
* **Persistência:** Joblib

## 📊 Performance e Resultados

O modelo atingiu um nível de precisão comparável às variações naturais de uma balança física.

| Métrica | Resultado | Descrição |
| :--- | :--- | :--- |
| **Assertividade** | **~96.4%** | Taxa de acerto média (100 - MAPE) |
| **Erro Médio (MAE)** | **~16.6 kg** | Margem de erro absoluta para mais ou menos |
| **R² Score** | **0.94** | O modelo explica 94% da variação de peso |

### Interpretação dos Gráficos gerados no Notebook

#### 📉 1. Curva de Aprendizado (Loss)
Mostra o erro diminuindo conforme o tempo passa. As linhas de **Treino** e **Validação** descem juntas, indicando que o modelo aprendeu as regras gerais e não apenas decorou os dados (*sem Overfitting*).

#### 🎯 2. Real vs. Previsto
Compara o peso real (Eixo X) com a previsão da IA (Eixo Y). Os pontos formam uma linha diagonal estreita sobre a linha vermelha de perfeição, provando a alta consistência do modelo.

#### 🔔 3. Distribuição dos Erros
A maioria dos erros está concentrada no **Zero** (formato de sino/Gaussiana). Isso confirma que o modelo não é viciado (*unbiased*), ou seja, ele não tem tendência de "chutar" sempre para cima ou para baixo.

#### 📐 4. A Física (Volume vs Peso)
Demonstra que a Rede Neural aprendeu a correlação física correta: quanto maior o volume corporal estimado, maior o peso, seguindo uma curva exponencial suave.

## 📂 Estrutura do Projeto

```text
AgroTech-Weight-Prediction/
│
├── notebook_boi_digital.ipynb   # Código completo (Geração, Treino e Análise)
├── dataset_boi_completo.csv     # Dataset gerado (5.000 registros)
├── modelo/                      # Arquivos para Deploy
│   ├── modelo_boi_senior.keras  # O modelo treinado
│   ├── scaler_input.pkl         # Normalizador de entrada
│   └── scaler_output.pkl        # Normalizador de saída
│
└── README.md                    # Documentação


```
## 💻 Como Executar

1. Clone este repositório:

```bash
git clone [https://github.com/SEU-USUARIO/AgroTech-Weight-Prediction.git](https://github.com/SEU-USUARIO/AgroTech-Weight-Prediction.git)

```

2. Instale as dependências:

```bash
pip install pandas numpy tensorflow scikit-learn seaborn matplotlib joblib

```

3. Execute o notebook `notebook_boi_digital.ipynb` no Jupyter ou Google Colab.

## 🔮 Próximos Passos

* Desenvolver uma interface Web simples com **Streamlit**.
* Implementar visão computacional para medir o boi automaticamente através de fotos, eliminando a fita métrica.

---

**Autor:** Gabriel Santana



