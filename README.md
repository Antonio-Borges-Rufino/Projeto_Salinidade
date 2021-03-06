![Pipeline dos dados](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/pipeline.jpg)
* [Os dados em situ estão disponiveis aqui](http://www.coriolis.eu.org/Data-Products/Data-Delivery/Data-selection)
* [Os dados de satélite estão disponiveis aqui](https://podaac.jpl.nasa.gov/dataset/MUR-JPL-L4-GLOB-v4.1)
>A data de seleção foi de 2003 a 2020 
>>Os tipos de coletas foram Argos, Tsg e Bottles

## 1. Preparando os dados do tipo argo
  1. [Lendo os dados](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/1.%20Preparando%20dados%20em%20Situ/Passo%201.%20(Argo).ipynb)
  2. [Organizando os dados](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/1.%20Preparando%20dados%20em%20Situ/Passo%202.%20(Argo).ipynb)
## 2. Lendo os dados do tipo Bottle e tsg
  1. [Lendo os dados](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/1.%20Preparando%20dados%20em%20Situ/Passo%201.%20(Bottles_TSG).ipynb)
## 3. Organizando os dados 
  1. [Organizando os dados do tipo Bottle](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/1.%20Preparando%20dados%20em%20Situ/Passo%202.%20(Bottles).ipynb)
  2. [Organizando os dados do tipo tsg](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/1.%20Preparando%20dados%20em%20Situ/Passo%202.%20(tsg).ipynb)
## 4. Separando os dados em situ em arquivos Ano-Mes
  1. [Codigo](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/Separacao_ano_mes.ipynb)
## 5. Transformação dos dados (Nesse processo vou deixar o dataset pronto para poder extrair imagens de satélite)
  1. [Codigo](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/Tranformacao.ipynb)
## 6. Extração dos dados de satélite
  1. [Codigo](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/Extra%C3%A7%C3%A3o.ipynb)
## 7. Junção dos dados de satélite em df anuais
  1. [Codigo](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/juncao.ipynb)
## 8. Criação da base de batimetria
  1. [Codigo](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/rasterBatimetria.ipynb)
## 9. Junção e criação do dataset final, é dele que vai ser tirado os dados de validação e treinamento
  1. [Codigo](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/dataSetFinal.ipynb) 
## 10. Divisão do dataset em dados de treinamento e dados de teste
  1. [Codigo](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/divisaoNormalizacao.ipynb)
  2. [Dataset de teste](https://drive.google.com/file/d/1-9WllvpwlAM9IOit5eoBvNk1G7pXqZf-/view?usp=sharing)
  3. [Dataset de treino](https://drive.google.com/file/d/1-3ZdBaUFueaxyLsxLu_F4m3AfFkQfuYu/view?usp=sharing)
## 11. Tunning de parametros de rede densa
  1. O tunning de parametros foi realizado com a seguinte distribuição
  2. ![Parametros do Tunning](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/tnn.jpg)
  3. O resultado para o tunning foi a rede densa de 2 camadas com 30 neuronios em cada camada, taxa de aprendizagem de 0.001 com otimizador Adan e 39 epocas para um micro batch de 120
  4. [Codigo](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/tunningDenseR.ipynb)
## 12. Tunning de parametros de redes LSTM E GRU
  1. O tunning de parametros foi realizado com a seguinte distribuição
  2. ![Parametros do Tunning](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/lstm-gru.jpg)
  3. Resultados:
      
      LSTM: rede com 30 neuronios, taxa de aprendizagem de 0.007 e 85 epocas
     
      GRU: rede com 85 neuronios, taxa de aprendizagem de 0.001 e 99 epocas
  5. [Codigo - LSTM](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/tunningLSTM.ipynb)
  6. [Codigo - GRU](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/tunningGRU.ipynb)
## 13. Tunning de parametros de redes Bi-LSTM E Bi-GRU
  1. O tunning de parametros foi realizado com a seguinte distribuição
  2. ![Parametros do Tunning](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/lstm-gru.jpg)
  3. Resultados:
      
      Bi-LSTM: rede com 60 neuronios, taxa de aprendizagem de 0.005 e 98 epocas
     
      Bi-GRU: rede com 75 neuronios, taxa de aprendizagem de 0.001 e 100 epocas
  5. [Codigo - Bi-LSTM](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/TunningBi_LSTM.ipynb)
  6. [Codigo - Bi-GRU](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/tunningBi_Gru.ipynb)
## 14. Resultado final para cada rede testada
1. ![Resultado](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/result.jpg)
2. [Codigo](https://github.com/Antonio-Borges-Rufino/Projeto_Salinidade/blob/main/Nova%20pasta/Compar.ipynb)
