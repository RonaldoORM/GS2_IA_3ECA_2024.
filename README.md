- Ronaldo Otsuka Ribeiro Mira - RM: 95595 
- Guilherme Rossi Kirsten - RM: 95230
- Gabriel Gino Jorge Dallape - RM:94862

# GS2_IA_3ECA_2024

## Relatório Técnico

### Descrição do Problema
O crescente número de veículos elétricos (EVs) demanda soluções eficientes para o gerenciamento do carregamento de baterias. Este projeto visa desenvolver um modelo de Inteligência Artificial que utilize técnicas de Machine Learning para otimizar o carregamento, reduzindo custos e melhorando a alocação de recursos energéticos.

---

### Metodologia Utilizada

#### Coleta e Exploração de Dados
Utilizou-se o dataset fornecido contendo informações de estações de carregamento, como consumo de energia, horários de carga, e dias da semana. A análise inicial incluiu:
- Inspeção de colunas e tipos de dados.
- Identificação e tratamento de valores ausentes.
- Análise exploratória de dados, como distribuição de consumo de energia.

#### Pré-processamento
As principais ações nesta etapa foram:
- Preenchimento de valores ausentes usando a mediana.
- Codificação de variáveis categóricas (e.g., dias da semana e tipo de instalação) com `pd.get_dummies`.
- Divisão do dataset em variáveis independentes (features) e dependente (alvo).

#### Divisão do Conjunto de Dados
O dataset foi dividido em conjuntos de treino (80%) e teste (20%) para avaliar o modelo.

#### Modelo de Machine Learning
Foi utilizado o **Random Forest Regressor**, um algoritmo robusto para prever o consumo de energia (`kwhTotal`) com base em variáveis como:
- `stationId` (identificação da estação).
- `chargeTimeHrs` (tempo de carga).
- `weekday` (dia da semana).
- `facilityType` (tipo de instalação, como residencial ou comercial).

#### Avaliação do Modelo
O modelo foi avaliado com as métricas:
- **Erro Médio Quadrático (MSE):** Penaliza grandes erros quadraticamente.
- **Erro Médio Absoluto (MAE):** Mede o erro médio em valores absolutos.
- Um gráfico comparativo dos valores reais e previstos também foi gerado.

---

### Resultados Obtidos

#### Métricas de Avaliação:
- **Erro Médio Quadrático (MSE):** 5.26  
- **Erro Médio Absoluto (MAE):** 1.40 

Esses valores indicam que o modelo apresenta boa capacidade de previsão, com erros controlados.

#### Importância das Features:
O gráfico de importância das features mostrou que `chargeTimeHrs` e `facilityType` são os fatores mais relevantes para prever o consumo de energia.

#### Gráfico de Comparação:
O gráfico entre valores reais e previstos indicou uma forte correlação, com desvios mínimos para a maioria dos pontos.

---

### Conclusões
O modelo desenvolvido foi capaz de prever com eficácia o consumo de energia em estações de carregamento de veículos elétricos. Este sistema pode ser aplicado em cenários reais para:
- Otimizar o uso da rede elétrica.
- Reduzir custos operacionais.
- Melhorar a gestão de recursos energéticos.

#### Próximos Passos:
- Implementação de mais dados para capturar sazonalidades.
- Integração com dados em tempo real para maior precisão.
- Testes com outros algoritmos de Machine Learning para comparação de resultados.
