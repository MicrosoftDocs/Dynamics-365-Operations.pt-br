---
title: "Conteúdo de Power BI de desempenho de lucratividade e vendas"
description: "Este tópico descreve o que está incluso no Dynamics 365 para Operações - Pacote de conteúdo de desempenho de lucratividade e vendas para o Microsoft Power BI. Ele explica como acessar os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo."
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

# <a name="sales-and-profitability-performance-power-bi-content"></a>Conteúdo de Power BI de desempenho de lucratividade e vendas

Este tópico descreve o que está incluso no Dynamics 365 para Operações - Pacote de conteúdo de desempenho de lucratividade e vendas para o Microsoft Power BI. Ele explica como acessar os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

<a name="overview"></a>Visão Geral
--------

Este pacote de conteúdo foi criado para os gerentes de vendas monitorarem as principais métricas de venda de receita, lucro bruto, e margens de lucro. Ele usa os dados transacionais de vendas do Dynamics 365 para Operações e fornece uma visão agregada das imagens de vendas de toda a empresa e um detalhamento do desempenho das vendas para clientes e produtos. Ao realçar as alterações no crescimento da receita e do lucro no decorrer do tempo, os relatórios podem ser usados para alertar os gerentes sobre tendências positivas e negativas para clientes e produtos individuais. Os gerentes regionais e de categoria acharão útil ter gráficos que comparam a receita e a lucratividade de diferentes categorias de produtos e grupos de clientes entre si para destacar os retardatários e líderes. Um relatório abrangente que destaca a receita individual do cliente em relação à margem de lucro oferece aos gerentes de conta uma fundação baseada em dados para afinar seus esforços de marketing e vendas com cada perfil respectivo do cliente. O pacote de conteúdo de desempenho de lucratividade e vendas permite que os gerentes de vendas analisam o desempenho das vendas por:

-   Receita, anual (por grupo de clientes e clientes individuais, por categorias de venda, por produtos individuais e por geografias)
-   Alteração de receita, ano a ano (por regiões de cliente e categorias de venda)

A lucratividade pode ser analisada por:

-   Lucro bruto e margem de lucro (por grupos de clientes e categorias de venda de produtos)
-   Alteração de lucro bruto, ano após ano
-   Lucratividade de cliente (por receita versus margem bruta)

## <a name="accessing-the-content-pack"></a>Acessando o pacote de conteúdo
O pacote de conteúdo do Power BI para desempenho de lucratividade e vendas é publicado como um ativo de implementação no Lifecycle Services (LCS) e pode ser acessado pelo Dynamics 365 para Operações. Para obter mais informações sobre como acessar e iniciar os relatórios do Power BI, consulte [conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md).

## <a name="metrics-included-in-the-content-pack"></a>Medidor incluído no pacote de conteúdo
O pacote de conteúdo inclui um relatório que consiste de um conjunto de métricas visualizadas como gráficos, blocos e tabelas. A tabela a seguir fornece uma visão geral das visualizações no pacote de conteúdo.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Página de relatório**        | **Gráficos**                                 | **Blocos**                                               |
| Receita por cliente    | 10 melhores clientes por receita                | Receita total                                           |
|                        | Receita total por grupo de clientes            | Crescimento de receita de YOY                                      |
|                        | Receita média do cliente por grupo de clientes | Margem bruta                                            |
|                        | Receite e lucro bruto por grupo de clientes   |                                                         |
| Receita por produto     | Receita e lucro bruto por categoria de vendas   | Total \# de produtos                                    |
|                        | 10 melhores produtos por receita                 | Número total de produtos ativos e percentual do total |
|                        | Receita total por categoria de vendas            | Número da contabilidade de produtos para receita de 80%           |
| Receita por período\*    | Receita por mês                           | Crescimento de receita de YOY                                      |
|                        | Variação de receita à direita, YOY             | % de crescimento de receita de YOY                                    |
|                        | Variação total de vendas por região do cliente    |                                                         |
| Receita por localização    | Receita de vendas por cidade                      |                                                         |
|                        | % de crescimento de receita de YOY                       |                                                         |
|                        | Receita de vendas por região                    |                                                         |
| Lucratividade de cliente | Margem bruta versus receita, por cliente   | Lucro bruto, margem bruta, crescimento de receita de YOY          |
| Análise de lucratividade | Receita e lucro bruto por mês          |                                                         |
|                        | 15 melhores clientes por margem bruta           |                                                         |
|                        | Lucro bruto por mês, YOY                 |                                                         |

\* Receita este ano e último ano, e crescimento por categoria de vendas.

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados do Dynamics 365 para Operações são usados para preencher o relatório no pacote de conteúdo de desempenho de lucratividade e vendas. Isso é representado como medições agregadas que são preparadas na loja Entidade, que é um banco de dados Microsoft SQL otimizado para análise. Leia mais sobre isso no blog [integração do Power BI com a loja Entidade no Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). As medidas agregadas neste pacote de conteúdo são o subconjunto de medidas agregadas que estavam disponíveis no Sales Cubo no Dynamics AX 2012 e AX 2012 R3. Para preparar as medidas agregadas do cubo na loja Entidade, você devem torná-las implementáveis. Para obter mais informações, consulte o procedimento sobre como preparar medidas agregadas na loja Entidade no blog [integração do Power BI com a loja Entidade no Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). As principais medidas agregadas a seguir da entidade Linhas de fatura são usadas como base do pacote de conteúdo.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entidade**    | **Principais medidas agregadas**               | **Fonte de dados para o Dynamics 365 para Operações** | **Campo**                                    | **Descrição**                          |
| Linhas da fatura | Receita                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Valor em moeda contábil            |
|               | Custo dos produtos vendidos                           | InventTrans                                     | SUM(CostAmountPosted + CostAmountAdjustment) | Valor de custo + ajuste                 |
|               | Valor da linha de comissão - moeda contábil | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Valor de comissão na moeda contábil |

A tabela a seguir mostra as principais medidas agregadas da entidade de linhas de fatura que são usadas para criar diversas medidas calculadas no conjunto de dados do pacote de conteúdo.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Medição**       | **Calculado como**                                                                                |
| Lucro bruto      | SUM(Receita – COGS – Comissão – Imposto (incluído no valor de linha de fatura de cliente))          |
| Margem bruta      | SUM(Lucro bruto / (Receita - Imposto (incluído no valor de linha de fatura de cliente)))             |
| Receita no ano passado | Receita no ano passado = CALCULATE(SUM('Linhas de fatura'\[Receita\]), SAMEPERIODLASTYEAR(Datas\[Data\]) |

As principais dimensões a seguir **Cubo de vendas** são usadas como filtros para cortar as medidas agregadas para obter uma granularidade maior e uma introspecção analítica mais profunda.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entidade**       | **Exemplos de atributos**                           |
| Clientes        | Grupos de clientes, regiões do cliente, endereço, indústria |
| Produtos         | Número do produto, nome do produto, nome do grupo de item       |
| Categorias de vendas | Nomes de categoria de venda                                 |
| Entidades legais   | Nomes de entidade legal                                   |
| Datas            | Datas                                                |

Por padrão, o pacote de conteúdo exibe dados para o ano civil atual, mas você pode abrir a seção de filtros de relatório e alterar o filtro de data. Você também pode alterar o filtro da empresa.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](..\data-entities\data-entities.md)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](configure-power-bi-integration.md)



