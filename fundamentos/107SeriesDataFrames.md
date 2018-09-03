# Series e Dataframes

Os conceitos de serie e dataframes servem para qualquer linguagem, mas para fins de exemplo usaremos a linguagem python durante este texto.

## Serie

Uma série é um objeto unidimensional que pode conter qualquer tipo de dados, como números inteiros, flutuantes e sequências de caracteres. Vamos dar uma lista de itens com um argumento de entrada e criar um objeto de série para essa lista.

```python
>>> import pandas as pd
>>> x = pd.Series([6,3,4,6])
>>> x
0 6
1 3
2 4
3 6

dtype: int64
```

Os rótulos dos eixos para os dados, são chamados de índices. O comprimento do índice deve ser o mesmo que o comprimento dos dados. Como não passamos nenhum índice no código acima, o índice padrão será criado com os valores sequenciais de 0 até o tamanho -1

Para definir índices para os dados

```python
>>> x = pd.Series([6,3,4,6], index=['a', 'b', 'c', 'd'])
>>> x
a 6
b 3
c 4
d 6

dtype: int64
```

O índice na coluna mais a esquerda agora se refere aos dados da coluna da direita. Podemos pesquisar os dados referindo ao seu índice

```python
>>> x["x"]
4
```

## DataFrame

Um DataFrame é um objeto bidimensional que pode ter colunas com tipos diferentes em potencial. Tipos diferentes de entradas incluem dicionários, listas, séries e até mesmo outro DataFrame.

Para criar um DataFrame passando uma matriz do NumPy com datetime como índices e colunas rotuladas

```python
>>> import numpy as np
>>> dates = pd.date_range(‘20170505’, periods = 8)
>>> dates
DatetimeIndex([‘2017–05–05’, ‘2017–05–06’, ‘2017–05–07’, ‘2017–05–08’,‘2017–05–09’, ‘2017–05–10’, ‘2017–05–11’, ‘2017–05–12’],dtype=’datetime64[ns]’, freq=’D’)
>>> df = pd.DataFrame(np.random.randn(8,3),index=dates, columns=list(‘ABC’))
>>> df
A B C
2017–05–05 -0.301877 1.508536 -2.065571
2017–05–06 0.613538 -0.052423 -1.206090
2017–05–07 0.772951 0.835798 0.345913
2017–05–08 1.339559 0.900384 -1.037658
2017–05–09 -0.695919 1.372793 0.539752
2017–05–10 0.275916 -0.420183 1.744796
2017–05–11 -0.206065 0.910706 -0.028646
2017–05–12 1.178219 0.783122 0.829979
```

Podemos acessar as linhas superiores e inferiores usando os comandos `df.head` e `df.tail`:

```python
>>> df.head ()
abc
2017–05–05 -0,301877 1,508536 -2,065571
2017–05–06 0,613538 -0,052423 -1,206090
2017–05–07 0,777951 0,835798 0,345913
2017–05–08 1,339559 0,900384 -1,037658
2017–05–09 -0,695919 1,372793 0,539752
>>> df.tail ()
abc
2017–05–08 1,339559 0,900384 -1,037658
2017–05–09 -0,695919 1,372793 0,539752
2017–05–10 0,275916 -0,420183 1,744796
2017–05–11 -0,206065 0,910706 -0,028646
2017–05–12 1,178219 0,783122 0,829979
```

Podemos até acessar um breve resumo estatístico de nossos dados:

```python
>>> df.describe()

A B C
count 8.000000 8.000000 8.000000
mean 0.372040 0.729842 -0.109691
std 0.731262 0.657931 1.244801
min -0.695919 -0.420183 -2.065571
25% -0.230018 0.574236 -1.079766
50% 0.444727 0.868091 0.158633
75% 0.874268 1.026228 0.612309
max 1.339559 1.508536 1.744796
```

Também podemos aplicar funções aos dados como soma cumulativa, visualizar histogramas, mesclar DataFrames, concatenar e remodelar DataFrames.

```python
>>> df.apply(np.cumsum)
A B C
2017–05–05 -0.301877 1.508536 -2.065571
2017–05–06 0.311661 1.456113 -3.271661
2017–05–07 1.084612 2.291911 -2.925748
2017–05–08 2.424171 3.192296 -3.963406
2017–05–09 1.728252 4.565088 -3.423654
2017–05–10 2.004169 4.144905 -1.678858
2017–05–11 1.798104 5.055611 -1.707504
2017–05–12 2.976322 5.838734 -0.877526
```
