# Aprendizado por regras

Este aprendizado de máquina é usado para previsão de rótulos, sendo constituído por um conjunto de regras parecidas com a estrutura de uma [árvore de decisão](/Árvore%20de%20decisão) onde registros são classificados por meio de um conjunto de regras.

#### Imagem 1 - Base de dados da condição de saúde.

<div align="center"><img title="Imagem 1" src="https://github.com/guilhermyandrade/Estudo-de-Caso-ML-Supervisionado/blob/main/_Imagens/base_condicao_saude.png" ></div>

#### Imagem 2 - Aprendizado por Regras a partir da base condicao_saude

<div align="center"><img title="Imagem 2" src="https://github.com/guilhermyandrade/Estudo-de-Caso-ML-Supervisionado/blob/main/_Imagens/aprendizado_abrangencia.png" ></div>


<hr>

A definição das regras é obtida pelo cálculo da abrangência de um valor em relação às classes a fim de gerar uma regra para cada classe, que é estruturada da seguinte forma:

        SE x ENTÃO y
        
Onde:

- *x* é o valor de um atributo
- *y* é o rótulo previsto (classe)

Entretanto, o treinamento pode gerar regras muito específicas, gerando o overfitting. Nesse caso, é possível aplicar o conceito de "poda" no modelo, retirando as regras excessivamente específicas.

## Conclusão

Modelos de aprendizado por regras não são tão populares pelo fato de outros algoritmos apresentarem desempenho superior na grande parte das vezes. 

#### Vantagens

- Fácil de interpretar e implementar
- Bom desempenho em situações que exigem regras específicas

#### Desvantagens

- Não consegue identificar relações complexas ou padrões suaves nos dados
- Sensíveis a outliers (valores fora da média)
- Ineficiência em grande volume de dados. Treinamento demorado.
- Flexibilidade reduzida para relações não-lineares
- Overfitting em conjuntos de dados pequenos