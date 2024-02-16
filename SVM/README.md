### SVM

O método SVM - Support Vectors Machine - consiste em encontrar a linha com a maior margem entre as coordenadas de um plano cartesiano.
<hr>

As equações matemáticas envolvidas nesse aprendizado de máquina são extensas e complexas. Abaixo estão listados resumos sobre os principais cálculos realizados nesse método. 

#### Envoltória Convexa

A envoltória convexa é a ligação entre coordenadas de um plano cartesiano de forma a envolver todos os registros de uma classe. Após encontrar os envoltórios, calcula-se a reta com a maior distância possível (margem) entre eles.

##### Erros

No caso onde a reta é traçada de forma que alguns registros não acabem sendo perfeitamente separados, uma equação é aplicada para verificar qual a menor taxa de erro possível, determinando qual a reta com a menor taxa de erro possível. Nesse cenário, a reta que separa os registros é a com a maior margem e menor taxa de erro.

#### Dados não lineares

Quando os dados não são lineares, significa que não é possível traçar uma reta para dividir as classes. Para traçar a reta, é necessário aplicar uma transformação à base de dados conhecida como [Kernel Trick](https://en.wikipedia.org/wiki/Kernel_method).

Nessa transformação, uma dimensão é adicionada ao conjunto de dados e permite que a reta seja traçada.

A partir do momento em que uma nova dimensão é adicionada, um novo atributo é criado. Esses atributos são conhecidos como [slack variables](https://en.wikipedia.org/wiki/Slack_variable#:~:text=In%20an%20optimization%20problem%2C%20a,constraint%20on%20the%20slack%20variable) e pode-se assumir que o modelo SVM também aprende a partir deles nessas ocasiões.

<br>

## Conclusão

SVM, em geral, é conhecida por ser uma técnica altamente eficaz quando comparada com outros métodos mais simples, como árvore de decisão, naive bayes, etc.

#### Vantagens

- É capaz de lidar com dados não lineares
- Não é muito influenciado por ruídos
- Utilizado para classificação e regressão
- Mais fácil de usar do que redes neurais

#### Desvantagens

- É preciso testar diversas combinações de parâmetros
- Lento; Equações complexas
- Black box - Não é amigável quando se trata de entender o processo de aprendizagem 