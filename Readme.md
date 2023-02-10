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

* Recebe uma matriz tridimensional, em que a terceira dimensão define o número de atributos por passo no tempo.


## Referências 

* Estudo desenvolvido acompanhando o curso [Deep Learning: previsão com Keras](https://cursos.alura.com.br/course/deep-learning-previsao-keras), da Alura.

:seedling:
