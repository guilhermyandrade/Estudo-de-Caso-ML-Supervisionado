### Random Forest (Floresta Randômica)

Este modelo de aprendizado de máquina utiliza mais de uma [árvore de decisão](/Árvore%20de%20decisão) para fazer previsões. A previsão é feita com base nos votos da maioria quando se trata de classificação e com uso da média quando se trata de regressão.

O treinamento para cada árvore de decisão é variado. Cada uma recebe uma quantidade x de atributos previsores definida pela raiz quadrada do total de atributos previsores na base de dados, cálculo que pode ser representado da seguinte forma:

        √x

Onde:

- *x* é a quantidade total de atributos previsores na base de dados

<br>

Exemplo: Se tivermos 4 atributos previsores, é possível gerar duas árvores que receberão uma combinação diferente de dois atributos para o treinamento.

## Conclusão

O aprendizado Random Forest é o aprimoramento do aprendizado por árvore de decisão.

#### Vantagens

- Trabalha bem com dados desbalanceados
- Boa performance com dados de alta dimensão
- Seleção de características automática

#### Desvantagens

- Sensibilidade a outliers
- Se as características mais importantes forem muito parecidas, as árvores podem acabar sendo muito semelhantes, aumentando as chances de gerar overfitting