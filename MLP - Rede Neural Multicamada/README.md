## Rede Neural Artificial Multicamada - MLP

Uma rede neural consiste em um conjunto de neurônios que se comunicam por meio de impulsos elétricos. As conexões entre eles são conhecidas como sinapses, que se tornam mais fortalecidas na medida em que uma memória - seja de ações ou eventos - é ativada, o que facilita a comunicação entre os neurônios que permitem o acesso àquela memória. Da mesma forma, uma rede neural artificial aprende com repetições e fortalece suas sinapses. Contudo, suas unidades de processamento, também chamadas de neurônios, se comunicam através de equações matemáticas que determinam os pesos de cada uma de suas conexões.

Um neurônio artificial segue um modelo proposto em 1950, conhecido como [perceptron](https://en.wikipedia.org/wiki/Perceptron). Os processos envolvidos no treinamento de uma rede neural não são necessariamente complexos. Apesar disso, a iteração de bases de dados, bem como a quantidade de cálculos que devem ser realizados a cada neurônio e suas conexões exige grandes capacidades de processamento computacional, motivo pelo qual redes neurais não se tornaram populares até os últimos anos.

A rede neural multicamada é baseada em camadas de percetrons que se relacionam entre si, processando informações e otimizando o aprendizado a cada iteração sobre um conjunto de dados.

<hr>


## Termos Comuns

Existem diversos termos e expressões importantes quando se trata de redes neurais. São eles:

- **Época (Epoch)**: Cada vez que o modelo verifica todos os registros da base de dados, temos o que é conhecido como época - representa quantas vezes a base de dados foi percorrida de ponta a ponta pelo modelo.
- **Lotes (Batch)**: Um conjunto de dados é dividido em lotes. Cada lote pode ser chamado de instância ou registro do conjunto de dados, que são repetidamente verificados por um modelo durante seu treinamento. Batch Size representa a quantidade total de registros.
- **Peso (Weight)**: Pesos determinam a importância de uma relação entre neurônios. Quanto mais importante uma relação é - ou seja, quanto maior o peso dessa relação -, mais ela influencia a saída de um modelo.
- **Camada (Layer)**: Uma camada se refere a um conjunto de neurônios que processam informações para uma previsão. Se tivermos apenas uma camada de entrada e outra de saída, é correto afirmar que essa rede neural tem duas camadas.
- **Camada Oculta (Hidden Layer)**: Quando existem camadas entre a camada de entrada e camada de saída, temos o que é conhecido como camada oculta. Quanto mais camadas de neurônio em uma rede neural, maior será a capacidade do modelo de compreender relações complexas nos dados. Observação: O custo de processamento computacional aumenta na medida em que neurônios são adicionados à rede neural.
- **Convergência**: Termo usado para se referir ao processo de redução do erro para o mínimo possível.
- **Hiperparâmetros**: São parâmetros externos, configurados antes do treinamento que impacta na eficácia do aprendizado de um modelo. Exemplos: Taxa de aprendizagem (Learning Rate), quantidade de camadas, quantidade de neurônios, momento (momentum), etc.
- **Parâmetros**: São parâmetros internos, aprendidos pelo modelo durante o treinamento.


## Conceitos Importantes

### Descida do Gradiente

O gradiente é usado para indicar como os parâmetros de um modelo devem ser ajustados para obter o resultado mais otimizado possível. Durante um treinamento, o gradiente serve como uma bússola que guia o aprendizado.

- **Mínimo local**: O mínimo local é um ponto onde o valor da função de erro é menor do que outros pontos por onde o gradiente passou, mas que pode não ser o menor ponto possível.

- **Mínimo global**: O mínimo global é o ponto com o menor valor da função de erro do que todos os outros pontos.


### Taxa de Aprendizagem (Learning Rate)

A taxa de aprendizagem é utilizada nos cálculos de otimização de aprendizado, definindo o tamanho dos passos percorridos na descida do gradiente.

- **Alta**: Uma taxa alta faz com que o caminho percorrido pelo gradiente tenha intervalos maiores, o que faz com que um modelo leve menos tempo para ser treinado, mas aumentando o risco de alcançar o mínimo global.

- **Baixa**: Quando a taxa é baixa, significa que os passos durante a descida do gradiente será menor, mais detalhada, o que faz com que o treinamento leve mais tempo, mas aumentando a chance do mínimo global ser encontrado.


### Momento (Momentum)

O momentum é um parâmetro que auxilia os algoritmos de otimização de aprendizado a encontrar o mínimo global. Não é um parâmetro tão relevante quanto a taxa de aprendizagem, mas pode ser configurado.

- **Alto**: Aumenta a velocidade de treinamento do modelo.
- **Baixo**: Ajuda a evitar mínimos locais, mas nem sempre funciona.


### Função de ativação

As [funções de ativação](https://en.wikipedia.org/wiki/Activation_function) são responsáveis por determinar a saída de um neurônio de acordo com os dados de entrada. Existem váriados tipos de funções que podem ter desempenho bom ou ruim de acordo com cada situação.

### Feedforward

Feedforward é o termo usado para descrever a forma como os dados percorrem a rede neural da camada de entrada, passando pelas camadas subsequentes até chegar à camada de saída.


### Backpropagation

A *retropropagação* - tradução literal de backpropagation - envolve um conjunto de equações que são aplicadas a todos os pesos, usada em diversas arquiteturas de redes neurais. Após os dados de entrada serem processados pela rede neural, a diferença entre o valor de resposta e o valor de saída é calculada e usada em equações como [MSE](https://pt.wikipedia.org/wiki/Erro_quadr%C3%A1tico_m%C3%A9dio) ou [RSME](https://en.wikipedia.org/wiki/Root-mean-square_deviation). O resultado é usado como parâmetro para o reajuste dos pesos, que é aplicado na ordem inversa - partindo da camada de saída em direção à camada de entrada.


## Definição de Hiperparâmetros

Este processo tem grande impacto no treinamento de um modelo e cada arquitetura de rede neural tem suas características e hiperparâmetros para serem configurados. Entretanto, existem alguns que são comuns a praticamente todas as arquiteturas:

- Taxa de Aprendizado (Learning Rate)
- Quantidade de épocas (Epochs)
- Tamanho do conjunto de dados (Batch Size)
- Funções de ativação
- Quantidade de camadas
- Quantidade de neurônios

### Quantidade de camadas e neurônios

O número de neurônios de entrada varia de acordo com a quantidade de atributos no conjunto de dados de treinamento. Por exemplo, se temos dois atributos, teremos dois neurônios na entrada. Já a quantidade de neurônios de saída pode ser definida de acordo com a quantidade de classes que o modelo está tentando prever quando se trata de problemas de classificação e apenas um neurônio quando se trata de problemas de regressão.

A quantidade de camadas varia de acordo com a complexidade do problema que o modelo deve resolver. Problemas lineares não exigem camadas ocultas, diferentemente de problemas não lineares que requerem maior capacidade de identificar relações complexas.

Apesar de não existir resposta para todos os casos, uma forma de calcular neurônios para camadas ocultas, de acordo com a literatura, se da pela metade da soma entre os neurônios das camadas de entrada e saída, sendo boa prática definir a mesma quantidade de neurônios para todas as camadas ocultas.

### Função de ativação

As funções de ativação são hiperparâmetros importantes que podem variar de acordo com cada camada, mas que também não possuem padrões explícitos. As estratégias mais difundidas consistem

## Conclusão

Sejam métodos simples ou não, a área de machine learning é muito experimental - especificamente no que concerne a redes neurais. A gama enorme de possibilidades de hiperparâmetros para otimizar o desempenho do modelo faz com que o treinamento seja mais custoso em muitos aspectos, mas os resultados podem fazer valer o esforço.