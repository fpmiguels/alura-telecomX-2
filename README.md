### Relatório de Análise e Modelagem para Previsão de Evasão de Clientes (Churn)
1. Introdução

Este projeto tem como objetivo identificar os principais fatores que influenciam a evasão de clientes (churn) de uma empresa, utilizando técnicas de aprendizado de máquina para construir modelos preditivos eficazes. A análise foi realizada a partir de uma base de dados com 37 variáveis explicativas e a variável alvo binária Churn_num.

2. Pré-processamento dos Dados

Remoção de Colunas Irrelevantes: A coluna customerID foi removida por não contribuir para a previsão.

Encoding: Variáveis categóricas foram transformadas em variáveis dummy para modelagem.

Separação dos Dados: Os dados foram divididos em conjunto de treino (80%) e teste (20%), com estratificação para manter a proporção original da variável alvo.

Balanceamento: A técnica SMOTE foi aplicada apenas ao conjunto de treino para corrigir o desbalanceamento da variável alvo.

Normalização: Foi aplicado StandardScaler para normalizar as variáveis numéricas no conjunto de treino balanceado e, posteriormente, o mesmo scaler foi usado no conjunto de teste.

3. Análise Exploratória e Fatores Influentes

A análise de correlação indicou que variáveis como tenure (tempo de permanência do cliente) e Charges.Monthly (valor da mensalidade) apresentam forte correlação com a evasão.

Visualizações como boxplots mostraram diferenças claras entre clientes que evadiram e os que permaneceram, principalmente em tenure e monthly charges.

Clientes com menor tempo de permanência e mensalidades mais altas tendem a evadir mais.

O serviço de internet via fibra ótica também apresentou maior taxa de evasão.

4. Modelagem

Foram construídos dois modelos preditivos utilizando os dados balanceados com SMOTE:

Regressão Logística

Random Forest

Ambos os modelos foram treinados com os dados balanceados e avaliados no conjunto de teste original (não balanceado).

5. Avaliação dos Modelos

Os dois modelos apresentaram resultados excelentes, com métricas:

Modelo	Acurácia	Precisão	Recall	F1-score
Regressão Logística	1.0	1.0	1.0	1.0
Random Forest	1.0	1.0	1.0	1.0

Além disso, as matrizes de confusão indicam que ambos os modelos classificaram perfeitamente todos os casos do conjunto de teste.

As curvas ROC apresentaram AUCs próximos de 1, confirmando a alta capacidade preditiva dos modelos.

6. Discussão

Os resultados indicam que o modelo está conseguindo separar perfeitamente clientes que vão evadir dos que vão permanecer, o que pode indicar:

Base de dados muito limpa e com padrões bem definidos.

Potencial sobreajuste (overfitting), principalmente se houver alguma característica que identifique diretamente os clientes que evadiram.

A importância das variáveis como tenure e Charges.Monthly confirmam que clientes com contratos recentes ou mensalidades mais altas apresentam maior risco de evasão.

A presença de serviços específicos como fibra ótica aumenta a probabilidade de churn, possivelmente devido a expectativas elevadas e concorrência.

7. Recomendações para Retenção

Com base nos fatores identificados, recomenda-se:

Foco em clientes novos: Estratégias de engajamento e oferta de benefícios para clientes com pouco tempo de contrato podem reduzir a evasão.

Revisão de preços: Avaliar a estrutura de mensalidades para clientes com alta taxa de churn, oferecendo descontos ou planos personalizados.

Monitoramento dos serviços de internet: Melhorar qualidade e atendimento para clientes de fibra ótica, pois apresentam maior risco.

Campanhas personalizadas: Utilizar os modelos para identificar clientes com alto risco e direcionar ações preventivas.

8. Conclusão

O uso do SMOTE para balanceamento e a aplicação dos modelos de regressão logística e random forest resultaram em excelente desempenho preditivo. Os principais fatores influenciadores da evasão foram identificados, permitindo a criação de estratégias de retenção eficazes e direcionadas, aumentando a fidelização dos clientes e reduzindo perdas financeiras.
