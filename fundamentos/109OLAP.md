# OLAP - On-Line Analytical Processing (Processamento Analítico On-Line)

OLAP é um conceito de interface com o usuário que proporciona a capacidade de ter idéias sobre os dados, permitindo analisá-los profundamente em diversos ângulos. As funções básicas do OLAP são:

* Visualização multidimensional dos dados;
* Exploração;
* Rotação;
* Vários modos de visualização.

__O OLAP e o Data Warehouse são destinados a trabalharem juntos__, enquanto o DW armazena as informações de forma eficiente, o OLAP deve recuperá-las com a mesma eficiência, porém com muita rapidez. As duas tecnologias se complementam, ao ponto de que um Data Warehouse para ser bem sucedido, já na sua concepção, deve levar em consideração o que se deseja apresentar na interface OLAP.

O OLAP é uma interface com o usuário e não uma forma de armazenamento de dados, porém se utiliza do armazenamento para poder apresentar as informações.

Os métodos de armazenamento são:

* ROLAP (OLAP Relacional): Os dados são armazenados de forma relacional.
* MOLAP (OLAP Multidimensional): Os dados são armazenados de forma multidimensional.
* HOLAP (OLAP Híbrido): Uma combinação dos métodos ROLAP e MOLAP.
* DOLAP (OLAP Desktop): O conjunto de dados multidimensionais deve ser criado no servidor e transferido para o desktop. Permite portabilidade aos usuários OLAP que não possuem acesso direto ao servidor.

Os métodos mais comuns de armazenamento de dados utilizados pelos sistemas OLAP são ROLAP e MOLAP, a única diferença entre eles é a tecnologia de banco de dados. O ROLAP usa a tecnologia RDBMS (Relational DataBase Management System), na qual os dados são armazenados em uma série de tabelas e colunas. Enquanto o MOLAP usa a tecnologia MDDB (MultiDimensional Database), onde os dados são armazenados em arrays multidimensionais.

Os dois fornecem uma base sólida para análise e apresentam tanto vantagens quanto desvantagens. Para se escolher entre os dois métodos deve-se levar em consideração os requisitos e a abrangência do aplicativo a ser desenvolvido.

ROLAP é mais indicado para DATA WAREHOUSE pelo grande volume de dados, a necessidade de um maior número de funções e diversas regras de negócio a serem aplicadas.

MOLAP é mais indidado para DATA MARTS, onde os dados são mais específicos e o aplicativo será direcionado na análise com dimensionalidade limitada e pouco detalhamento das informações.

Para se fazer uma comparação básica entre os dois métodos, as regras mais importantes são desempenho da consulta e desempenho do carregamento.

## Desempenho de consulta

O MOLAP fornece uma resposta rápida para praticamente qualquer consulta, pois no modelo multidimensional são gerados previamente todas as combinações e resumos possíveis.

O ROLAP responde às consultas da mesma forma que os aplicativos RDBMSs, a velocidade da resposta depende da informação desejada, pois a maior parte do processamento é feito em tempo de execução tendo em vista que os dados pré-calculados e resumidos geralmente não atendem a todas as solicitações dos usuários.

## Desempenho de carregamento

O MOLAP necessita de um longo período para execução da carga de dados, raramente esta carga é diária devido ao grande volume de informações a serem atualizadas para possibilitar um retorno rápido às consultas da inferface OLAP.

O ROLAP possibilita um carregamento mais rápido devido à estrutura de tabelas e colunas, menos complexa em comparação à estrutura de arrays utilizada pelo MOLAP. Outro fator importante na rapidez da carga é o número menor de informações pré-calculadas e resumidas.

Por fim, chegamos à conclusão de que não existe uma definição entre qual o melhor, ROLAP ou MOLAP, e que a tendência será a utilização do método HOLAP (citado acima), no qual é possível utilizar as vantagens dos dois modelos numa mesma arquitetura.
