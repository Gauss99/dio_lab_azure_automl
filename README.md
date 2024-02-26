<div class="image">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Microsoft_Azure.svg/640px-Microsoft_Azure.svg.png" width="80" height="80">
</div>

## Descrição do Projeto 📚

Este projeto utiliza a plataforma AutoML do Azure para realizar uma regressão em dados de aluguel de bicicletas.

## Conjunto de Dados 💾

O conjunto de dados utilizado neste projeto é publico e provido pela própria Microsoft. O conjunto de dados esta na forma csv e pode ser visto em sua forma raw pelo [link_dados](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/main/data/ml/daily-bike-share.csv).

Informações gerais sobre os dados:
* **Número de linhas:** 731;
* **Número de colunas:** 13;
* **Nome das colunas:** ['day', 'mnth', 'year', 'season', 'holiday', 'weekday', 'workingday', 'weathersit', 'temp', 'atemp', 'hum', 'windspeed', 'rentals'];
* **Informações**:

| #  | Column     |   Non-Null Count | Dtype   |
|--- |---         |---               |---      |
| 0  | day        | 731 non-null     | int64   |
| 1  | mnth       | 731 non-null     | int64   |
| 2  | year       | 731 non-null     | int64   |
| 3  | season     | 731 non-null     | int64   |
| 4  | holiday    | 731 non-null     | int64   |
| 5  | weekday    | 731 non-null     | int64   |
| 6  | workingday | 731 non-null     | int64   |
| 7  | weathersit | 731 non-null     | int64   |
| 8  | temp       | 731 non-null     | float64 |
| 9  | atemp      | 731 non-null     | float64 |
| 10 | hum        | 731 non-null     | float64 |
| 11 | windspeed  | 731 non-null     | float64 |
| 12 | rentals    | 731 non-null     | int64   |

## Metodologia 📘

O projeto segue as seguintes etapas:

1. **Preparação dos Dados**:
Esta etapa não foi necessária para este projeto pois os dados fornecidos já foram previamente preparados e limpos.

2. **Configuração do AutoML**: A configuração do ambiente foi divida nas seguintes etapas.

    * Primeiramente, foi necessário criar uma "*resource group*", nesse caso uma "*Azure Machine Learning*".

    * Então indicamos o nome da *resource group*, que para esse projeto foi escolhido como "LAB_AI_900_DIO".

    * Logo após, define-se os detalhes da *workspace* como nome, região, conta de armazenamento, etc.

    * Para o *Networking*, manteve-se a isolação como pública, já que é um laboratório mais simples e sem dados confidenciais.

    * As abas de *Encryption*, *Identity* e *Tags* foram mantidas com seus valores padrões.

    * Por fim, na aba *Review + Create*, passada a validação, foi criado o ambiente e foi necessário esperar alguns minutos para que o *deployment* fosse finalizado.

  Após a criação do ambiente, somos redirecionados para o Estúdio do Azure Machine Learning, aonde é possível finalmente utilizar a ferramenta de ML Automatizado.

  A partir disso, foi criado um novo trabalho de ML automatizado dando um nome de trabalho como "mslearn-bike-automl", nome de experimento como "mslearn-bike-rental", e outras configurações básicas como tipo de tarefa.

  Em seguida foi necessário configurar a tarefa do AutoML, como a coluna que será utilizada como *target*, sendo essa coluna "rentals", definições dos tipos de algoritmos de regressão a serem utilizados (LightGBM e RandomForestRegressor para esse modelo) configuração de limites de tempo e outras variáveis do modelo, seleção de tipo de computação a ser implementada, e depois foi enviado o trabalho de treinamento.

  Após isso, o trabalho entrou em execução e demorou aproximadamente 10 minutos para ser finalizado, bastando agora fazer a avaliação do modelo.
  
3. **Avaliação do Modelo**: Os modelos gerados podem ser avaliados de duas formas:

* Passando os valores na própria área de teste do Estudio de *Machine Learning* do Azure, na aba pontos de extremidade.

* Consumindo esse ponto de extremidade utilizando o link provido para API Rest.

## Resultados

Os resultados do projeto incluem o desempenho do modelo selecionado e insights sobre a importância das características, junto a adição de diversas métricas como *r2score*, *sperman correlation*, *mean absolute error*, *mean squared error*, além de plots como o *ground truth (valor verdadeiro vs valor predito)* e plot de resíduos, nos entregando uma excelente ferramenta para tomada de decisão.

## Repositório do Projeto

[![Repo Card](https://github-readme-stats.vercel.app/api/pin/?username=Gauss99&repo=dio_lab_azure_automl&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)](https://github.com/Gauss99/dio_lab_azure_automl)

## Conclusão

Com esse projeto, foi possível obter um grande aprendizado sobre a plataforma de Machine Learning do Azure. Foi obtido o primeiro contato com o AutoML e ainda foram revistos conceitos de git e seus comandos através da criação de um repositório no GitHub para o projeto.

## Referências

Site do AutoML: [Microsoft Azure](https://azure.microsoft.com/pt-br/products/machine-learning/AutoML/#overview)

Introdução ao AutoML: [Introdução](https://learn.microsoft.com/pt-br/azure/machine-learning/concept-automated-ml?view=azureml-api-2)

Machine Learning para cientistas de dados: [Data Science Azure](https://azure.microsoft.com/pt-br/solutions/ai/data-scientist-resources/)
