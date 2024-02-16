### Árvore de decisão

Uma árvore de decisão é um método de aprendizado de máquina que se assemelha à estrutura de uma árvore onde os atributos de uma base de dados formam as conexões de cada ramificação da árvore. Ao final do aprendizado, a árvore classificará novos registros de acordo com a estrutura condicional que foi gerada com o conjunto de dados do treinamento.

#### Imagem 1 - Base de dados da condição de saúde.

<div align="center"><img title="Imagem 1" src="https://github.com/guilhermyandrade/Estudo-de-Caso-ML-Supervisionado/blob/main/_Imagens/base_condicao_saude.png" ></div>

#### Imagem 2 - Aprendizado por Árvore de Decisão a partir da base condicao_saude

<div align="center"><img title="Imagem 2" src="https://github.com/guilhermyandrade/Estudo-de-Caso-ML-Supervisionado/blob/main/_Imagens/arvore_aprendizado.png" ></div>

<hr>
Para definir quais atributos devem ser posicionados no topo ou na raiz da árvore, é necessário aplicar duas equações à base de dados para verificar a relevância de cada atributo para a o aprendizado do modelo: a equação da **entropia** e a equação do **ganho de informação**.


#### Equação da entropia

Verifica a imprevisibilidade de determinado valor aparecer na base de dados. Quanto maior é a entropia, maior é a incerteza ao realizar uma previsão para o valor do contexto.

        -Pi * log2( Pi )

Onde:

- *Pi* representa a proporção da classe do contexto em relação ao total
- *log2( Pi )* é o logaritmo da proporção da classe na base 2

#### Equação do ganho de informação

Após o cálculo da entropia inicial, a equação deve ser realizada em todos os atributos previsores da base de dados de modo que a equação da entropia seja aplicada à proporção de cada classe e em cada valor distinto do atributo.


        Entropia( S ) - ( Si / S * Entropia( Si ) )

Onde:


- *S* é a entropia inicial, ou seja, das classes do conjunto de dados
- *Si* é o conjunto de dados subdividido pela classe do contexto


A ordem do atributo na árvore de decisão é definido de acordo com o resultado da equação de ganho de informação.

Portanto, realizando os cálculos necessários com a base de dados de teste inicial, é possível chegar à estrutura exibida na imagem 2.

<br>

Exemplo de registro:

    Status do peso = Acima
    Alimentação = Desbalanceada
    Pressão sanguínea = Normal
    Colesterol = Normal
    Diabetes = Sim
    Exercício físico = Nao

Classificação do exemplo:

#### Imagem 3 - Árvore de decisão percorrida pelo registro de exemplo
<div align="center"><img title="Imagem 3" src="https://github.com/guilhermyandrade/Estudo-de-Caso-ML-Supervisionado/blob/main/_Imagens/arvore_percorrida_exemplo.png" ></div>


Portanto, de acordo com a árvore de decisão apresentada na imagem 3, o risco para este registro pode ser classificado como **"Nao regular"**.

## Conclusão

Uma árvore de decisão pode não ser tão eficiente quanto uma rede neural na maior parte dos casos. Contudo, este aprendizado de máquina foi aprimorado, originando o que é conhecido hoje como [Random Forest](/Random%20Forest), sendo capaz de competir, até certo ponto, com modelos mais sofisticados.


#### Vantagens

- Fácil de interpretar
- Não exige escalonamento de dados
- Capaz de identificar características irrelevantes por conta própria por conta da entropia e ganho de informação
- Pode aprender com atributos nos formatos numérico e texto
- Exige menos pré-processamento de dados

#### Desvantagens

- Pode gerar ramos muito específicos (Overtiffing)
- A estrutura da árvore é facilmente afetada por variações nos dados
- Tendência a gerar vieses por valores mais frequentes em um atributo
- Problemas para gerar ramos muito complexos, levando o modelo a ter desempenho inferior em determinados tipos de conjuntos de dados
- Por conta disso, não é adequado para todos os tipos de dados
