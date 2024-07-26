# Atividade 2 - Bootcamp Avanti - Machine Learning
### Aluna: Karen Ribeiro


### 1. Escreva uma função que receba uma lista de números e retorne outra lista com os números ímpares.

    def numeros_impares (list):
        num_impar = []
        for numero in list:
            if numero % 2 != 0:
                num_impar.append(numero)
        return num_impar

### 2. Escreva uma função que receba uma lista de números e retorne outra lista com os números primos presentes.

    def numeros_primos (list):
        num_primo = []
        for numero in list:
            if numero > 1:
                for i in range(2, numero):
                    if (numero % i) == 0:
                        break
                else:
                    num_primo.append(numero)
        return num_primo

### 3. Escreva uma função que receba duas listas e retorne outra lista com os elementos que estão presentes em apenas uma das listas.

    def numeros_unicos(list1, list2):
        num_unico = []
        for numero in list1:
            if numero not in list2:
                num_unico.append(numero)
        for numero in list2:
            if numero not in list1:
                num_unico.append(numero)
        return num_unico

### 4. Dada uma lista de números inteiros, escreva uma função para encontrar o segundo maior valor na lista.

    def segundo_maior(lista):
    lista_unica = list(set(lista)) 
    lista_unica.sort(reverse=True) 
    if len(lista_unica) < 2:
        return None  
    return lista_unica[1]

### 5. Crie uma função que receba uma lista de tuplas, cada uma contendo o nome e a idade de uma pessoa, e retorne a lista ordenada pelo nome das pessoas em ordem alfabética. 

    def ordenar_por_nome(lista_de_pessoas):
    return sorted(lista_de_pessoas)

### 6. Observe os espaços sublinhados e complete o código.
#### import __________.pyplot as plt (1)
#### import numpy as ___ (2)
#### fig, axs = plt.subplots(ncols=2, nrows=2, figsize=(5.5, 3.5),
####  layout="constrained")
#### for ___ in range(2): (3)
####  for ___ in range(2): (4)
####  axs[row, col].annotate(f'axs[{row}, {col}]', (0.5, 0.5),
####  transform=axs[row, col].transAxes,
####  ha='center', va='center', ________=18, (5)
####  color='darkgrey')
#### fig.suptitle('__.subplots()') (6)

    1 - matplotlib
    2 - np 
    3 - row
    4 - col
    5 - fontsize
    6 - plt

### 7. Observe os espaços sublinhados e complete o código.
#### import numpy as np
#### import __________ as mpl (1)
#### import __________.______ as plt (2)
#### x = np.________(-2 * np.pi, 2 * np.pi, 100) (3)
#### y = np.____(x) (4)
#### __, __ = plt.subplots() (5)
#### ax.____(_, _) (6)

    1 - matplotlib
    2 - matplotlib.pyplot 
    3 - linspace
    4 - sin
    5 - fig, ax 
    6 - plot(x, y)

### 8. Utilizando pandas, como realizar a leitura de um arquivo CSV em um DataFrame e exibir as primeiras linhas?
    1 - Ler o arquivo CSV em um dataframe com o método "read_csv(caminho)"
    2 - Exibir as primeiras linhas com o método head()

    import pandas as pd
    df = pd.read_csv('caminho/para/seu_arquivo.csv')
    print(df.head())

### 9. Utilizando pandas, como selecionar uma coluna específica e filtrar linhas em um “DataFrame” com base em uma condição?

    1 - Selecionar uma coluna específica utilizando o dataframe (df) e nome da coluna
    2 - Filtrar linhas no dataframe com expressões booleanas

    df['Nome_da_Coluna']
    df['Idade'] > 18 (expressão booleana)
    df[df['Idade'] > 18] (retornar as linhas que atendem à condição)

### 10.Utilizando pandas, como lidar com valores ausentes (NaN) em um DataFrame?

    1 - Verificar os valores (NaN) com o método isna() para apontar onde estão os NaNs. Pode-se combinar com o método sum() para contar o número de NaNs por coluna.
        df.isna()
        df.isna().sum()

    2 - Podemos remover os valores ausentes usando o método dropna() (remove a linha), dropna(axis=1) (remove a coluna), dropna(how='all') (remove a linha em que todos registros estão ausentes)
        df.dropna()
        df.dropna(axis=1)
        df.dropna(how='all')

    3 - Podemos preencher os NaNs com novos valores, a partir do método fillna()
        df.fillna((value={'Coluna': Valor}))
        f.fillna(method='ffill') (preencher com valor anterior)
        df.fillna(method='bfill') (preencher com valor posterior)

    4 - Em séries temporais, ainda podemos lidar com os valores ausentes usando interpolação, a partir do método interpolate()
        df.interpolate()