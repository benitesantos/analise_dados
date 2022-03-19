  <img src="https://www.kindpng.com/picc/m/81-811458_jupyter-notebook-logo-hd-png-download.png" width="210" height="140">

# **Análise de dados**
 Uma análise de dados simples.
 Que ajudou o tomador de decisão a implementar
 um produto que não estava nas outras lojas.

 ## Requisitos:
 - Ter o jupyter notebook instalado.
 - Ter o arquivo Vendas.xlsx nas mesma pasta do arquivo introducao_analise_dados.ipynb

## Pacotes instalados:
- Pandas
```bash
pip install pandas
```

## Processo das ferramentas que foram usadas:

Código que importa a tabela em excel e trás  para o python.

```python
tabela = pd.read_excel('Vendas.xlsx')
display(tabela)
```

Código que informa o faturamento total da loja, primeiro filtra-se a tabela na coluna 'Valor Final' e usa a função sum() pra somar todos os valores da coluna.

```python
faturamento_total = tabela['Valor Final'].sum()
print(faturamento_total)
```

Para acharmos o faturamento por cada loja na tabela. Filtra-se a tabela, e depois agrupa atraves do comando groupby()

```python
#faturamento por loja
faturamento_por_loja = tabela[['ID Loja','Valor Final']].groupby('ID Loja').sum()
display(faturamento_por_loja)
```
Para acharmos agora o faturamento por loja e produto. Filtra-se novamente a tabela, só que acrescentando as colunas que queremos que apareça na tabela.

```python
faturamento_por_produto = tabela[['ID Loja','Produto','Valor Final']].groupby(['ID Loja','Produto']).sum()
display(faturamento_por_produto)
```
## Aprendizagem

- Aprendi algumas ferramentas para melhor visualizar os dados. groupby() do pandas.
- Também interpretrar os dados , ver se tem dados que saltam os olhos.

## Dificuldades

- Filtrar bem os valores