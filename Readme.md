# :bike: Previsão de fluxo de aluguel de bicicletas

[Link do Google Colab](https://colab.research.google.com/drive/1YeAfleLAfa_g_sAKxwH65B_19JrncxL5?usp=sharing)

#### Sobre o projeto

O projeto consiste em uma previsão sobre o fluxo de clientes em um aeroporto fictício, com base nos padrões presentes em uma Série Temporal. Este tipo de planejamento futuro pode ser útil para escolher o momento certo para expansão de um negócio, saber quando a demanda de matéria prima e mão de obra será maior, quando fazer uma promoção ou captação ativa de clientes, e afins.

#### Dataset 

[Material do curso (referência)](https://raw.githubusercontent.com/alura-cursos/deeptime/aula4/bicicletas.csv) 

Quantidade de bicicletas computadas em um determinada data e hora.


## Pré-processamento

* A quantidade de bicicletas foi escalonada. Os métodos que serão experimentados no estudos utilizam Gradiente Descendente, que funcionam melhor com entradas neste formato

* 90% dos dados foram atribuídos ao conjunto de treino, 10% ao de teste.

## Redes Neurais Recorrentes

* Os métodos estudados anteriormente ([previsão de fluxo de clientes](https://colab.research.google.com/drive/1Lna_c5YRh7R7HjZQpWZKgwpneyMkqlbY?usp=sharing)) não conseguem "entender" o caráter sequencial das Séries Temporais, em que cada uma das informações está correlacionada.

* Modelos Recorrentes costumam ser usadas em Séries Temporais e Textos (palavras ou caracteres).

* É utilizada uma janela deslizante de um tamanho especificado. Os dados históricos são coletados no intervalo desta janela e adicionados à entrada da próxima iteração.

* No estudo, as redes recorrentes escolhidas foram LSTM e GRU.

#### **LSTM** (Long Short Term Memory)
  * É usado em séries muito longas, uma rede neural recorrente comum não consegue lidar com padrões muito distantes da iteração corrente (históricos distantes).

#### **GRU** (Gated Recurrent Unit)
  * Tem uma estrutura menor que a LSTM, com menos parâmetros internos. Portanto seu treinamento é mais rápido.
  * Entretando, as LSTMs "lembram" de sequências maiores. 
  
#### **RMSProp** 
  * É um otimizador *adaptativos* que evita a *explosão de gradiente* que pode ser causado por modelos recorrentes, ou seja, evita que cresça muito, se aproxime demais ou fique igual a zero. 
  
### Treinamento e Teste

* Visualmente, as predições parecem acompanhar bem os números padrões do dataset.
* Entretando, ainda ocorrem ou podem ocorrer picos que não são bem previstos pelo modelo.
* A Rede Recorrente com GRU teve uma quantidade de parâmetros 25% menor, aproximadamente.

<div align="center">
  <img src="https://github.com/Tathy/Previsao_fluxo_de_aluguel_de_bicicletas/blob/main/imgs/graph_LSTM.png?raw=true"/>
</div>

<div align="center">
  <img src="https://github.com/Tathy/Previsao_fluxo_de_aluguel_de_bicicletas/blob/main/imgs/graph_GRU.png?raw=true"/>
</div>

### Comparação entre os dois modelos

* Nos dois casos os resultados foram satisfatórios.
* Em uma análise apenas visual, a GRU se sai um pouco melhor que a LSTM, além de ser mais barata computacionalmente.

<div align="center">
  <img src="https://github.com/Tathy/Previsao_fluxo_de_aluguel_de_bicicletas/blob/main/imgs/graph_loss_LSTM_GRU.png?raw=true"/>
</div>

## Referências 

* Estudo desenvolvido acompanhando o curso [Deep Learning: previsão com Keras](https://cursos.alura.com.br/course/deep-learning-previsao-keras), da Alura.
