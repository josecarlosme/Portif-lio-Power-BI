# 📊 Dashboard de Vendas e Desempenho Comercial | Power BI

Dashboard interativo em Power BI que analisa as vendas de uma varejista norte-americana para responder uma pergunta de negócio: **onde a empresa ganha e onde perde dinheiro?**

![Dados por ano](<img width="1323" height="757" alt="image" src="https://github.com/user-attachments/assets/ea47158e-71e0-4329-ab1d-ecb4585fe263" />)


## 🎯 Objetivo

Transformar dados brutos de pedidos em um painel que permite acompanhar receita, lucro e margem, identificar os produtos, categorias e regiões de melhor e pior desempenho e apoiar decisões comerciais, como política de descontos e mix de produtos.

## 🗂️ Dados

- **Fonte:** Sample - Superstore (base pública amplamente usada para estudos de BI)
- **Período:** janeiro de 2014 a dezembro de 2017
- **Volume:** 9.994 linhas de venda, 5.009 pedidos, 793 clientes e 1.862 produtos
- **Dimensões de análise:** categoria, subcategoria, produto, cliente, segmento (Consumer, Corporate, Home Office) e região (West, East, Central, South)

## 📈 Indicadores gerais

| Indicador | Valor |
|---|---|
| Receita total | US$ 2,30 milhões |
| Lucro total | US$ 286,4 mil |
| Margem de lucro | 12,5% |
| Ticket médio por pedido | US$ 458,61 |

## 🛠️ Ferramentas

- Power BI Desktop
- Power Query (tratamento e preparação dos dados)
- DAX (medidas e tabela Calendário)
- Modelagem de dados com tabela Calendário para inteligência de tempo

## ⚙️ Etapas do projeto

1. **Importação e tratamento (Power Query):** importação do arquivo Excel, ajuste de tipos de dados, tratamento de duplicados e nulos e renomeação das colunas para português.
2. **Modelagem:** criação da tabela **Calendário** (ano, mês, trimestre) e relacionamento com a tabela de vendas pela data do pedido.
3. **Medidas em DAX:** criação dos indicadores de receita, lucro, margem, ticket médio e comparação com o ano anterior.
4. **Visualização:** construção de 3 páginas com segmentadores de ano, categoria e região e navegação entre páginas.
5. **Análise:** levantamento dos insights de negócio.

## 🧮 Principais medidas DAX

```DAX
Receita Total = SUM(superstore[Receita])

Lucro Total = SUM(superstore[Lucro])

Margem % = DIVIDE([Lucro Total], [Receita Total])

Ticket Médio = DIVIDE([Receita Total], DISTINCTCOUNT(superstore[ID do pedido]))

Receita Ano Anterior = CALCULATE([Receita Total], SAMEPERIODLASTYEAR(Calendario[Date]))

Crescimento YoY % = DIVIDE([Receita Total] - [Receita Ano Anterior], [Receita Ano Anterior])
```

## 📑 Páginas do relatório

| Página | O que mostra |
|---|---|
| **Dados por ano** | Cartões de Receita Total, Lucro Total, Margem % e Ticket Médio; gráfico de linhas da receita mensal comparada ao ano anterior; receita por região; segmentador de ano |
| **Produtos e Clientes** | Ranking dos produtos por receita; receita e lucro por categoria; participação dos segmentos de cliente em gráfico de rosca; tabela de clientes com receita e lucro |
| **Análise detalhada** | Matriz de categoria e subcategoria com receita, lucro e margem; árvore de decomposição por categoria, região e segmento; segmentadores de ano, categoria e região |

## 💡 Principais insights

- **Crescimento:** a receita saiu de US$ 484 mil em 2014 para US$ 733 mil em 2017 (+51%). Houve leve queda em 2015 (-2,8%), seguida de crescimento de 29,5% em 2016 e 20,4% em 2017.
- **Móveis vendem muito, mas lucram pouco:** a categoria Furniture gerou US$ 742 mil em receita, mas apenas US$ 18,5 mil de lucro (margem de 2,5%). Technology e Office Supplies operam com margem próxima de 17%.
- **Subcategorias com prejuízo:** Tables (-8,6% de margem, prejuízo de US$ 17,7 mil), Bookcases (-3,0%) e Supplies (-2,6%) dão prejuízo, mesmo com Tables faturando US$ 207 mil.
- **Descontos corroem o lucro:** vendas sem desconto têm margem de 29,5%. Com desconto entre 20% e 40%, a margem cai para -15,3%, e acima de 40% chega a -77,4%. Cerca de 19% das linhas de venda têm prejuízo.
- **Sazonalidade forte:** setembro, novembro e dezembro concentram cerca de 43% da receita anual, enquanto janeiro e fevereiro somam apenas cerca de 7%.
- **Regiões:** West lidera com US$ 725 mil em receita e a melhor margem (14,9%). Central fatura US$ 501 mil, mas tem a menor margem (7,9%).
- **Segmentos:** Consumer representa cerca de 51% da receita, enquanto Home Office tem a maior margem (14,0%).

## 🖼️ Prints

![Produtos e Clientes](<img width="1320" height="752" alt="image" src="https://github.com/user-attachments/assets/565514c4-06b8-4720-bc12-517e0cf18585" />)

![Análise detalhada](<img width="1324" height="759" alt="image" src="https://github.com/user-attachments/assets/18c680b2-996d-4e99-b11f-0bc29e712334" />
)

## ▶️ Como usar

1. Baixe o arquivo `Projeto_Power_BI.pbix` deste repositório.
2. Abra no [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (gratuito).
3. Use os segmentadores para filtrar por ano, categoria e região e navegue entre as páginas pelos botões do relatório.

## 🔭 Próximos passos

- Adicionar metas de vendas e comparar o realizado com o planejado
- Criar uma página de análise de descontos e impacto na margem
- Incluir previsão de vendas com o recurso de forecast

## 👤 Autor

José Carlos de João Miguel e Alves Guerra
[LinkedIn](https://www.linkedin.com/in/josé-carlos-82a35b202/) | [E-mail](mailto:joaomiguel243809@gmail.com)
