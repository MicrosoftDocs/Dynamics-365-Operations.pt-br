---
title: Conteúdo de desempenho de vendas e de lucratividade do Power BI
description: Este tópico descreve o que está incluído no conteúdo do Power BI Desempenho de vendas e lucratividade.
author: ShylaThompson
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesProfitabilityPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9ec9ef5f4abf898100c670b1ca1cc845d6ebeeea36f21cdda3a9b7d3f1027d4e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725201"
---
# <a name="sales-and-profitability-performance-power-bi-content"></a>Conteúdo de desempenho de vendas e de lucratividade do Power BI

[!include [banner](../includes/banner.md)]

Este tópico descreve o que está incluído no conteúdo **Desempenho de vendas e lucratividade** do Microsoft Power BI. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que são usados para criar o conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo do Power BI **Desempenho de vendas e lucratividade** foi criado para que os gerentes de vendas possam monitorar as principais métricas de vendas de receita, lucro bruto e margens de lucro. Ele usa dados transacionais de vendas e fornece uma visão agregada dos números de vendas da empresa e uma quebra do desempenho de vendas para clientes e produtos.

Os relatórios destacam as mudanças na receita e no crescimento dos lucros ao longo do tempo. Portanto, os relatórios podem ser usados para alertar os gerentes sobre tendências positivas e negativas para clientes e produtos individuais. Além disso, os gráficos comparam a receita e a rentabilidade de diferentes categorias de produtos e grupos de clientes entre si. Portanto, a categoria e os gerentes regionais podem identificar retardatários e líderes. Por fim, um relatório abrangente representa a receita de um cliente individual em relação à margem de lucro. Portanto, os gerentes de contas têm uma base de dados que podem usar para ajustar suas iniciativas de vendas e marketing para o perfil de cada cliente.

O conteúdo **Desempenho de lucratividade e vendas** permite aos gerentes de vendas analisar o desempenho das vendas das seguintes maneiras:

- Receita, anual (por grupo de clientes e clientes individuais, por categorias de venda, por produtos individuais e por geografias)
- Alteração de receita, ano a ano (por regiões de cliente e categorias de venda)

A lucratividade pode ser analisado das seguintes formas:

- Lucro bruto e margem de lucro (por grupos de clientes e categorias de venda de produtos)
- Alteração de lucro bruto, ano após ano
- Lucratividade de cliente (por receita versus margem bruta)

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
O conteúdo do Power BI **Desempenho de vendas e de lucratividade** é exibido na página **Desempenho de vendas e de lucratividade** (**Vendas e marketing** \> **Consultas e relatórios** \> **Análise de desempenho de vendas** \> **Desempenho de vendas e de lucratividade**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI
O conteúdo do Power BI **Desempenho de lucratividade** e vendas inclui um relatório que consiste em um conjunto de métricas. Estas métricas são visualizadas como gráficos, blocos e tabelas. A tabela a seguir fornece uma visão geral das visualizações no conteúdo.

| Página de relatório            | Gráficos                                     | Blocos                                                   |
|------------------------|--------------------------------------------|---------------------------------------------------------|
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
Os seguintes dados são usados para preencher o relatório no conteúdo do Power BI **Desempenho de lucratividade e vendas**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para obter mais informações, consulte [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).

As medidas agregadas neste conteúdo são o subconjunto de medidas agregadas que estavam disponíveis no Cubo de Vendas no Microsoft Dynamics AX 2012 e no Microsoft Dynamics AX 2012 R3. Para preparar as medidas agregadas do cubo na loja Entidade, você deve torná-las implementáveis. Para obter mais informações, consulte o procedimento sobre como preparar medidas agregadas na loja Entidade na postagem do blog [Integração do Power BI com a loja Entidade no Dynamics](/archive/blogs/dynamicsaxbi/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update).

As principais medidas agregadas a seguir da entidade Linhas de fatura são usadas como base do conteúdo.

| Entidade        | Principais medidas agregadas                   | Fonte de dados para Dynamics 365 | Campo                                        | descrição                                       |
|---------------|----------------------------------------------|------------------------------|----------------------------------------------|---------------------------------------------------|
| Linhas da fatura | Receita                                      | CustInvoiceTrans             | SUM(LineAmountMST)                           | O valor na moeda contábil.            |
|               | Custo dos produtos vendidos                           | InventTrans                  | SUM(CostAmountPosted + CostAmountAdjustment) | A soma o valor de custo e o ajuste.    |
|               | Valor da linha de comissão - moeda contábil | CustInvoiceTrans             | SUM(CommissAmountMST)                        | O valor da comissão na moeda de contabilidade. |

A tabela a seguir mostra as principais medidas agregadas da entidade de linhas de fatura que são usadas para criar diversas medidas calculadas no conjunto de dados do conteúdo.

| Medição           | Cálculo                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| Lucro bruto      | SUM(Receita – COGS – Comissão – Imposto (incluído no valor de linha de fatura de cliente))          |
| Margem bruta      | SUM(Lucro bruto / (Receita - Imposto (incluído no valor de linha de fatura de cliente)))             |
| Receita no ano passado | Receita no ano passado = CALCULATE(SUM('Linhas de fatura'\[Receita\]), SAMEPERIODLASTYEAR(Datas\[Data\]) |

As dimensões-chave a seguir no Cubo de Vendas são usadas como filtros para cortar as medidas agregadas, para que você possa obter maior granularidade e obter informações analíticas mais profundas.

| Entidade           | Exemplos de atributos                               |
|------------------|------------------------------------------------------|
| Clientes        | Grupos de clientes, regiões do cliente, endereço, indústria |
| Produtos         | Número do produto, nome do produto, nome do grupo de item       |
| Categorias de vendas | Nomes de categoria de venda                                 |
| Entidades legais   | Nomes de entidade legal                                   |
| Datas            | Datas                                                |

Por padrão, o conteúdo exibe dados do ano atual. Entretanto, poderá modificar o filtro de data na seção filtros de relatório. Você também pode alterar o filtro da empresa.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]