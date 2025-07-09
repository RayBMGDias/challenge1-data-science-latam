# challenge1-data-science-latam
AluraStoreLatam

# 🛒 Análise de Vendas — AluraStore
Este projeto realiza uma análise exploratória das vendas de quatro lojas da rede **AluraStore**,
com base em dados disponibilizados em arquivos `.csv` públicos.

A análise foi feita utilizando **Python**, com bibliotecas como `pandas`, `csv` e `urllib`.

## 📁 Dados Utilizados

Os dados foram carregados diretamente de URLs hospedadas no GitHub da Alura:

- Loja 1: `loja_1.csv`
- Loja 2: `loja_2.csv`
- Loja 3: `loja_3.csv`
- Loja 4: `loja_4.csv`
  
Cada arquivo contém colunas como:

- `Produto`
- `Categoria do Produto`
- `Preço`
- `Frete`
- `Quantidade de parcelas`
- `Data da Compra`
- `Avaliação`


## 🔍 Análises Realizadas

### ✅ Faturamento por Loja

Foi calculado o **faturamento total** de cada loja, somando os valores de todas as vendas (baseado na coluna `Preço`).
````
for venda in dados_loja:
  preco = float(venda['Preço'])
  faturamento_loja += preco
````

### ✅ Vendas por Categoria (Valor Total)
Em seguida, foi calculado o total vendido por categoria, tanto em cada loja separadamente quanto no consolidado geral das 4 lojas.

O valor foi obtido pela multiplicação entre o preço e a quantidade de parcelas:
```
valor_venda = preco * quantidade
```

### ✅ Vendas por Categoria (Simples)
Também foi gerado um agrupamento simples com o total de vendas por categoria com base apenas no valor do Preço, usando pandas.groupby:
```
loja.groupby('Categoria do Produto')['Preço'].sum()
```

📊 Exemplos de Resultados
Faturamento Total de Cada Loja
|  Loja  | Faturamento (R$) |
|--------|------------------|
|Loja 1  |R$ 1.534.509,12   |
|Loja 2	 |R$ 1.488.459,06   |
|Loja 3	 |R$ 1.464.025,03   |
|Loja 4  |R$ 1.384.497,58   |
