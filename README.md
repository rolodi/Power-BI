DESAFIO 4 - DIO

🔷 Modelagem Dimensional - Star Schema
🎯 Objetivo
Este projeto tem como objetivo a criação de um modelo dimensional em formato estrela (Star Schema), estruturado para análises de vendas, produtos e descontos, com foco na performance de indicadores de vendas ao longo do tempo e por atributos de produto.

🏗️ Estrutura do Modelo
A modelagem segue o padrão de um Data Warehouse com:

Uma tabela fato central: F_Vendas

Diversas tabelas dimensão para enriquecer a análise:
D_Produtos
D_Produtos_Detalhes
D_Descontos
D_Calendario
D_Detalhes

Essa estrutura permite cruzamentos eficientes de dados com alta granularidade, facilitando análises como: descontos por produto, volume de vendas por período, comparação de preços, entre outros.

🧪 Transformações e Modelagem no Power Query
Durante o processo de modelagem, foram aplicadas diversas transformações nos dados originais para preparar o modelo analítico:

Group By (Agrupar por)
Utilizado para agregar valores por produto, mês ou faixa de desconto (ex: média de vendas por produto).
Índice (Index)
Inserido para facilitar ordenações, relacionamentos e controle de chave artificial.
Coluna Condicional
Criada para classificar produtos ou definir faixas de análise, como bandas de desconto e segmentações.
Coluna Personalizada (Custom Column)
Aplicada para criar cálculos intermediários, como margem de lucro, variação entre preço de fabricação e venda, etc.
Transformações adicionais:
Normalização de nomes de colunas
Conversão e formatação de tipos de dados
Remoção de duplicatas
Eliminação de colunas irrelevantes
Divisão de colunas (split)
Mesclagem (merge) entre tabelas relacionadas

📊 Fato: F_Vendas
Contém os registros transacionais de vendas, com campos como:
Date
Country
ID_Produtos
Discount Band
Discounts
Manufacturing Price
IDRelacionamento (chave artificial auxiliar)

🧭 Dimensões
D_Produtos
Contém atributos analíticos como:
Média, mediana, máximo e mínimo do valor de venda

Nome do produto
D_Produtos_Detalhes
Traz detalhes técnicos por produto, como:
Preço de fabricação
Preço de venda
Quantidade vendida

D_Descontos
Responsável por representar as bandas de desconto e respectivos valores médios.

D_Calendario
Dimensão de tempo com granularidade mensal, incluindo:
Data, mês, trimestre, número do mês
Nome do mês

D_Detalhes
Tabela complementar para análises cruzadas com país, produto e calendário.

🧩 Fonte dos Dados
A base de dados foi inicialmente extraída da tabela financials_origem, a qual foi tratada e desnormalizada em múltiplas dimensões para melhorar a eficiência de consulta e clareza analítica.

📈 Benefícios da Modelagem
Permite análises dinâmicas com cruzamento de filtros de tempo, produto e desconto
Estrutura intuitiva para usuários de negócio
Otimização de performance no Power BI via modelagem em estrela
Suporte a indicadores de desempenho como:
Receita bruta
Margem de lucro
Eficácia de campanhas promocionais
