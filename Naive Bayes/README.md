### Aprendizado de Naive Bayes

A aprendizagem bayeseana consiste no uso de cálculos simples de probabilidade por meio de um conjunto de dados históricos (Imagem 1), gerando uma tabela de probabilidades como resultado do aprendizado (Imagem 2) que viabiliza a previsão de rótulos.

#### Imagem 1 - Base de dados da condição de saúde.

<div align="center"><img title="Imagem 1" src="https://github.com/guilhermyandrade/Estudo-de-Caso-ML-Supervisionado/blob/main/_Imagens/base_condicao_saude.png" ></div>

#### Imagem 2 - Aprendizado por Naive Bayes a partir da base condicao_saude

<div align="center"><img title="Imagem 2" src="https://github.com/guilhermyandrade/Estudo-de-Caso-ML-Supervisionado/blob/main/_Imagens/prob_nbayes_saude.png" ></div>

<hr>
Para rotular novos registros, é necessário aplicar a seguinte equação para cada classe que desejamos prever:


    P( C | x ) = P( C )  *  P( x | C ) / P( x )



Onde:


- P( C ∣ x ) é a probabilidade de pertencer à classe C dado o exemplo x.

- P( x ∣ C ) é a verossimilhança, a probabilidade do exemplo x dado que pertence à classe C.

- P( C ) é a probabilidade geral - a priori - de pertencer à classe C.

- P( x ) são os dados que podem ser observados. Não é usado na prática para a finalidade deste modelo.




<br>

Exemplo de registro:

    Status do peso = Acima
    Alimentação = Desbalanceada
    Pressão sanguínea = Normal
    Colesterol = Normal
    Diabetes = Sim
    Exercício físico = Nao

Classificação do exemplo:

    P(Regular)     = 7/16 * 1/7 * 1/7 * 3/7 * 6/7 * 2/7 * 2/7 => 0.000268
    P(Nao regular) = 9/16 * 5/9 * 7/9 * 2/9 * 2/9 * 6/9 * 7/9 => 0.00622
    
    Total = 0.000268 + 0.00622 => 0.00649

    A probabilidade deste registro para cada classe é o percentual do valor da classe sobre o total. Logo,
    
        P(Regular) = (0.000268 / 0.00649 ) * 100 => 4.13 %
        P(Nao regular) = (0.00622 / 0.00649 ) * 100 => 95.87 %
    
Portanto, de acordo com a tabela de probabilidades apresentada na imagem 2, a condição de saúde para este registro pode ser classificada como "Nao regular".

## Conclusão

Esse método de aprendizado de máquina simples capaz de categorizar dados, sendo usado para processamento de linguagem natural, isto é, classificar textos.

#### Vantagens

- Fácil de interpretar
- Bom para classificação de texto
- Bom desempenho com conjuntos de dados de alta dimensão
- Não exige grande volume de dados para o treinamento

#### Desvantagens

- Encara os atributos como independentes
- Pouco desempenho para relações não-lineares
- Sensível a atributos irrelevantes, exigindo cautela na modelagem de dados
- Dados desbalanceados podem enviesar as previsões
- Incapacidade de lidar com dados temporais ou sequenciais visto que encara os atributos como independentes
- Problemas com dados numéricos contínuos, exigindo a discretização