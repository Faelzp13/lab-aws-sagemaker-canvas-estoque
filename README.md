# 📊 Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

Este projeto faz parte de um desafio prático onde explorei o uso de Machine Learning (ML) low-code para otimizar a gestão de inventário. Utilizei o Amazon SageMaker Canvas em conjunto com dados gerados via Gemini para criar um modelo preditivo capaz de antecipar demandas e auxiliar na tomada de decisão.

## 🎯 Objetivos Deste Desafio de Projeto (Lab)

O foco principal foi desenvolver habilidades práticas com ferramentas de IA sem a necessidade de codificação intensa, focando em:

Aprender o ecossistema de Machine Learning da AWS.
Entender como previsões baseadas em dados podem reduzir custos de estoque e evitar rupturas.
Analisar o impacto de variáveis (como preço e quantidade) no comportamento de vendas.

## 🚀 Passo a Passo

### 1. Modelagem do Dataset

Para simular um cenário real, utilizei o Gemini para gerar um arquivo CSV com o histórico de movimentações. O prompt estruturado garantiu dados consistentes:
 * Colunas: ID_Produto, ID_Cliente, Valor, Data, Quantidade_estoque.
 * Lógica de Reabastecimento: Reposição automática sempre que o nível chegava a 10 unidades.
 * Período: Dados diários de 01/07/2024 a 17/07/2024, com pelo menos 6 transações variadas por dia.

### 2. Construção e Treinamento

No console do SageMaker Canvas, realizei as seguintes etapas:
 * Importação: Carreguei o dataset para a plataforma.
 * Configuração: Identifiquei a coluna alvo para a previsão e ajustei as variáveis de entrada.
 * Processamento: Executei o treinamento do modelo para identificar padrões de consumo.

### 3. Análise de Performance

Após o processamento, o modelo revelou que os fatores de maior peso nas previsões foram:
 * Quantidade em Estoque (quantidade_estoque): O principal motor de influência.
 * Valor do Produto (valor): Influenciador direto na elasticidade da demanda.

### 📈 4. Resultados e Insights

Após o treinamento, o modelo foi submetido a uma análise de cenários (What-if) para validar as previsões de demanda baseadas em diferentes níveis de preço e estoque. Os principais achados foram:

🚀 Sensibilidade ao Preço (Produto P005)
 * Cenário Otimista: Ao manter o valor reduzido de 50.00, a previsão de saída sobe para 18 unidades.
 * Impacto: Notou-se uma correlação direta onde a redução do preço gera um incremento de 63% na demanda projetada.
Recomendação: Estratégia de "Preço Baixo" para maximizar o volume de vendas.

📦 Disponibilidade de Estoque (Produto P003)
 * Gargalo Identificado: Com um estoque baixo de 10 unidades, a previsão de vendas é limitada a 14.
 * Potencial de Crescimento: Ao elevar o estoque simulado para 100 unidades, a demanda prevista salta para 25, representando um impacto     de 80% relacionado puramente à disponibilidade do produto.
Recomendação: Manter níveis de estoque elevados para evitar rupturas e perda de vendas.

🛡️ Resiliência de Mercado (Produto P007)
 * Estabilidade: O produto demonstrou ser extremamente resiliente. Mesmo aumentando o valor de 100.00 para 120.00, a variação na demanda    foi mínima (de 15 para 14 unidades).
Insight: Este item possui baixa elasticidade-preço, permitindo margens de lucro maiores sem sacrificar o volume de saída.

⚠️ Alertas de Reposição
 * P001: O modelo identificou um status crítico de "Necessita Reposição" devido ao estoque atual de apenas 10 unidades frente à demanda     prevista.

### 🏁 Conclusão
O uso do SageMaker Canvas permitiu identificar não apenas quanto vamos vender, mas quais alavancas (preço ou estoque) realmente movem o ponteiro de cada produto. O projeto demonstra que decisões baseadas em dados de Machine Learning reduzem a incerteza e otimizam o capital de giro da empresa.


