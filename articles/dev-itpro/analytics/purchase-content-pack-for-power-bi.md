---
title: "Conteúdo do Power BI de análise de gasto em compras"
description: "Este tópico descreve o que está incluído no conteúdo do Power BI de análise de gastos da compra. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: FrankDahl
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3e42746329b1194c0ce0e2fb5c476742259a5b43
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a>Conteúdo do Power BI de análise de gasto em compras

[!include[banner](../includes/banner.md)]

Este tópico descreve o que está incluído no conteúdo do Microsoft Power BI de **Análise de gastos da compra**. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo do Power BI de **Análise de gastos da compra** foi desenvolvido para ajudar os gerentes de compras e os gerentes responsáveis por orçamentos a ficar de olho nos gastos de compra. Os gerentes podem analisar os gastos de compra das seguintes maneiras:

-   Compra de um ano atrás até agora (por grupo de fornecedor e fornecedores individuais, categoria de compras e produtos individuais e local de fornecedor)
-   Alteração de compra de um ano atrás até agora (por grupo de fornecedor e categoria de compras)

O conteúdo usa dados transacionais de compra e fornece uma visão agregada dos números de compra da empresa e uma repartição dos gastos de compra por fornecedor e produto. Os relatórios destacam as alterações no gasto em compras ao longo do tempo. Portanto, os relatórios podem ser usados para alertar gerentes sobre tendências positivas e negativas de gastos para fornecedores individuais e produtos. Além disso, gráficos mostram gasto em compras para categorias de compras diferentes e grupos de fornecedores. Portanto, a categoria e os gerentes regionais podem usar os gráficos para ajudar a identificar mudanças nos comportamentos de gastos.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017), o conteúdo do Power BI de **Análise de gastos em compra** é mostrado na página **Análise de compra e de gastos** (**Compras** > **Consultas e relatórios** > **Análise de desempenho de compra** > **Análise de compra e de gastos**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI
O conteúdo de Power BI de **Análise de gastos da compra** inclui um relatório que consiste em um grupo de métricas. Estas métricas são visualizadas como gráficos, blocos e tabelas. A tabela a seguir fornece uma visão geral das visualizações.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Página de relatório</th>
<th>Gráficos</th>
<th>Blocos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Venda por fornecedor</td>
<td><ul>
<li>10 principais fornecedores por compra (gráfico de barra empilhada)</li>
<li>Compra total por grupo de fornecedor/país/nome (gráfico de pizza)</li>
<li>Compra por grupo de fornecedor/país/nome (gráfico de coluna)</li>
<li>Compra média por grupo de fornecedor/país/nome (gráfico de coluna)</li>
</ul></td>
<td><ul>
<li>Total da Compra</li>
<li>Crescimento de compra de YOY</li>
<li>Número total de fornecedores</li>
<li>Número total de fornecedores ativos</li>
</ul></td>
</tr>
<tr class="even">
<td>Compra por produto</td>
<td><ul>
<li>Compra por categoria de itens/nome do produto (gráfico de coluna)</li>
<li>Compra total por categoria de itens/nome do produto (gráfico de pizza)</li>
<li>10 principais produtos por compra (gráfico de barra empilhada)</li>
</ul></td>
<td><ul>
<li>Número total de produtos</li>
<li>Porcentagem de produtos ativos total do número total de produtos</li>
<li>Número da contabilidade de produtos para compra de 80%</li>
</ul></td>
</tr>
<tr class="odd">
<td>Compra por período*</td>
<td><ul>
<li>Compra por mês/dia (gráfico de coluna)</li>
<li>Variação de YOY de compra cumulativa (gráfico de cascata)</li>
<li>Crescimento de YOY total da compra (gráfico de coluna)</li>
<li>Demonstrativo de compras (matriz)</li>
</ul></td>
<td><ul>
<li>Crescimento de compra de YOY</li>
<li>Porcentagem de crescimento de compra de YOY</li>
</ul></td>
</tr>
<tr class="even">
<td>Compra por local de fornecedor</td>
<td><ul>
<li>Compra por cidade</li>
<li>Porcentagem de crescimento de YOY de compra</li>
<li>Compra por país</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Análise de gastos de compra por hora</td>
<td><ul>
<li>Ano atual de compra em mês/dia (gráfico de linha)</li>
<li>Compra atual e do último ano (gráfico de linha e coluna)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Análise de gastos de compra por fornecedor</td>
<td><ul>
<li>10 principais porcentagens de compra de fornecedor (funil)</li>
<li>10 principais fornecedores com gasto elevado de YOY</li>
<li>10 principais fornecedores com gasto diminuído de YOY</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\* Compras este ano e no ano passado e crescimento por categoria de compra

## <a name="extending-the-power-bi-content"></a>Aumentando o conteúdo do Power BI
Usando os pacotes de conteúdo disponíveis no Microsoft Dynamics Lifecycle Services (LCS), você pode fornecer grande análise às pessoas que não acessam o Microsoft Dynamics 365. Você pode modificar esses pacotes de conteúdo para que eles incluam outros relatórios ou imagens e, em seguida, publique os pacotes de conteúdo no locatário do Power BI.com para análise. 

Você pode encontrar o conteúdo do Power BI de **Análise de gastos da compra** na biblioteca de ativos compartilhados no LCS. Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md). Para ver uma demonstração que mostra como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

Certifique-se de baixar o conteúdo de **Análise de gastos da compra** que se aplica à versão do Dynamics 365 que você está usando.

> [!NOTE]
> Se você estiver usando o Microsoft Dynamics 365 for Operations versão 1611, o KB 4011327 é um pré-requisito para este conteúdo de Power BI. Depois de iniciar sessão no LCS, você pode acessar o KB em https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="data-model-and-entities"></a>Modelo de dados e entidades
Os seguintes dados são usados para preencher as páginas de relatório no conteúdo do Power BI **Análise de gastos da compra**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para obter mais informações, consulte [Visão geral da integração do Power BI com a loja Entidade](power-bi-integration-entity-store.md).

As medidas agregadas neste conteúdo são o subconjunto de medidas agregadas que estavam disponíveis no Cubo de Compras no Microsoft Dynamics AX 2012 e no Microsoft Dynamics AX 2012 R3. Para preparar as medidas agregadas do cubo na loja Entidade, você deve torná-las implementáveis. Para obter mais informações, consulte o procedimento sobre como preparar medidas agregadas na loja Entidade em [Visão geral da integração do Power BI com a loja Entidade](power-bi-integration-entity-store.md). As principais medidas agregadas a seguir estão disponíveis diretamente nas entidade de linhas de fatura e são usadas como base do conteúdo.

| Entidade        | Principais medidas agregadas | Fonte de dados                                 | Campo              | descrição                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Linhas da fatura | Compra                   | VendInvoiceTrans                            | SUM(LineAmountMST) | O valor na moeda contábil. |

A tabela a seguir mostra as principais medidas no conteúdo que são calculadas a partir da entidade de linhas da fatura.

| Medição               | Cálculo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Ano atual de compra | Ano atual de compra = SUM('Invoice lines'\[Purchase\])                                            |
| Compras do ano passado    | Compras do último ano = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\])) |
| Crescimento de compra de YOY   | Crescimento de compra de YOY = \[Purchase current year\] – \[Purchase last year\]                            |

As principais dimensões a seguir no conteúdo são usadas como filtros para cortar as medidas agregadas, para que você possa alcançar mais granularidade e uma introspecção analítica mais profunda.

| Entidade                 | Exemplos de atributos                                |
|------------------------|-------------------------------------------------------|
| Fornecedores                | Grupos de fornecedores, país ou regiões do fornecedor, nome do fornecedor |
| Produtos               | Número do produto, nome do produto, nome do grupo de item        |
| Categorias de compras | Categoria de compras, nomes da categoria de compras      |
| Entidades legais         | Nome da entidade legal                                     |
| Datas                  | Datas, Compensação anual                                    |

Por padrão, o conteúdo exibe dados do ano atual. Entretanto, poderá modificar o filtro de data na seção filtros de relatório. Você também pode alterar o filtro da empresa.

