#### Relatório Analítico: Predição de Evasão de Clientes com SMOTE e Modelos Supervisionados

1. Objetivo

Identificar os principais fatores que influenciam a evasão de clientes (churn) e propor estratégias de retenção com base nos resultados de modelos de classificação e nas variáveis preditoras mais relevantes.

2. Preparação dos Dados

Base de dados: informações de clientes com a variável-alvo churn (0 = permaneceu, 1 = saiu).

Problema identificado: forte desbalanceamento das classes.

Não churn (0): 1033 clientes

Churn (1): 374 clientes

Técnica Utilizada:
Foi aplicado SMOTE no X_train para balancear as classes antes do treinamento dos modelos.

3. Modelos Treinados

Modelo	Acurácia	Precisão	Recall	F1-Score	AUC
Regressão Logística	0.7818	0.5844	0.6203	0.6018	0.815
Random Forest	0.7733	0.5762	0.5561	0.5660	~0.79

A regressão logística apresentou o melhor desempenho geral, com destaque para a métrica de recall (essencial para detectar clientes que tendem a sair) e o maior valor de AUC.

4. Principais Fatores que Influenciam a Evasão

Com base na importância das variáveis (Random Forest) e nos coeficientes da regressão logística, os fatores com maior influência são:

Variáveis mais relevantes
Variável	Impacto na Evasão	Tipo de Relação
Contract	Alto	Contratos mensais têm maior chance de churn
tenure	Alto	Quanto menor o tempo, maior a chance de churn
MonthlyCharges	Alto	Valores mais altos estão associados a maior churn
InternetService	Médio	DSL e Fiber afetam de forma diferente
PaymentMethod	Médio	Pagamentos com cartão virtual ou boletos tendem a ter mais churn
TechSupport	Médio	Ausência de suporte técnico aumenta churn
OnlineSecurity	Médio	Falta de segurança online contribui para evasão

Outras variáveis com influência menor, mas que ajudam: PaperlessBilling, StreamingTV, OnlineBackup, Dependents.

5. Estratégias de Retenção Recomendadas
   
Com base nas variáveis mais influentes, recomenda-se:

Incentivar Contratos Anuais

Problema: Clientes com contratos mensais são mais propensos a sair.
Solução: Oferecer descontos, brindes ou benefícios adicionais para contratos de 12 ou 24 meses.

Ajustar Planos com Alto Valor Mensal

Problema: Clientes com MonthlyCharges elevados demonstram maior taxa de evasão.
Solução: Criar planos personalizados com menos serviços, ou oferecer benefícios em fidelização.

Reforçar o Suporte Técnico e Segurança Online

Problema: Falta de suporte e segurança estão associadas a maior churn.
Solução: Ampliar comunicação sobre os benefícios desses serviços e oferecer suporte proativo.

Monitorar Clientes com Baixa Permanência

Problema: Clientes novos (baixo tenure) são mais instáveis.
Solução: Criar campanhas de onboarding e acompanhamento no primeiro mês, reduzindo a frustração inicial.

Oferecer Benefícios para Pagamentos Automatizados

Problema: Pagamentos por boleto são menos confiáveis.
Solução: Estimular o uso de cartão de crédito/débito com cashback, bônus ou agendamento automático.

6. Conclusão
O projeto demonstrou que, ao aplicar técnicas de balanceamento como SMOTE, é possível melhorar significativamente a capacidade de detectar clientes propensos à evasão. A regressão logística, além de interpretar bem os fatores, apresentou bom desempenho geral com AUC de 0.815.

As variáveis ligadas ao contrato, tempo de permanência e valor mensal são as mais críticas para a evasão. Com estratégias direcionadas a esses fatores, é possível reduzir o churn e melhorar a fidelização.
