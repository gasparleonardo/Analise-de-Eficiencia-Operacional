# Análise de Eficiência Operacional e Inteligência de Negócios — Call Center

## Descrição do Projeto
Este projeto foi desenvolvido com o objetivo de analisar a performance e a eficiência operacional de um Call Center (empresa fictícia *CallMeMaybe*). A partir de dados históricos de chamadas e cadastros de clientes, foi estruturado um pipeline de análise para identificar gargalos de produtividade, classificar o desempenho de mais de 1.000 operadores e validar hipóteses de negócios de forma científica.

---

## Tecnologias e Ferramentas Utilizadas
* **Linguagem:** Python
* **Manipulação e Tratamento de Dados:** Pandas
* **Análise Estatística:** SciPy (Módulo Stats)
* **Visualização de Dados:** Matplotlib e Seaborn
* **Ambiente de Desenvolvimento:** Jupyter Notebook / Google Colab

---

## Pipeline de Dados e Metodologia

### 1. Limpeza e Preparação dos Dados
* Tratamento de valores ausentes (*missing values*) e remoção de dados duplicados para garantir a integridade das métricas.
* Conversão de tipos de dados (como formatação de strings para `datetime` e ID de operadores de `float` para `int`).

### 2. Análise Exploratória de Dados (AED) & Engenharia de Atributos
* Criação de métricas de negócios personalizadas através do agrupamento de dados (`groupby` e `agg`).
* Desenvolvimento do indicador de **Tempo de Espera (*Waiting Time*)**, calculado pela diferença entre a duração total da chamada e o tempo de conversa ativa.
* Cálculo das **Taxas de Perda (*Missed Calls*)** por operador.
* Automatização das regras de classificação de desempenho (Eficiente vs. Ineficiente) via funções customizadas aplicadas linha por linha no dataset.

### 3. Testes Estatísticos e Validação
* Análise descritiva detalhada (médias, medianas e quartis) para estabelecimento empírico de *thresholds* (limites de corte).
* Aplicação do teste não-paramétrico de **Mann-Whitney (U-test)** com nível de significância de 5% ($\alpha = 0.05$) para validar se a diferença no tempo de espera entre os grupos era estatisticamente significativa.

### 4. Visualização de Dados
* Geração de gráficos de barras para distribuição de frequência das classificações.
* Construção de **Boxplots** comparativos para analisar a dispersão e identificar *outliers* no tempo médio de espera.
* Implementação de gráficos de distribuição por subplots para avaliar os principais fatores de arrasto da operação.

---

## Principais Insights & Impacto de Negócio
* **Quebra de Intuição:** O teste estatístico resultou em um *p-valor* de ~0.298, comprovando que, ao contrário da suposição inicial, o tempo médio de espera na linha *não* era o diferencial entre operadores eficientes e ineficientes.
* **Identificação do Gargalo:** A análise revelou que **71,7% da ociosidade e da perda de eficiência** da operação eram causadas pelo alto índice de chamadas abandonadas (*inbound*) e pela baixa produtividade em ligações ativas (*outbound*).
* **Tomada de Decisão:** O diagnóstico permitiu recomendar ações estratégicas focadas em sistemas de alertas de fila e recalibragem de metas de ligações ativas, reduzindo o risco de perda de clientes (*churn*).

---

## Como Executar o Projeto

1. Clone o repositório:
   ```bash
   git clone [https://github.com/seu-usuario/nome-do-repositorio.git](https://github.com/seu-usuario/nome-do-repositorio.git)
