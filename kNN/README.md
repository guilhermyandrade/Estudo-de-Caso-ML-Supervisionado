### KNN - K Nearest Neighbors

KNN é a sigla usada para "K Nearest Neighbors", que significa "K Vizinhos Mais Próximos", sendo "K" o número de vizinhos. Este método de aprendizado utiliza a distância entre dois pontos em um [plano cartesiano](https://pt.wikipedia.org/wiki/Sistema_de_coordenadas_cartesiano#/media/Ficheiro:Cartesian-coordinate-system.svg) para classificar novas instâncias.

#### Cálculo de Distância Euclidiana

Essa equação calcula a distância entre duas coordenadas *(x, y)* no plano cartesiano. Calcula-se a diferença entre os eixos X e Y de cada coordenada, elevando-as ao quadrado e fazendo a soma dos valores obtidos. Por fim, obtem-se a raiz quadrada da soma, valor que representa a distância.

        DE = √( Ai - Bi )²

Onde:

- *A* é uma coordenada para comparação. 
- *B* é outra coordenada para comparação. 
- *i* representa o valor do eixo de cada coordenada que está sendo verificado.

    Exemplo:

        Coordenadas A e B:
             x  y
        A = (2, 5)
        B = (4, 3)
        
            x          y
        √(2 - 4)² + (5 - 3)² => √4 + 4 => √8 => 2,8

        Portanto, a diferença euclidiana entre os pontos A e B é 2,8.

<br>

## Conclusão

#### Vantagens

- Fácil de interpretar
- Eficaz em bases de dados com relações complexas
- Aplicável para classificação e regressão
- Capacidade de adaptação

#### Desvantagens

- Número K pequeno pode ser facilmente influenciado por outliers
- Leva mais tempo para fazer previsões
- Quantidade desbalanceada de classes pode enviesar o modelo
- Exige maior cuidado com preprocessamento dos dados. É essencial aplicar a normalização ou padronização para resultados mais eficazes.