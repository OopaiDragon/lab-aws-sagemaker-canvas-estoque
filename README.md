# 📊 Previsão de Estoque Inteligente na AWS com SageMaker Canvas

## Objetivo
Desenvolver um modelo de previsão de estoque utilizando o SageMaker Canvas e documentar o processo em um repositório no GitHub.

## Pré-requisitos
Antes de começar, certifique-se de ter uma conta na AWS. Se precisar de ajuda para criar sua conta, confira nosso repositório [AWS Cloud Quickstart](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque).


## 🎯 Passo a Passo

### 1. Criação do Domínio no SageMaker Canvas
Foi criado um domínio no AWS SageMaker para poder acessar e abrir o SageMaker Canvas.

### 2. Construção do Modelo Customizado
No SageMaker Canvas, selecionamos a opção de criar um modelo customizado para análise preditiva.

### 3. Carregamento e Preparação dos Dados no SageMaker Canvas
Carregamos o dataset `dataset-500-curso-sagemaker-canvas-dio.csv` para o SageMaker Canvas. Os dados utilizados vieram do repositório base. 

### 4. Configuração do Dataset
Configuramos a variável alvo para ser prevista, foi utilizada a configuração padrão do modelo, a que ja é recomendada.

### 5. Execução do Treinamento do Modelo
Selecionamos a opção de Quick Build para construir e treinar o modelo de forma rápida. Iniciamos a análise, e após a conclusão, o SageMaker Canvas forneceu métricas de performance do modelo, como MAE, RMSE, MSE e o impacto das outras colunas em relação ao alvo.

### 6. Análise das Métricas de Performance
Após o treinamento, examinamos as métricas de performance do modelo fornecidas pelo SageMaker Canvas:

#### Mean Absolute Error (MAE)
- **Definição:** O MAE é a média das diferenças absolutas entre os valores previstos pelo modelo e os valores reais.
- **Resultado:** Um MAE de 3.2223 indica que, em média, a previsão da quantidade de estoque pelo modelo está fora por cerca de 3.22 unidades de estoque.
- **Importância:** O MAE é uma medida direta e intuitiva do erro médio absoluto das previsões. É útil porque é fácil de interpretar e está na mesma unidade que os dados de previsão, facilitando a compreensão da precisão do modelo.

#### Mean Squared Error (MSE)
- **Definição:** O MSE é a média dos quadrados das diferenças entre os valores previstos pelo modelo e os valores reais.
- **Resultado:** O MSE foi de 17.2392, indicando que, em média, os quadrados das diferenças entre as previsões do modelo e os valores reais de estoque são 17.2392.
- **Importância:** O MSE penaliza mais severamente grandes erros devido ao quadrado das diferenças. Isso é útil quando queremos garantir que o modelo não tenha grandes desvios nas previsões, mas pode ser menos intuitivo para interpretar, pois está na unidade ao quadrado dos dados originais.

#### Root Mean Squared Error (RMSE)
- **Definição:** O RMSE é a raiz quadrada do MSE e fornece uma medida de erro que está na mesma unidade dos valores previstos e reais.
- **Resultado:** O RMSE de 4.1520 indica que, em média, a previsão da quantidade de estoque pelo modelo está fora por cerca de 4 unidades de estoque.
- **Importância:** O RMSE é uma métrica mais intuitiva do que o MSE porque está na mesma escala dos dados originais. Ele ainda penaliza grandes erros de forma mais severa do que o MAE, proporcionando um equilíbrio entre penalizar grandes desvios e manter a interpretação na mesma unidade dos dados.

### 7. Identificação das Variáveis Mais Influentes
A coluna `DIA` teve uma influência significativa (94.12%) na previsão da quantidade de estoque, conforme identificado pelo SageMaker Canvas. Isso indica que a variável `DIA` é um fator crucial para prever a quantidade de estoque.

### 8. Realização de Previsões
Utilizamos o modelo treinado para realizar previsões de estoque. As previsões foram feitas para diferentes cenários, incluindo variação de dias e promoções. A maior variação ocorreu quando a promoção foi alterada, indicando que a variável de promoção tem um impacto significativo na previsão do estoque para esse produto.


## 📚 Referências
- [Documentação do AWS SageMaker Canvas](https://docs.aws.amazon.com/sagemaker/latest/dg/canvas.html)
- [Repositório Base da DIO](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque)
- [AWS Cloud Quickstart](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque)
