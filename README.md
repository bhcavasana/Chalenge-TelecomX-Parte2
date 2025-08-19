# 📊 Projeto de Previsão de Churn - Telecom X
### _Uma solução de Data Science para retenção proativa de clientes_

---

## 🎯 O Desafio

A Telecom X, como muitas empresas do setor, enfrenta o desafio constante da evasão de clientes (churn). As estratégias de retenção, muitas vezes reativas, não eram suficientes para mitigar a perda de receita e a deterioração da base de clientes.

O objetivo deste projeto foi sair da reatividade e entrar na **proatividade**. Nossa missão foi desenvolver uma solução de Machine Learning capaz de:

1.  **Prever com alta acurácia** quais clientes têm a maior probabilidade de cancelar seus serviços.
2.  **Identificar os principais fatores** que levam a essa decisão.
3.  **Gerar insights** para a criação de um plano de ação estratégico e direcionado.

---

## 🛠️ Tecnologias Utilizadas

Este projeto foi construído utilizando o ecossistema Python para Data Science. As principais bibliotecas foram:

-   **Análise e Manipulação de Dados:** Pandas, NumPy
-   **Visualização de Dados:** Matplotlib, Seaborn
-   **Machine Learning e Modelagem:** Scikit-learn
-   **Técnicas de Balanceamento:** Imbalanced-learn (para o SMOTE)

---

## 🚀 Pipeline do Projeto

A solução foi desenvolvida seguindo um pipeline estruturado de Data Science para garantir robustez e reprodutibilidade.

| Etapa | Descrição |
| :--- | :--- |
| **1. Análise Exploratória (EDA)** | Investigamos os dados para entender o perfil dos clientes, a distribuição das variáveis e as primeiras correlações com o churn. |
| **2. Pré-Processamento** | Preparamos os dados para os algoritmos, aplicando *One-Hot Encoding* para transformar variáveis categóricas em um formato numérico. |
| **3. Modelagem Baseline** | Treinamos e avaliamos três modelos iniciais (Regressão Logística, Random Forest, Gradient Boosting) para estabelecer uma linha de base de performance. |
| **4. Otimização Avançada** | Elevamos o potencial do melhor modelo (Gradient Boosting) com duas técnicas cruciais: **SMOTE**, para corrigir o desbalanceamento de classes e ensinar o modelo a identificar melhor a minoria (churn), e **GridSearchCV**, para encontrar a combinação ótima de hiperparâmetros. |
| **5. Avaliação e Escolha Final** | Comparamos todos os modelos com base em métricas estratégicas para o negócio (com foco especial em **Recall**) e selecionamos o modelo campeão. |

---

## 📊 Resultados e Análise

Após o processo de otimização, o modelo **Gradient Boosting Otimizado** se provou a ferramenta mais eficaz para o desafio.

### Performance do Modelo Final

A otimização com SMOTE foi fundamental para criar um modelo especialista em **detectar o churn**, como visto na métrica de **Recall**.

| Modelo | Recall (Capacidade de Detecção) | AUC (Performance Geral) | Precisão |
| :--- | :--- | :--- | :--- |
| **🏆 GB Otimizado (Final)** | **75.1%** | **0.844** | **0.561** |
| Gradient Boosting (Baseline) | 52.1% | 0.849 | 0.659 |
| Regressão Logística | 53.7% | 0.844 | 0.632 |

> **Principal Insight:** O modelo final é capaz de **identificar 3 de cada 4 clientes** que estão prestes a cancelar, um aumento de mais de 21 pontos percentuais na capacidade de detecção em relação aos modelos baseline. Ele faz isso de forma estratégica, aceitando gerar mais "alarmes falsos" (menor precisão) para garantir que o mínimo de clientes em risco passe despercebido.

### Principais Fatores de Risco (Drivers de Churn)

O modelo nos permitiu identificar claramente os principais sinais de alerta:

* 🔑 **Contrato "Mês a Mês":** O fator de maior impacto. A falta de um vínculo de longo prazo é o principal preditor de cancelamento.
* ⏳ **Baixo Tempo de Casa (Tenure):** Clientes com poucos meses de serviço são muito mais voláteis.
* 🌐 **Serviço de Fibra Ótica:** Clientes deste serviço premium tendem a cancelar mais, exigindo uma investigação focada em preço, concorrência e qualidade percebida.
* 💳 **Pagamento com Cheque Eletrônico:** O atrito de um pagamento não automatizado é um fator de risco relevante.

---

## 💡 Plano de Ação Estratégico

Com base nos resultados, propomos um plano de ação focado em transformar dados em resultados financeiros.

1.  **🎯 Implementar o "Radar de Churn":** Integrar o modelo final ao CRM para gerar um **score de risco** semanal para cada cliente, criando uma lista de ação priorizada para a equipe de retenção.
2.  **🤝 Campanhas de Fidelização:** Lançar ofertas direcionadas para clientes com **contrato Mês a Mês** e baixo **tenure**, incentivando a migração para planos anuais com benefícios claros.
3.  **🔬 Força-Tarefa "Fibra Ótica":** Criar uma equipe multidisciplinar para diagnosticar a causa do churn no segmento de **Fibra Ótica**, avaliando a jornada do cliente de ponta a ponta.
4.  **💸 Otimizar a Jornada de Pagamento:** Desenvolver campanhas de incentivo para que clientes que usam **Cheque Eletrônico** migrem para métodos automáticos (Cartão de Crédito, Débito em Conta).

---

## ⚙️ Como Executar o Projeto

Para replicar esta análise, siga os passos abaixo:

1.  **Pré-requisitos:**
    * Python 3.8 ou superior
    * Jupyter Notebook ou qualquer IDE compatível (ex: VS Code)

2.  **Clone o Repositório:**
    ```bash
    git clone [https://github.com/bhcavasana/Chalenge-TelecomX-Parte2.git](https://github.com/bhcavasana/Chalenge-TelecomX-Parte2.git)
    cd Chalenge-TelecomX-Parte2
    ```

3.  **Crie um Ambiente Virtual (Recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows: venv\Scripts\activate
    ```

4.  **Instale as Dependências:**
    Crie um arquivo `requirements.txt` com o conteúdo abaixo e execute o comando de instalação.

    **`requirements.txt`:**
    ```
    pandas
    numpy
    matplotlib
    seaborn
    scikit-learn
    imbalanced-learn
    jupyter
    ```

    **Comando de Instalação:**
    ```bash
    pip install -r requirements.txt
    ```

5.  **Execute o Jupyter Notebook:**
    ```bash
    jupyter notebook TelecomX_BR_Parte2.ipynb
    ```

---

## 👨‍💻 Autor

| [<img src="https://avatars.githubusercontent.com/bhcavasana" width=115><br><sub>Bruno Cavasana</sub>](https://github.com/bhcavasana) |
| :---: |
| **Economista, Analista Dados e Machine Learning Junior** <br /><br /> [<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" height="30" alt="linkedin logo"  />](https://www.linkedin.com/in/bruno-cavasana-04326b2a/)  [<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" height="30" alt="github logo"  />](https://github.com/bhcavasana) |
