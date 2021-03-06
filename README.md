﻿# Camada Física
Por: Isabella Oliveira e Vitória Camilo (Insper)

# Projeto 5 - DTMF

## Geração dos tons
Os tons são gerados a partir da soma de duas ondas senoides. A fórmula utilizada foi *sen(wt)* para gerar a onda, onde *w = 2πf*. O arquivo onde os tons são gerados, reproduzidos, e plotados pela primeira vez é o *encoderDTMF.py*.


## Frequências que compõem cada tom 
|             |1209 Hz  |1336 Hz  |1477 Hz  |
|:-----------:|---------|---------|---------|
|**697 Hz**   |1        |2        |3        |
|**770 Hz**   |4        |5        |6        |
|**852 Hz**   |7        |8        |9        |
|**941 Hz**   |*        |0        |#        |


## Tons Gerados e Captados

Nos gráficos abaixo relaciona-se o sinal de tom no decorrer do tempo. Na esquerda estão as soma dos senos das duas frequências utilizadas, e na direita o gráfico do som que foi gravado de um computador que escutava o outro. As visíveis disparidades entre os gráficos correspondem as interferencias presentes em meio a gravação. O arquivo com o código que escuta, grava e plota um novo gráfico é o *decoderDTMF.py*.

| Tom | Primeira plotagem                  |Ondas Captadas               |
|:-----:|-------------------------|----------------------|
|1      | ![1](img/1p.png)        |![1](img/1.png)       |
|2      | ![2](img/2p.png)        |![2](img/2.png)       |
|3      | ![3](img/3p.png)        |![3](img/3.png)       |
|4      | ![4](img/4p.png)        |![4](img/4.png)       |
|5      | ![5](img/5p.png)        |![5](img/5.png)       |
|6      | ![6](img/6p.png)        |![6](img/6.png)       |
|7      | ![7](img/7p.png)        |![7](img/7.png)       |
|8      | ![8](img/8p.png)        |![8](img/8.png)       |
|9      | ![9](img/9p.png)        |![9](img/9.png)       | 
|0      | ![0](img/0p.png)        |![0](img/0.png)       |
|*      | ![*](img/astp.png)  |![*](img/ast.png)    |
|#      | ![#](img/hashp.png)     |![#](img/hash.png) |

# Projeto 6 - DTMF

## Sinais Enviados e Recebidos

| Tom   | Sinal Enviado       |Sinal Recebido         |
|:-----:|-------------------------|----------------------|
|1      | ![1](img/F1.png)        |![1](img/T1.png)      |
|2      | ![2](img/F2.png)        |![2](img/T2.png)      |
|3      | ![3](img/F3.png)        |![3](img/T3.png)      |
|4      | ![4](img/F4.png)        |![4](img/T4.png)      |
|5      | ![5](img/F5.png)        |![5](img/T5.png)      |
|6      | ![6](img/F6.png)        |![6](img/T6.png)      |
|7      | ![7](img/F7.png)        |![7](img/T7.png)      |
|8      | ![8](img/F8.png)        |![8](img/T8.png)      |
|9      | ![9](img/F9.png)        |![9](img/T9.png)      | 
|0      | ![0](img/F0.png)        |![0](img/t0.png)      |
|*      | ![*](img/Fast.png)  |![*](img/Tast.png)   |
|#      | ![#](img/Fhash.png)     |![#](img/Thash.png)|


## Frequências enviadas e recebidas
As frequências enviadas são recebidas com pouca discrepância, pois há pouco ruído, mas foi necessário o uso do software Audacity, pois a função peakutils muitas vezes não reconhecia os picos corretamente. O nosso código está funcionando corretamente para os áudios 0, 1, 4, 5, 7, 8, #. Utilizamos a leitura de um arquivo de áudio ao invés de captar o áudio em tempo real pois os microfones dos computadores apresentaram muitos problemas.

Tom 1: 

Frequências Enviadas: 697, 1209 

Frequências Recebidas: 697, 1210 

Tom 2: 

Frequências Enviadas: 697, 1336

Frequências Recebidas: 697, 1335

Tom 3: 

Frequências Enviadas: 697, 1477

Frequências Recebidas: 697, 1477

Tom 4: 

Frequências Enviadas: 770, 1209 

Frequências Recebidas: 769, 1211 

Tom 5: 

Frequências Enviadas: 770, 1336

Frequências Recebidas: 770, 1337 

Tom 6: 

Frequências Enviadas: 770, 1447

Frequências Recebidas: 769, 1351 

Tom 7: 

Frequências Enviadas: 852, 1209 

Frequências Recebidas: 852, 1208

Tom 8: 

Frequências Enviadas: 852, 1336 

Frequências Recebidas: 852, 1337 

Tom 9: 

Frequências Enviadas: 852, 1477 

Frequências Recebidas: 853, 1477 

Tom 0: 

Frequências Enviadas: 941, 1336 

Frequências Recebidas: 943, 1336 

Tom *: 

Frequências Enviadas: 941, 1209 

Frequências Recebidas: 941, 1277 

Tom #: 

Frequências Enviadas: 941, 1477 

Frequências Recebidas: 941, 1477

## Tempos utilizados
Os audios transmitidos tem duração de 1 segundo, o mesmo setado na geração dos tons, e os gráficos são gerados para cada 1 segundo recebido, captando, assim, cada audio de tom por completo.

# Projeto 7 - Modulação AM



## Descrever a modulação e a demodulação

Na modulação, o sinal é multiplicado por portadoras criadas, e filtrado por um Passa-Baixa com 3400 Hz de frequencia de corte, o maximo alcançado pela voz humana
.
Na demodulação, multiplica-se o sinal recebido pela portadora novamente, obtendo os sinais com diversas repetições, e então aplica-se o mesmo filtro Passa-Baixa para 
selecionar apenas um dos sinais entre os diversos repetidos.

## Descrever as frequências das portadoras utilizadas e as bandas ocupadas


Utilizamos 7000 Hz e 14000 Hz para as portadoras, pois como o corte do filtro foi de 3400 Hz (ocupando 6800 Hz de banda após modular,
ter os centros em 7000 Hz e 14000 Hz permite que não haja interferencia entre os sinais, pois um vai ocupar de 3600 Hz até 10400 Hz e o outro de 10600 Hz a 17400 Hz.



## Transmissor
Fourier dos sinais modulados

![transmissor](img/transmissor.png)

## Receptor
Mensagens demoduladas no tempo

![receptor](img/receptor.png)
![receptor2](img/receptor2.png)


## Relação entre áudio transmitido e recebido

As diferenças entre o som transmitido e o que foi recebido são bem discretas, os demodulados estão um pouco mais abafados, mas há pouco ruído e é possível escutar bem a mensagem.
