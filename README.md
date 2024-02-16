### Introdução

O objetivo deste repositório é verificar o desempenho de diferentes métodos de aprendizado de máquina supervisionados com o propósito de encontrar o método mais eficaz possível para cada base de dados.

Observação: O ChatGPT foi usado meramente para impulsionar os estudos, tirando eventuais dúvidas e provendo maior entendimento das equações envolvidas em cada método de aprendizado. **Cada anotação, descrição, código ou comentário foi escrito por mim, autor do repositório, com base no meu entendimento sobre os temas abordados**.

### Estrutura do repositório

A otimização de parâmetros e aplicação de técnicas para analisar o desempenho dos modelos foram aplicadas em [Otimização e Avaliação de Resultados](/Otimização%20e%20Avaliação%20de%20Resultados). Os outros diretórios servem para auxiliar no entendimento dos métodos.

Cada diretório armazena:

- Arquivo README, explicando o método usado no sub-diretório
- Arquivos *.py* (python), onde o conhecimento teórico está aplicado
- O nome dos arquivos *.py* contém o percentual de precisão do modelo ( arquivo.py - precisão )

<br>
    Estrutura de diretórios

    1. Método de aprendizado

        1.1. Arquivo.py - precisão
        1.2. README.md (Descrição/anotações sobre o método)

### Bases de dados

Os dados usados nos modelos deste diretório são provenientes de três bases de dados sobre temas distintos, listadas abaixo. A explicação sobre cada uma delas, bem como foram processadas para iniciar o treinamento dos algorítmos, está disponível no sub-diretório [Pre-processamento](/_Pre-processamento).

- **Base condicao_saude**
- **Base census**
- **Base credit_data**