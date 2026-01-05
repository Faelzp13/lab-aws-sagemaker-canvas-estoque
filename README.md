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


