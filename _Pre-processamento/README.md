# Pre-processamento dos dados

O processo de tratamento dos dados para o aprendizado de máquina é fundamental para o resultado correto de um modelo. É nessa etapa onde podemos verificar as condições da base de dados, entender o que cada atributo representa, identificando possíveis falhas e ajustando-as para fazer o treinamento.

### Explicação das bases de dados

- **Base condicao_saude**: Pequeno conjunto de dados para facilitar a compreensão das equações envolvidas nos aprendizados de máquina. Deseja-se prever a condição de saúde de um paciente ("Regular" ou "Nao regular").

- **Base census**: O objetivo para este conjunto de dados é prever se a renda anual de uma pessoa é maior que 50.000 (>50K) ou menor que 50.000 (<=50k) com base em dados pessoais.

- **Base credit_data**: Contém a renda, idade e empréstimo como valores previsores, onde deseja-se prever se o empréstimo será pago ou não.


### Codificando valores de texto com LabelEncoder

O aprendizado de máquina ocorre por meio de operações matemáticas entre matrizes. Portanto, os valores em formato de texto devem se tornar numéricos.

Existem ferramentas capazes de codificar strings e, entre elas, temos o LabelEncoder, que designa um número distinto a cada uma das strings em uma coluna do conjunto de dados. Por exemplo, valores como _"carro" e "avião" poderiam ser substituídos por 10 e 20, respectivamente._ Entretanto, existe grande diferença entre esses valores - _em outras palavras, diferença de peso_ -, o que pode levar o algoritmo a encarar incorretamente o maior valor como mais importante.

### Codificando valores de texto com OneHotEncoder

Por conta disso, o __OneHotEncoder__ _codifica os valores gerando novas colunas de acordo com a quantidade de valores diferentes na coluna._ Portanto, se tivermos 3 valores distintos em uma coluna, três colunas serão geradas e cada uma receberá um valor entre 1 e 0, gerando um código de identificação único para cada valor. Dessa forma, não haverá diferença de pesos entre valores e os resultados das operações matemáticas entre matrizes não será afetada.

### Escalonamento dos valores com StandardScale

Tendo em vista que valores maiores têm mais impacto nos resultados das equações aplicadas ao conjunto de dados, é preciso deixar os números na mesma escala e uma das ferramentas disponíveis para isso é o *sklearn.preprocessing.StandardScale*.

Exemplo: existe grande diferença de escala entre os valores 25 e 25.000 (24.975 de diferença). A partir do momento em que a equação de padronização for usada, esses valores ficarão na mesma escala (aproximadamente entre 1 e -1), tornando-os adequados para o aprendizado de máquina.