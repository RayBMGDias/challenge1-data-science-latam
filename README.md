# Challenge1-data-science-latam

# 🛒 Análise de Vendas — AluraStore
Este projeto realiza uma análise exploratória das vendas de quatro lojas da rede **AluraStore**,
com base em dados disponibilizados em arquivos `.csv` públicos.

## 🚀 Objetivo

Aplicar conceitos de análise e visualização de dados para identificar, com base em métricas reais, qual loja apresenta o menor desempenho e deve ser vendida. O projeto utiliza bibliotecas nativas do Python e ferramentas amplamente usadas em ciência de dados.

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
---
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

Faturamento Total de Cada Loja:
|  Loja  | Faturamento (R$) |
|--------|------------------|
|Loja 1  |R$ 1.534.509,12   |
|Loja 2	 |R$ 1.488.459,06   |
|Loja 3	 |R$ 1.464.025,03   |
|Loja 4  |R$ 1.384.497,58   |


Vendas Totais por Categoria (Todas as Lojas):
| Categoria               | Total Vendido (R$) |
|-------------------------|--------------------|
| Eletrônicos             | 6.519.744,59       |
| Eletrodomésticos        | 5.358.770,66       |
| Móveis                  | 2.962.647,31       |
| Esporte e Lazer         | 575.997,31         |
| Instrumentos Musicais   | 1.392.820,77       |
| Brinquedos              | 282.153,90         |
| Utilidades Domésticas   | 227.149,45         |
| Livros                  | 150.780,86         |

---

📌🛠️ Tecnologias Utilizadas:
- Google Colab
- Python
- Bibliotecas: (Pandas, pandas, csv, urllib, Matplotlib)
  
---

💡 Conclusão:
Este projeto permite uma visão clara do desempenho de cada loja e das categorias de produtos mais rentáveis. Ele serve como base para decisões estratégicas, como:

- Qual loja vender ou manter
- Quais categorias impulsionar
- Ajustar políticas de frete ou marketing por produto

✍️ Autor
Projeto desenvolvido para fins educacionais com base nos dados do Challenge Data Science da Alura.
Rayra Bandeira
