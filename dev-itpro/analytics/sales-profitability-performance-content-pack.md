---
title: "Conteúdo de O power BI de vendas e de desempenho de lucratividade"
description: "Este tópico descreve o que está incluído em dynamics 365 operações - para blocos de conteúdo de vendas e de desempenho da lucratividade do power BI Microsoft. Explica como acessar os relatórios incluídas no bloco de conteúdo e fornece informações sobre o modelo de dados e as entidades que são usados para construir o bloco de conteúdo."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 3e6b48768bb8e69d46f1555d9300f3b878b01ff1
ms.lasthandoff: 03/31/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Conteúdo de O power BI de vendas e de desempenho de lucratividade

Este tópico descreve o que está incluído em dynamics 365 operações - para blocos de conteúdo de vendas e de desempenho da lucratividade do power BI Microsoft. Explica como acessar os relatórios incluídas no bloco de conteúdo e fornece informações sobre o modelo de dados e as entidades que são usados para construir o bloco de conteúdo.

<a name="overview"></a>Visão Geral
--------

Esse bloco de conteúdo foi criado para aos gerentes de venda monitorem métricas chave de venda de receita, lucro bruto, e margens de benefício. Usa os dados transacionais de vendas do 365 para operações, e uma visão agregada de valores comerciais de venda e uma divisão de desempenho de vendas para clientes e produtos. Realçando alterações na receita e o crescimento de lucros no tempo, relatórios pode ser usado para alertar gerentes sobre tendências positivas e negativos para clientes individuais e produtos. A categoria e gerentes regionais localizar-o-9&z útil ter os gráficos que comparam a receita e a lucratividade de categorias e de cliente de produtos diferentes entre si agrupa se escolher retardatários e tracejados. Um relatório que plote abrangente receita de cliente individual na margem de lucro oferece a gerentes de uma conta como dados- voltada afinar os esforços de vendas e marketing perfil do respectivo cada cliente. Bloco de conteúdo de vendas e de desempenho de lucratividade habilita gerentes de venda para analisar pelo desempenho de vendas:

-   Receita, anual (por grupo de clientes e do indivíduo de clientes, por categorias de venda, e para produtos individuais e por geografias)
-   Alteração de receita, ano (por ano após regiões do cliente e de venda por categorias)

A lucratividade podem ser analisados por:

-   Lucro bruto e margem de lucro (categorias por grupos de clientes e de venda de produtos)
-   Alteração lucro bruto, ano após ano
-   Lucratividade de cliente (por receita na margem bruta)

## <a name="accessing-the-content-pack"></a>Acessando o bloco de conteúdo
Bloco de conteúdo do power BI de vendas e de desempenho de lucratividade for publicado como um ativo de implementação do ciclo de vida de serviço a (LCS) e pode ser acessado do 365 para as operações. Para obter mais informações sobre como acessar e iniciar relatórios de O power BI, consulte [conteúdo de O power BI em LCS Microsoft e seus parceiros (power-bi-content-microsoft-partners.md]).

## <a name="metrics-included-in-the-content-pack"></a>Medidor incluído no bloco de conteúdo
Bloco de conteúdo inclui um relatório que consiste em um conjunto de metro visualizado como gráficos, caixas, e tabelas. A seguinte tabela fornece uma visão geral de visualisations no bloco de conteúdo.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| ** ** Página de relatório        | **Charts**                                 | ** Quadros **                                               |
| Receita por cliente    | Clientes de 10 melhores por receita                | Receita total                                           |
|                        | Receita total por grupo de clientes            | Crescimento de receita de YOY                                      |
|                        | Receita de média cliente por grupo de clientes | Margem bruta                                            |
|                        | Receita e lucro bruto por grupo de clientes   |                                                         |
| Subproduto de receita     | Receita e lucro bruto por categoria de vendas   | Total do produto \#                                    |
|                        | Produtos a parte superior 10 por receita                 | Número total de produto ativos e percentual total |
|                        | Receita total de venda por categoria            | Número na conta receita de 80%           |
| Receita do período\*    | Receita por mês                           | Crescimento de receita de YOY                                      |
|                        | Variação à direita de receita, YOY             | Crescimento % de receita de YOY                                    |
|                        | Variação total de vendas por região do cliente    |                                                         |
| Receita por local    | Receita por cidade de vendas                      |                                                         |
|                        | Crescimento % de receita de YOY                       |                                                         |
|                        | Receita de vendas por região                    |                                                         |
| Lucratividade de cliente | Margem bruta a receita, por cliente   | Lucro bruto, margem bruta, crescimento de receita de YOY          |
| Análise de lucratividade | Receita e lucro bruto do mês          |                                                         |
|                        | Clientes de 15 melhores margem bruta por           |                                                         |
|                        | Lucro bruto por mês, YOY                 |                                                         |

receita\* esta e no ano passado e crescimento, por categoria de vendas.

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
O dynamics 365 para dados de operações é usado para popular o relatório no bloco de conteúdo de vendas e de desempenho de lucratividade. Isso é apresentada como as medições agregadas que forem preparadas na entidade, um base de dados Microsoft SQL otimizada para análise. Ler mais sobre ela em [blog integração do POWER BI com o armazenamento de entidade em dynamics] (https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Medidas agregadas esse bloco de conteúdo são o subconjunto de medições que estavam agregadas disponíveis no cubo de vendas no dynamics AX 2012 e o AX 2012 R3. Para preparar as medições de cubo agregadas na entidade é necessário deployable fazê-las. Para obter mais informações, consulte o procedimento sobre como preparar medições agregadas na entidade em [blog integração do POWER BI com o armazenamento de entidade em dynamics] (https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Estas medições agregação de chave de entidade linhas de nota fiscal são usadas como base de blocos de conteúdo.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entity**    | ** Medições agregadas principais **               | ** Fonte de dados para dynamics 365 para operações ** | **Field**                                    | **Description**                          |
| Linhas da fatura | Receita                                      | CustInvoiceTrans                                | SUM (LineAmountMST)                           | Valor em moeda contábil            |
|               | Custo dos produtos vendidos                           | InventTrans                                     | SUM (CostAmountPosted + CostAmountAdjustment) | Valor de custo previsto + ajuste                 |
|               | Valor de linha de comissão contábil – a moeda | CustInvoiceTrans                                | SUM (CommissAmountMST)                        | Valor da comissão em moeda contábil |

A tabela mostra medições agregadas de linhas principais entidade de nota fiscal são usadas para criar diversas medidas calculadas no conjunto de dados de conteúdo do bloco.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Measure**       | ** Calculado como **                                                                                |
| Lucro bruto      | (Receita – SUM COGS – comissão impostos – (valor incluídos na linha de nota fiscal de cliente))          |
| Margem bruta      | SUM (lucro bruto (/receita - vendas incluídos na linha (valor da nota fiscal de cliente)))             |
| Receita no ano passado | Receita no ano passado CALCULA = (SUM 'receita (\]), SAMEPERIODLASTYEAR de lines'entity_PLACEHOLDER \ [data de faturamento (\]\[datas) |

As seguintes dimensões principais em ** cubo vendas ** são usadas como os filtros para cortar medições agregadas para obter a granularidade maior e uma introspecções analíticas mais profundas.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entity**       | ** Exemplos de atributos **                           |
| Clientes        | Grupos de clientes, regiões do cliente, endereço, indústria |
| Produtos         | Número do produto, nome do produto, nome de item       |
| Categorias de vendas | Nomes de categoria de vendas                                 |
| Entidades legais   | Nomes de entidade legal                                   |
| Datas            | Datas                                                |

Por padrão, o bloco de conteúdo exibe dados o ano civil atual, mas você pode abrir a seção de filtros e de relatório alterar o filtro de data. Você também pode alterar o filtro de empresa.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](..\data-entities\data-entities.md)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](configure-power-bi-integration.md)



