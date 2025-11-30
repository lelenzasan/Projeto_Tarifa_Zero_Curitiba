Análise de Viabilidade do Passe Livre no Transporte Público de Curitiba
Este projeto visa analisar a viabilidade financeira da implementação do passe livre (tarifa zero) aos domingos e feriados no transporte público de Curitiba-PR, considerando os custos para o governo/URBS e o impacto na inclusão de populações de baixa renda.

📋 Tabela de Conteúdo
Definição do Problema
Objetivo do Projeto
Dados Utilizados
Metodologia
Principais Descobertas e Conclusões
Tecnologias e Bibliotecas
Estrutura do Projeto
Como Rodar o Projeto
Licença
📝 Definição do Problema
O transporte público em Curitiba-PR enfrenta desafios como custos operacionais elevados, inclusão social limitada e evasão de passageiros pagantes. A proposta do passe livre busca aumentar o acesso, mas sua sustentabilidade financeira é uma preocupação.

🎯 Objetivo do Projeto
Analisar a viabilidade financeira do passe livre aos domingos e feriados, utilizando dados históricos e resultados de um experimento real (a meia tarifa) para criar simulações e gerar recomendações.

📊 Dados Utilizados
Os dados primários para esta análise são da URBS (Urbanização de Curitiba S/A), especificamente a série temporal do número de usuários diários do transporte público na cidade. Além disso, foram utilizadas:

Dados de Usuários Diários: URBS - Rede Integrada de Transporte
Evolução da Tarifa Técnica: URBS - Tarifas e Custos
Tarifa de Ônibus AMEP: AMEP - Agência de Assuntos Metropolitanos do Paraná
Despesas da Prefeitura de Curitiba: Dados Abertos da Prefeitura de Curitiba
Dados Climáticos: Obtidos de fontes abertas para auxiliar na modelagem preditiva.
Dados Populacionais: Evolução da população de Curitiba.
Para metadados detalhados, dicionário de dados e fontes, consulte o documento: Metadados.

🚀 Metodologia
O projeto segue uma abordagem multifacetada:

Configuração e Importação: Setup do ambiente com as bibliotecas necessárias e montagem do Google Drive para acesso a arquivos.
Teste de Hipóteses: Análise do impacto da meia tarifa aos domingos e feriados no fluxo de passageiros pagantes, utilizando teste t de Student.
Análise da Pandemia: Quantificação do impacto da pandemia (2020-2021) na demanda de passageiros, com visualizações de série temporal e médias móveis.
Cálculo de KPIs da Meia Tarifa: Estimativa da perda de receita, aumento de custo operacional e impacto líquido (subsídio) da política de meia tarifa, considerando tarifas públicas e técnicas variáveis por ano.
Simulação da Viabilidade do Passe Livre:
Elasticidade-Preço da Demanda: Cálculo da elasticidade-preço com base nos dados da meia tarifa.
Projeção de Demanda: Simulação do aumento de passageiros em um cenário de passe livre (redução de 100% na tarifa).
Estimativa de Custo Anual: Projeção do subsídio anual necessário para o passe livre aos domingos e feriados.
Análise Orçamentária: Contextualização do custo do passe livre dentro do orçamento total de subsídio do transporte público de Curitiba para 2025.
Modelagem Preditiva (Machine Learning):
Facebook Prophet: Uso do Prophet para prever a tendência de passageiros, capturando sazonalidades (diária, semanal, anual) e impacto de feriados.
Random Forest Regressor: Desenvolvimento de um modelo de Random Forest para prever o total de passageiros, incorporando features como clima, população, tarifas e lag features.
💡 Principais Descobertas e Conclusões
Impacto da Meia Tarifa
Aumento de Demanda: A política 'Domingão Paga Meia' resultou em um aumento expressivo de +33,90% no uso total do transporte público (e +33,42% entre os pagantes), comprovado estatisticamente.
Impacto Financeiro Líquido: O investimento diário total (subsídio) para a meia tarifa foi de **R 591.343,48∗∗,compostoporR  181.937,21 de perda de receita e R$ 409.406,28 de aumento de custo operacional.
Simulação do Passe Livre (Domingos e Feriados)
Aumento de Demanda Projetado: A implementação do Passe Livre geraria um aumento total de 69.235 passageiros por dia de aplicação (+62,99%).
Custo Anual Estimado: O custo total anual estimado para o passe livre aos domingos e feriados é de aproximadamente R 31.090.264,78∗∗,oqueequivaleauminvestimentomédiomensalde∗∗R  2.590.855,40.
Aumento de Subsídio: Representa um aumento de 319.79% no subsídio anual em comparação com o cenário 'antes'.
Impacto Orçamentário: Este investimento mensal consumiria cerca de 10.33% do subsídio total já destinado ao transporte público de Curitiba (baseado na projeção de R$ 301 milhões para 2025).
Modelagem Preditiva
Prophet: O modelo Prophet capturou bem as tendências e sazonalidades históricas, projetando o fluxo futuro de passageiros com intervalos de confiança.
Random Forest: O modelo Random Forest inicial apresentou um R² muito alto (0.9995), o que foi identificado como vazamento de dados devido à inclusão de TOTAL S/ ISENTOS como feature. Após a correção, as features mais importantes para a previsão de passageiros são:
DIA_SEMANA (dia da semana)
Population (população)
TOTAL_PASSAGEIROS_lag_1 e TOTAL_PASSAGEIROS_lag_7 (passagens do dia anterior e da semana anterior)
TIPO_DIA_Feriado e is_holiday (indicadores de feriado)
Períodos da pandemia e o mês também demonstraram alguma influência.
🛠️ Tecnologias e Bibliotecas
Python: Linguagem de programação principal.
Pandas: Manipulação e análise de dados.
Matplotlib, Seaborn: Visualização de dados.
SciPy: Testes estatísticos.
Holidays: Gestão de datas de feriados.
Prophet: Modelagem de séries temporais para previsão.
NumPy: Computação numérica.
Scikit-learn: Modelagem de Machine Learning (Regressão Linear, Random Forest).
📂 Estrutura do Projeto
O projeto está organizado como um notebook Jupyter, dividido em seções claras:

1 - Configuração do Ambiente: Instalação de bibliotecas e montagem do Drive.
2 - Teste de Hipóteses - Aumento de fluxo de passageiros pagantes: Análise da meia tarifa.
3 - Testes de Normalidade: Análise de distribuição e impacto da pandemia.
4 - Simulação da viabilidade do passe livre: Cálculo da elasticidade e custos do passe livre.
5 - Machine Learning - Tendência de Passageiros: Modelagem com Prophet e Regressão Linear.
6 - Modelagem Preditiva: Random Forest para Passageiros: Construção e avaliação do modelo Random Forest.
🚀 Como Rodar o Projeto
Clonar o Repositório: Faça um clone deste repositório para sua máquina local ou ambiente de desenvolvimento.
git clone https://github.com/lelenzasan/Projeto_Tarifa_Zero_Curitiba.git
Abrir no Google Colab: O projeto foi desenvolvido para ser executado no Google Colab. Abra o arquivo .ipynb diretamente no Colab.
Executar Células: Execute as células do notebook sequencialmente. Certifique-se de que o Google Drive está montado para que os arquivos de dados sejam acessíveis (a célula from google.colab import drive; drive.mount('/content/drive') cuidará disso).
