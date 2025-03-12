# Regressão Linear por Mínimos Quadrados

## Visão Geral
Este estudo implementa e analisa modelos de regressão linear utilizando o método dos Mínimos Quadrados para prever notas em concursos com base em dados de estudo. O objetivo é entender a relação entre o tempo de preparação e desempenho, construindo um modelo preditivo.

## Conjunto de Dados
Os dados utilizados contêm informações de 25 candidatos com as seguintes variáveis:
- `inicio_estudo`: Quando o candidato começou a estudar (em semanas antes da prova)
- `tempo_estudo_dia`: Minutos de estudo por dia
- `nota`: Nota obtida no concurso (escala de 0 a 10)

## Metodologia
O projeto implementa dois modelos de regressão linear:

### 1. Regressão Linear Simples (sem intercepto)
Implementação manual do método dos Mínimos Quadrados para resolver a equação:
- **nota = a·inicio_estudo + b·tempo_estudo_dia**

A solução é encontrada através da fórmula:
- **X = (A^T·A)^(-1)·A^T·b**

Onde:
- A é a matriz das variáveis independentes
- b é o vetor das notas (variável dependente)
- X é o vetor de coeficientes estimados

### 2. Regressão Linear Múltipla (com intercepto)
Adição de um termo constante ao modelo:
- **nota = c + a·inicio_estudo + b·tempo_estudo_dia**

Este modelo é implementado tanto manualmente quanto utilizando a biblioteca Statsmodels.

## Implementação e Análise
O notebook contém:

1. **Importação e Análise de Dados**
   - Carregamento dos dados do Excel
   - Verificação de tipos e valores ausentes
   - Visualização inicial dos dados

2. **Manipulação das Matrizes**
   - Criação das matrizes A e b
   - Operações matriciais (transpostas, multiplicações, inversões)

3. **Cálculos do Método dos Mínimos Quadrados**
   - Implementação da fórmula X = (A^T·A)^(-1)·A^T·b
   - Obtenção dos coeficientes estimados

4. **Avaliação dos Modelos**
   - Cálculo das previsões usando os coeficientes
   - Cálculo do erro médio absoluto (MAE)
   - Comparação entre valores reais e previstos

5. **Regressão com Intercepto**
   - Adição de uma coluna de "1's" para o termo constante
   - Recálculo dos coeficientes e avaliação do modelo

6. **Uso de Statsmodels**
   - Implementação do modelo usando uma biblioteca estatística
   - Análise dos resultados e estatísticas do modelo

## Resultados

### Modelo 1: Sem Intercepto
- **nota = 0.1839·inicio_estudo + 0.0414·tempo_estudo_dia**
- Erro médio absoluto: 1.58

### Modelo 2: Com Intercepto
- **nota = 6.4871 + 0.0413·inicio_estudo + 0.00644·tempo_estudo_dia**
- R² do modelo: 0.184
- Estatística F: 2.485 (p-valor: 0.106)

## Conclusões
O modelo com intercepto parece fornecer melhores estimativas, embora o poder explicativo (R²) seja moderado. O p-valor indica que o modelo como um todo tem significância estatística marginal ao nível de 10%.

## Requisitos
- Python 3.x
- Bibliotecas: numpy, pandas, statsmodels, sklearn

## Como Executar
1. Clone este repositório
2. Certifique-se que o arquivo `concurso.xlsx` está na pasta data
3. Execute o notebook Jupyter `notebook.ipynb `

## Autor
Estudo desenvolvido para fins educacionais como demonstração da aplicação do método dos Mínimos Quadrados na resolução de problemas de regressão linear.
