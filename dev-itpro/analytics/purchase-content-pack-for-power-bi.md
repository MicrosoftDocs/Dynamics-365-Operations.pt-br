---
title: "Conteúdo do Power BI de análise de gasto em compras"
description: "Este tópico descreve o que está incluído no pacote de conteúdo de analise de gasto em compras para Microsoft Power BI. Ele explica como acessar os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o pacote de conteúdo."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d392b88942f4b7d7365b000df1cd69809060b910
ms.openlocfilehash: e39b1677038037cd91cfad8d104d0130bc20fb9b
ms.contentlocale: pt-br
ms.lasthandoff: 04/26/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Conteúdo do Power BI de análise de gasto em compras

[!include[banner](../includes/banner.md)]


Este tópico descreve o que está incluído no pacote de conteúdo de analise de gasto em compras para Microsoft Power BI. Ele explica como acessar os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o pacote de conteúdo.

<a name="overview"></a>Visão Geral
--------

O bloco de conteúdo de teste de gasto em compras do Microsoft Power BI foi criado para os gerentes de compras e os gerentes responsáveis por orçamentos. Criado para ajudá-los a manter um olho nos gastos de compra. Ele usa os dados transacionais de compra do Microsoft Dynamics 365 for Operations e fornece uma visão agregada das imagens de compras de toda a empresa e um detalhamento do gasto em compras por fornecedor e produto. Os relatórios destacam as alterações no gasto em compras ao longo do tempo. Portanto, podem ser usados para alertar gerentes sobre tendências positivas e negativas de gastos para fornecedores individuais e produtos. Gráficos mostram gasto em compras para categorias de compras diferentes e grupos de fornecedores. As categorias e gerentes regionais podem achar ele útil para usar gráficos e ajudar a identificar alterações no comportamento de gasto. O pacote de conteúdo permite que os gerentes de compra e gerentes responsáveis por orçamentos analisem gastos de compra nas formas a seguir:

-   Compra de um ano atrás até agora (por grupo de fornecedor e fornecedores individuais, categoria de compras e produtos individuais e local de fornecedor)
-   Alteração de compra de um ano atrás até agora (por grupo de fornecedor e categoria de compras)

## <a name="accessing-the-content-pack"></a>Acessando o pacote de conteúdo
O pacote de conteúdo da análise de gastos de compra é publicado como um ativo de implementação no Microsoft Dynamics Lifecycle Services (LCS) e pode ser acessado pelo Microsoft Dynamics 365 for Operations. Para obter mais informações sobre como acessar e iniciar os relatórios do Power BI, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md).
Observação: KB 4011327 é um pré-requisito para o conteúdo do Power BI. Após entrar no Lifecycle Services, você pode acessar a Base de Dados de Conhecimento: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="metrics-that-are-included-in-the-content-pack"></a>Métricas incluídas no pacote de conteúdo
O pacote de conteúdo da análise de gastos de compra inclui um relatório que consiste em um grupo de métricas. Estas métricas são visualizadas como gráficos, blocos e tabelas. A tabela a seguir fornece uma visão geral das visualizações no pacote de conteúdo.

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

## <a name="data-model-and-entities"></a>Modelo de dados e entidades
Os dados do Microsoft Dynamics 365 for Operations são usados para o relatório no pacote de conteúdo de análise de gasto em compras. Esses dados são representados como medições agregadas que são preparadas na loja Entidade, que é um banco de dados Microsoft SQL otimizado para análise. Para obter mais informações sobre a loja Entidade, consulte a postagem do blog [Integração do Power BI com Loja de entidade no Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). As medidas agregadas neste pacote de conteúdo são o subconjunto de medidas agregadas que estavam disponíveis no Cubo de Compras no Microsoft Dynamics AX 2012 e no Microsoft Dynamics AX 2012 R3. Para preparar as medidas agregadas do cubo na loja Entidade, você deve torná-las implementáveis. Para obter mais informações, consulte o procedimento sobre como preparar medidas agregadas na loja Entidade na postagem do blog [Integração do Power BI com a loja Entidade no Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). As principais medidas agregadas a seguir estão disponíveis diretamente nas entidade de linhas de fatura e são usadas como base do pacote de conteúdo.

| Entidade        | Principais medidas agregadas | Fonte de dados para o Dynamics 365 para Operações | Campo              | descrição                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Linhas da fatura | Compra                   | VendInvoiceTrans                            | SUM(LineAmountMST) | O valor na moeda contábil |

A tabela a seguir mostra as medidas que podem ser calculadas no pacote de conteúdo da entidade de linhas da fatura.

| Medição               | Cálculo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Ano atual de compra | Ano atual de compra = SUM('Invoice lines'\[Purchase\])                                            |
| Compras do ano passado    | Compras do último ano = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\])) |
| Crescimento de compra de YOY   | Crescimento de compra de YOY = \[Purchase current year\] – \[Purchase last year\]                            |

As principais dimensões a seguir no pacote de conteúdo são usadas como filtros para cortar as medidas agregadas, para que você possa alcançar mais granularidade e uma introspecção analítica mais profunda.

| Entidade                 | Exemplos de atributos                                |
|------------------------|-------------------------------------------------------|
| Fornecedores                | Grupos de fornecedores, país ou regiões do fornecedor, nome do fornecedor |
| Produtos               | Número do produto, nome do produto, nome do grupo de item        |
| Categorias de compras | Categoria de compras, nomes da categoria de compras      |
| Entidades legais         | Nome da entidade legal                                     |
| Datas                  | Datas, Compensação anual                                    |

Por padrão, o bloco de conteúdo exibe dados do ano atual. Entretanto, poderá modificar o filtro de data na seção filtros de relatório. Você também pode alterar o filtro da empresa.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](..\data-entities\data-entities.md)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](configure-power-bi-integration.md)





