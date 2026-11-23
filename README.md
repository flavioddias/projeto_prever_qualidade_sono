# Classificação da qualidade do sono

Estudo de Machine Learning com **10 mil registros sintéticos**, voltado à construção de pipelines e à análise de vazamento de dados. A pergunta central é como o desempenho muda quando uma variável diretamente associada à formação do alvo é retirada.

[Explore o notebook](pipeline_qualidade_sono.ipynb)

## Abordagem

- Análise exploratória e preparação de variáveis numéricas e categóricas.
- Comparação de cenários com e sem a variável de horas de sono.
- `ColumnTransformer` e `Pipeline` com escalonamento e codificação.
- Regressão Logística, Random Forest e HistGradientBoosting.
- Divisão estratificada 80/20, validação cruzada com cinco partições e `GridSearchCV` com F1 macro.
- Relatório por classe e exportação do modelo com Joblib.

## Resultados registrados

No cenário sem a variável identificada como vazamento, o Random Forest ajustado apresenta **acurácia de 80,45% e F1 macro de 0,7694** na partição de teste. Esses valores são saídas salvas no notebook, sem nova execução nesta revisão.

O desempenho varia entre classes: a classe *Excellent* tem F1 próximo de 0,25. A acurácia isolada, portanto, não resume a qualidade da classificação.

## Como explorar e executar

1. Abra o notebook no Jupyter ou Google Colab.
2. Disponibilize o arquivo `synthetic_coffee_health_10000(in).csv`, que **não está incluído neste repositório**.
3. Ajuste o caminho de leitura. Fora do Colab, adapte também a montagem do Google Drive.
4. Instale as bibliotecas e execute as células em sequência:

```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn joblib jupyter
```

O arquivo `modelo_sleep_quality.joblib` é gerado pela execução; não acompanha o repositório.

## Limitações e próximos passos

Os dados são sintéticos e os resultados têm finalidade educacional, sem validação clínica. A escolha final compara o F1 dos modelos na partição de teste; uma avaliação futura deve reservar outra amostra intocada para estimar a generalização após essa escolha. Próximos passos: disponibilizar a origem dos dados e o ambiente reproduzível, investigar a classe com menor desempenho e validar em dados independentes.

**Competências demonstradas:** análise exploratória, pipelines, classificação multiclasse, validação e interpretação de métricas.
