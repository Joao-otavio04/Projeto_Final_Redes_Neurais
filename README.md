# Previsão de rendimento agrícola por redes neurais tipo MLP
*Grupo:* Emelyn Alves, João O. de A. Nascimento, Kayllany L. da S. Oliveira
<br>
*Instituição:* Ilum - Escola de Ciência 
<br>
*Professor:* Daniel R. Cassar
<br>
*Disciplina:* Redes Neurais e Algoritmos Genéticos

## Apresentação 
Como primeiro projeto final da disciplina propusemos a utilização de redes neurais (RN) tipo MLP (*Multilayer Perceptron*) para previsão do maior rendimento agrícola, a partir da análise de regressão linear com dados sintéticos.

## Importância
A utilização de um modelo que possa prever o rendimento agrícola a partir das condições do plantio pode ser uma ferramenta para implementação de uma agricultura mais sustentável e eficiente.  

## Dataset
O conjunto de dados escolhido [Synthetic Agricultural Yield Prediction Dataset](https://www.kaggle.com/datasets/blueloki/synthetic-agricultural-yield-prediction-dataset/data) foi retirado so site [Kaggle](https://www.kaggle.com/) e apresenta as seguintes características: 

1. Dados sintéticos, ou seja, não reais.
2. Conjunto com split treino-teste aplicado:
   * `agricultural_yield_train.csv` (treino; 16000 linhas x 7 solunas) - arquivo `.csv` com dados de treino. 
   * `agricultural_yield_test.csv`(teste; 4000 linhas x 7 colunas). - arquivo `.csv` com dados de teste. 
3. 7 atributos:
   * `Soil_Quality` - Índice de qualidade do solo, variando de 50 a 100.
   * `Seed_Variety` -  Indicador binário de variedade de semente, onde 1 representa uma variedade de alto rendimento.
   * `Fertilizer_Amount_kg_per_hectare`- A quantidade de fertilizante utilizada em quilogramas por hectare.
   * `Sunny_Days` - O número de dias ensolarados durante a estação de crescimento.
   * `Precipitação_mm` - precipitação total recebida durante a estação de crescimento em milímetros.
   * `Irrigation_Schedule` - O número de irrigações durante a estação de crescimento.
   * `Yield_kg_per_hectare` - O rendimento agrícola em quilogramas por hectare, servindo como variável alvo para previsão. [2] (texto traduzido pelo Google Translator)
4. Target:`Yield_kg_per_hectare` - Rendimento agrícola (kg/hec)

### Como obter o dataset? 
O download do dataset pode ser feito pelo:
1. link: [Synthetic Agricultural Yield Prediction Dataset](https://www.kaggle.com/datasets/blueloki/synthetic-agricultural-yield-prediction-dataset/data)
2. repositório; para isso basta selecionar os arquivos `.csv` do main branch e fazer o download.
***Não se esqueça de baixar os dois arquivos `.csv` disponíveis.***

## Repositório
* `Projeto Final Redes Neurais.ipynb` - notebook do JupyterLab apresenta a rede neural com todos os processo de otimização, treino e teste, além de discussões a cerca dos resultados gráficos e numéricos obtidos. 
* `agricultural_yield_test.csv` - conjunto de dados de teste sintéticos 
* `agricultural_yield_train.csv` - conjunto de dados de treino sintéticos

### Como utilizar? 
1. Obtenha os arquivos `.csv` 
2. Baixe o arquivo `.ipynb`
Todos se encontram no main branch do repositório.
3. Mantenha todos os arquivos no mesmo ambiente.
4. Execute o cógido no JupyterLab.

## Requisitos 
* Python instalado
* JupyterLab habilitado
* Obter arquivos `.csv` e `.ipynb` do repositório 
* Python configurado para importar bibliotecas, módulos, etc;

## Bibliotecas/Módulos e suas funções (no projeto)
* `pandas` - importar e tratar dados
* `random` - aleatorizar números de neurônios nas camadas da MLP teste
* `matplotlib` - plotar gráficos (curvas de aprendizado) e matriz de correlação
* `seaborn` - fazer mapa de calor da matriz de correlação
* `torch` - conversão de dados em tensores 
* `pytorch lightning` - criar e treinar a rede neural
* `sklearn` - calcular RMSE, normalização e realizar split de dados
* `optuna` - otimização

## Brevíssimas considerações sobre rendimento agrícola
A agricultura é uma atividade econômica do setor primário de alta relevância mundial, sobretudo para países produtores e exportadores mundiais de alimentos, como o Brasil. Dentre os desafios enfrentados pela agricultura, está o rendimento agrícola. Este pode ser definido como: "uma medida da quantidade de uma cultura cultivada [...] por unidade de área de terra."  e sua unidade é: [kg/hec] (quilos por hectare de terra). [1][3]

Desde sempre busca-se aumentar cada vez mais o rendimento agrícola. E atualmente tem ganhado mais importância, tanto econômica quanto ambiental. Já que uma maior produção em menores espaços é eficiente e, teoricamente, preserva recursos naturais. [3]

## Conclusão

Após treino e teste podemos perceber que houve uma melhoria significativa no RMSE do primeiro modelo de teste para o real, que foi otimizado. O RMSE era de 199 kg/hec e diminuiu para 76 kg/hec, uma taxa de dimuição de erro de aproximadamente 62%. 
Dessa forma, com base nos gráficos de curva de aprendizado e através de análises de porcentagem, o modelo pode prever redimentos de plantação com uma taxa de erro baixa. 

Embora a rede tenha sido treinada com dados sintéticos, devido à diferença relativamente grande entre os valores de rendimento, pode-se considerar uma boa rede. Vale ressaltar que a rede poderia ser treinada com dados reais, sendo possível melhorar ainda mais o RMSE da rede.


## Referências: 
[1] [Rendimento agrícola](https://pt.wikipedia.org/wiki/Rendimento_agr%C3%ADcola#:~:text=Na%20agricultura%2C%20o%20rendimento%20%C3%A9,maneira%20de%20calcular%20os%20rendimentos.)

[2] [Conjunto de dados sintéticos de previsão de rendimento agrícola - "Synthetic Agricultural Yield Prediction Dataset"](https://www.kaggle.com/datasets/blueloki/synthetic-agricultural-yield-prediction-dataset/data)

[3] [Trajetoria da agricultura Brasileira](https://www.embrapa.br/visao/trajetoria-da-agricultura-brasileira)

[4] LOOMIS, C. Using Optuna to Optimize PyTorch Lightning Hyperparameters. Disponível em: <https://medium.com/optuna/using-optuna-to-optimize-pytorch-lightning-hyperparameters-d9e04a481585>.

[5] optuna-examples/pytorch/pytorch_lightning_simple.py at main · optuna/optuna-examples. Disponível em: <https://github.com/optuna/optuna-examples/blob/main/pytorch/pytorch_lightning_simple.py#L161>.

[6] optuna.create_study — Optuna 3.6.1 documentation. Disponível em: <https://optuna.readthedocs.io/en/stable/reference/generated/optuna.create_study.html>.

[7] optuna.trial.Trial — Optuna 3.6.1 documentation. Disponível em: <https://optuna.readthedocs.io/en/stable/reference/generated/optuna.trial.Trial.html>.
