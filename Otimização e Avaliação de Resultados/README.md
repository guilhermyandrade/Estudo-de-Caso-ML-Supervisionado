### Otimização e Avaliação de Resultados

Otimizar resultados de um modelo implica no uso de ferramentas como GridSearchCV para combinar hiperparâmetros e alcançar o melhor resultado. Essa ferramenta verifica todas as combinações de parâmetros desejada pelo usuário.

Além do GridSearch, existem outros métodos que podem auxiliar na otimização, assim como a validação cruzada. Essa técnica é usada para avaliar resultados, mas também pode ajudar na otimização ao testar um método de aprendizado (detalhes no tópico sobre validação cruzada).

A avaliação consiste no uso de técnicas estatísticas para determinar se um método é melhor do que outro. Recursos como distribuição normal, teste de hipótese ou paramétricos, média, desvio padrão, min, max, etc, são fundamentais em artigos científicos onde uma hipótese precisa ser comprovada estatisticamente, bem como - suponho - na implementação de um modelo no ambiente de produção de uma empresa.

### Técnicas para Avaliação

Explicação dos principais métodos utilizados no código. Para mais detalhes, acesse os notebooks.

#### Validação Cruzada

Dividir um conjunto de dados entre **bases** de treinamento e teste **fixas** não é uma prática comum, visto que há possibilidade de registros com boas combinações de atributos acabarem em um conjunto de dados de teste.

Para solucionar este problema, o método **K-Fold Cross Validation** - também conhecido como validação cruzada - separa o conjunto de dados de em K partes, sendo o valor de K definido pelo usuário. Se temos que K=2, o conjunto será repartido entre bases de treinamento e teste duas vezes; na primeira, uma parcela será retirada do conjunto de dados para testar o modelo e verificar seu desempenho e, em seguida, a parcela é devolvida e uma nova é retirada, verificando qual a melhor base de treinamento possível, sem deixar nenhum registro de lado.

Pode ser usado como fonte de dados para análises estatísticas de um método de aprendizado, mas também é uma prática comum armazenar o modelo com o melhor resultado.


#### ANOVA / Teste F

O teste ANOVA também é conhecido como avaliação de variância ou [teste F](https://pt.wikipedia.org/wiki/Teste_F). Os cálculos visam provar se existe real diferença entre grupos num conjunto de dados usando média do conjunto e de cada grupo, soma do quadrado dos grupos (SSG), grau de liberdade dos grupos (DFG), soma do quadrado do erro (SSE) e grau de liberdade do erro (DFE). Por fim, os valores são aplicados à seguinte equação:

    F = (SSG / DFG) / (SSE / DFE)

Para encontrar o resultado final, o valor de F deve ser consultado na tabela F. Se o resultado da equação estiver entre 0 e o valor consultado na tabela F, não há diferença estatística. Caso o resultado da equação seja maior, então há diferença estatística. Entretanto, o teste F não mostra a diferença estatística individual dos grupos do conjunto de dados, apenas a visão geral.

Se existir diferença entre os grupos, é necessário verificar quais grupos são diferentes entre si.

#### Tukey

O teste de comparações múltiplas de Tukey, também conhecido como teste de Tukey, visa verificar se há diferença estatística entre cada grupo de um conjunto de dados.

Temos que a hipótese nula para esse teste é: os grupos no conjunto de dados não tem diferença estatística entre si.

- **Valor P**: É a probabilidade de se observar os dados obtidos se a hipótese nula for verdadeira. Um pouco confuso, não? É a maneira estatística de explicá-lo, mas de forma simplificada, seria como um percentual que representa a confiabilidade da hipótese nula de acordo com os dados obtidos.

- **Valor de Alpha**: É o valor que determina o intervalo de confiança do teste de hipótese. As opções para este parâmetro geralmente variam entre 0.05 e 0.01, representando 5% e 1% de margem de erro, respectivamente. Neste caso, o valor padrão de alpha é 0.05 (5%), o que indica que a confiabilidade do teste de hipótese é de 95%.

    Se o **valor P** for menor ou igual ao **valor de alpha**, significa que há evidências suficientes para rejeitar a hipótese nula. 

- **Reject**: O teste retorna uma tabela de comparações. A coluna "reject" diz se a hipótese nula pode ser rejeitada. *True* indica que sim, *False* indica que não.