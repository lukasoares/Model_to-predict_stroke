<h1>Model to Predict Stroke</h1>

Limpeza de dados, análise exploratória, pré-processamento, treinamento e validação de um modelo de classificação com o objetivo de prever AVC. A base de dados esta disponibilizada no <a href='https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset'>Kaggle</a>.

<h2>Objetivo</h2>

Este projeto teve como objetivo realizar uma análise exploratória para investigar a relação da variável dependente "stroke" com as demais variáveis presentes no banco de dados. Com base nessa análise, foi construído um modelo de machine learning de classificação capaz de prever a ocorrência de um AVC com base em informações pré-informadas, como idade, taxa de glicose no sangue e se o paciente é hipertenso, entre outras características e em seguida, avaliar as variáveis que tiveram maior influência na decisão do modelo, ou seja, aquelas que tem maior peso na previsão de ocorrência de AVC.

<h2>Notebook 1 - Limpeza e Análise Exploratória</h2>
Neste notebook, está contida toda a limpeza dos dados, incluindo o preenchimento de valores nulos, bem como a análise exploratória, com foco na variável "stroke" e sua relação ou comportamento em conjunto com as outras variáveis. O objetivo dessa análise é avaliar as diferenças entre pessoas que tiveram AVC e as que não tiveram com a sustentação de testes estatísticos.
<img src ="https://user-images.githubusercontent.com/110298606/226346294-0d7e2418-384f-43c5-a28d-771cfd9cf7fe.png" width = 700px/>

<h2>Notebook 2 - Pré-processamento e Construção do Modelo</h2>
Como parte do pré-processamento, foi realizada a vetorização do banco de dados, bem como o teste de correlação de Pearson e a aplicação do método "SMOTE" para balancear a variável dependente "stroke" por meio da criação de dados sintéticos, a fim de evitar o overfitting em uma das categorias (teve ou não teve AVC).

Para a construção do modelo, foi utilizado o método "nested cross-validation" para separar o conjunto de dados entre treinamento e teste, sendo que este último foi utilizado apenas para a validação dos modelos. Após essa divisão, os hiperparâmetros de cada modelo foram otimizados e, em seguida, cada modelo foi avaliado utilizando a métrica "F1 Score" e uma matriz de confusão. Por fim, após a seleção do melhor modelo, foram realizadas análises para identificar as variáveis que tiveram maior peso na classificação do modelo.

<h2>Conclusão</h2>

O modelo SVC (Support Vector Classification) foi o que obteve a maior taxa de acerto na previsão de pessoas que sofreram AVC (86%), com um F1 Score global de 80%. Entretanto, é necessário destacar que a base de dados original apresenta um desequilíbrio considerável, o que pode ter afetado o desempenho do modelo. Assim, o aumento da amostra de pessoas que sofreram AVC poderia contribuir para aprimorar a performance do modelo.

Ao examinar os dois melhores modelos, observou-se que ambos concederam grande importância às variáveis "age", "hypertension", "avg_glucose_level" e "heart_disease". Além disso, surpreendentemente, a variável "work_type_Govt_job" também exerceu uma influência significativa na probabilidade de ocorrência de AVC.

Por outro lado, é relevante destacar a pequena influência da variável "bmi" na probabilidade de uma pessoa sofrer AVC. Tal constatação sugere que o índice de massa corporal pode não ser um fator determinante para prever o risco de AVC em comparação com outras variáveis, como idade, hipertensão, nível médio de glicose e doença cardíaca.


