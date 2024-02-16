### Regressão Logística

A regressão logística é um método de aprendizado de máquina de classificação que tenta encontrar a linha que mais se encaixe nos dados, retornando a probabilidade de novas instâncias pertencerem a uma classe.

#### Imagem 1 - Base de dados da condição de saúde.

<div align="center"><img title="Imagem 1" src="https://github.com/guilhermyandrade/Estudo-de-Caso-ML-Supervisionado/blob/main/_Imagens/base_condicao_saude.png" ></div>

#### Imagem 2 - Aprendizado por Regressão Logística a partir da base condicao_saude

<div align="center"><img title="Imagem 2" src="https://github.com/guilhermyandrade/Estudo-de-Caso-ML-Supervisionado/blob/main/_Imagens/aprendizado_regressao_log.png" ></div>

<hr>

Resumidamente, os cálculos nesse método visam encontrar o valor dos parâmetros *b0, b1, b2, bn...* na **equação da reta**. O resultado dessa equação é usado para elevar o [número de euler](https://pt.wikipedia.org/wiki/E_(constante_matem%C3%A1tica)) na equação *sigmoide*.

A linha é calculada várias vezes para encontrar a linha que mais se adapta à base de dados de treinamento, assim como demonstrado na imagem 2.

#### Equação da reta

        y = b0 + b1 * x

Onde:

- *y* é o que está sendo previsto
- *b* é o parâmetro calculado pela técnica [descida do grandiente](https://en.wikipedia.org/wiki/Gradient_descent). *b0* e *b1* mostram o ângulo da linha e onde o eixo Y foi cortado, respectivamente.
- *x* representa o valor do atributo que está sendo usado para fazer a previsão.


#### Equação sigmoide

A equação da reta gera a linha da regressão. Entretanto, a linha reta acaba deixando registros de fora da previsão, problema que é corrigido pela função sigmoide, fazendo com que a linha da regressão possa abranger todos os registros da base de dados de treinamento, assemelhando-se ao formato de um "S".

        p = 1 / (1 + e ** -y)

Onde:

- *y* é o resultado da equação da reta, ou seja, o que está sendo previsto
- *e* representa o [número de euler](https://pt.wikipedia.org/wiki/E_(constante_matem%C3%A1tica))

<br>

## Conclusão

Existem outras equações envolvidas em regressão logística. Este foi um breve resumo sobre algumas de suas equações.

#### Vantagens

- Recomendado para classificações binárias
- Atua como classificador, mas também retorna a probabilidade de uma instância pertencer a uma classe 

#### Desvantagens

- Suscetível a overfitting quando treinado com datasets de alta dimensionalidade
- Problemas com valores com muito mais relevância que os demais
- Requer maior cuidado com o preprocessamento