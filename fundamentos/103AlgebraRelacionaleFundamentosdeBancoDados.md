# Álgebra Relacional

Na ciência da computação, álgebra relacional é uma derivação descendente da lógica de primeira ordem e da álgebra de conjuntos, auxilia o trabalho ao identificar os componentes de uma sequência ordenada de elementos por nome ao invés de uma coluna de chaves numéricas. A principal aplicação da álgebra relacional é sustentar a fundamentação teórica de banco de dados relacional, particularmente linguagem de consulta para tais bancos de dados, entre os maiores o SQL.

## Funções da Álgebra Relacional

A álgebra relacional se divide em nove operações:
  - UNION - União;
  - INTERSECTION - Intersecção;
  - DIFFERENCE - Diferença, Subtração;
  - PRODUCT - Produto, Produto Cartesiano;
  - SELECT - Seleção
  - PROJECT - Projeção
  - JOIN - Junção
  - DIVIDE - Divisão
  - ASSIGNMENT - Designação, Atribuição
  -
Vamos usar a seguinte tabela como estudo de caso para exemplificar nossas operações:

PESSOA

ID | NOME | SOBRENOME | DATA_NASCIMENTO | SEXO | SALARIO | CIDADE
---|------|-----------|-----------------|------|---------|--------
210|João|Silva|02/08/1994|M|2000|1    
432|Fernando|Wall|07/06/1998|M|2450|3
532|Eduarda|Martins|11/02/1999|F|2300|3

__Atribuindo um valor a uma nova tabela__

O objetivo do operador de designação/atribuição é atribuir o resultado de uma operação a uma nova relação, gerando assim uma nova tabela

Simbologia: <-----

Exemplo: R <----- A *U* B

Simbologia: :=
Exemplo: R := union(A,B)

__Operação de selecção (Select)__

è utilizada para selecionar parte do conjunto, esse subconjunto será gerado com base em registros que satisfaçam uma condição pré definida.

Simbologia: δ

Exemplo: δ SALARIO > 2200

A seleção a cima, nos apresentará como resultado as informações abaixo:

ID | NOME | SOBRENOME | DATA_NASCIMENTO | SEXO | SALARIO | CIDADE
---|------|-----------|-----------------|------|---------|--------
432|Fernando|Wall|07/06/1998|M|2450|3
532|Eduarda|Martins|11/02/1999|F|2300|3

__Operação de Projeção (Project)__

A operação de projeção é utilizada para selecionar determinadas colunas de uma relação. A operação é executada em apenas uma relação e o resultado é uma nova relação contendo apenas os atributos selecionados, eliminando-se as duplicidades.

Simbologia: π

Exemplo: π NOME, SOBRENOME^

Teremos o seguinte resultado:

NOME | SOBRENOME
-----|----------
João|Silva    
Fernando|Wall
Eduarda|Martins

__Aninhar de operações e renomear de atributos__

Podemos aninhar as operações e produzir novos resultados sem a necessidade de sucessivas operações. Imaginem se nos interessa apenas o nome, sobrenome dos funcionários que recebam 2000. Vejamos como ficaria a expressão em álgebra relacional:

1 =>Relação = Tabela, entidade, na terminologia formal de banco de dados.
2 =>Chave-valor = Linha da tabela, registro, na terminologia formal de banco de dados.

π NOME, SOBRENOME (δ SALARIO = 2000 (PESSOA)), produz o seguinte resultado:

NOME | SOBRENOME
-----|----------
João|Silva

Poderíamos escrever esta mesma operação criando uma operação intermediaria e renomear os valores:

R1 <---- δ SALARIO = 2000 (PESSOA)

RESULT(Name, LastName) <---- π NOME, SOBRENOME (R1)
