# Análise de Viabilidade do Passe Livre no Transporte Público de Curitiba

Este repositório contém a análise de dados completa sobre a viabilidade financeira e o impacto social da implementação de uma política de passe livre (tarifa zero) no sistema de transporte público de Curitiba, com foco em domingos e feriados.

> **Objetivo Principal:** Analisar se o passe livre é viável financeiramente, considerando os custos para o governo/URBS e o impacto na inclusão de populações de baixa renda. O projeto utiliza dados históricos e os resultados de um experimento real (a meia tarifa) para criar uma simulação e gerar recomendações.

## 📈 Principais Resultados

* A política de **Meia Tarifa** ("Domingão Paga Meia") resultou em um **aumento estatisticamente significativo de aproximadamente 34%** no número de passageiros pagantes em domingos e feriados.
* A elasticidade-preço da demanda, calculada a partir do experimento, sugere que o passe livre total poderia gerar um **aumento projetado de 68%** no fluxo de passageiros.
* A simulação estima que o custo anual para subsidiar o passe livre *apenas em domingos e feriados* seria de aproximadamente **R$ 69,4 milhões**.
* A análise histórica (2020-2023) mostra que o sistema já opera com subsídios governamentais consideráveis, especialmente durante e após a pandemia de COVID-19, que causou uma queda drástica no número de passageiros.

## 📂 Estrutura do Repositório

O projeto está organizado da seguinte forma:

* **/data**: Contém todos os datasets brutos utilizados na análise, incluindo dados diários de passageiros, despesas da URBS e a evolução da tarifa técnica.
* **/notebooks**: Contém o Jupyter Notebook `Espinha_Dorsal_do_Projeto_TRANSPORTE_CWB.ipynb` com todo o código da análise, desde a limpeza e tratamento dos dados até a modelagem, testes de hipóteses e visualizações.

## 🛠️ Metodologia

A análise foi conduzida seguindo as seguintes etapas:

1.  **Configuração do Ambiente:** Importação das bibliotecas necessárias (pandas, matplotlib, scipy, seaborn, prophet) e configuração do acesso aos dados.
2.  **Carga e Tratamento dos Dados:** Carregamento dos dados de passageiros, limpeza, conversão de tipos e criação de features como dia da semana e tipo de dia (útil, sábado, domingo, feriado).
3.  **Análise de Impacto da Pandemia:** Classificação dos períodos (Pré, Auge, Pós-pandemia) e análise quantitativa e visual da queda de passageiros.
4.  **Análise de Impacto da Meia Tarifa:**
    * Filtragem de dados para domingos e feriados.
    * Visualização da distribuição de passageiros antes e depois da política.
    * Aplicação de um **Teste t de Hipótese** para verificar a significância estatística do aumento de passageiros.
5.  **Simulação da Viabilidade do Passe Livre:**
    * Cálculo da **Elasticidade-Preço da Demanda** com base nos resultados da meia tarifa.
    * Projeção do aumento de passageiros em um cenário de tarifa zero.
    * Estimativa do **custo anual do subsídio** necessário para cobrir a receita perdida e os custos operacionais adicionais.
6.  **Análise do Subsídio Governamental:** Análise de dados históricos de despesas e tarifa técnica da URBS para contextualizar o custo do novo subsídio.

## 🚀 Como Executar o Projeto

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba.git](https://github.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba.git)
    cd Projeto_Tarifa_Zero_Curitiba
    ```
2.  **Instale as dependências:**
    Certifique-se de ter as principais bibliotecas Python para análise de dados instaladas.
    ```bash
    pip install pandas matplotlib scipy seaborn prophet holidays
    ```
3.  **Execute a análise:**
    Abra e execute o notebook `notebooks/Espinha_Dorsal_do_Projeto_TRANSPORTE_CWB.ipynb` em um ambiente como Jupyter Lab, Jupyter Notebook ou Google Colab.

## 📊 Conclusão e Recomendações

EM CONSTRUÇÃO

## 📚 Fontes dos Dados

* **Dados de passageiros diários:** [URBS - Rede Integrada de Transporte](https://www.urbs.curitiba.pr.gov.br/transporte/rede-integrada-de-transporte/51)
* **Dados de despesas e tarifa técnica da URBS:** [Painel de Dados da URBS](https://lookerstudio.google.com/embed/u/0/reporting/b1ccd1b5-f21a-4374-af10-bc03226b3273/page/c6jRB)
* **Arquivos CSV utilizados na análise:**
    * [Usuários por dia](https://raw.githubusercontent.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba/main/data/usuarios_dia.xlsx)
    * [Despesas (2014-2024)](https://raw.githubusercontent.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba/main/data/DESPESAS_CWB_2014_2024.csv)
    * [Evolução da Tarifa Técnica (2010-2023)](https://raw.githubusercontent.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba/main/data/1.1-evolucao_tarifa_tec_2010-2023.csv)
    * [Passageiros (2020)](https://raw.githubusercontent.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba/main/data/Passageiro_P%C3%BAblico_2020.csv)
    * [Passageiros (2021)](https://raw.githubusercontent.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba/main/data/Passageiro_P%C3%BAblico_2021.csv)
    * [Passageiros (2022)](https://raw.githubusercontent.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba/main/data/Passageiro_P%C3%BAblico_2022.csv)
    * [Passageiros (2023)](https://raw.githubusercontent.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba/main/data/Passageiro_P%C3%BAblico_2023.csv)

---
