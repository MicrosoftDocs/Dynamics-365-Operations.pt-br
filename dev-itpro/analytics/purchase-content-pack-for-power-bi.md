---
title: "Conteúdo de O power BI de teste de produção de compra"
description: "Este tópico descreve o que está incluído no bloco de conteúdo de teste de produção de compra do power BI Microsoft. Explica como acessar os relatórios que são incluídos no bloco de conteúdo, além fornece informações sobre o modelo de dados e as entidades que são usados para construir o bloco de conteúdo."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-12-30 09 - 40 - 51
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
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 8cb928cbf1316e63a8c7de833587168cd36a455c
ms.lasthandoff: 03/29/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Conteúdo de O power BI de teste de produção de compra

Este tópico descreve o que está incluído no bloco de conteúdo de teste de produção de compra do power BI Microsoft. Explica como acessar os relatórios que são incluídos no bloco de conteúdo, além fornece informações sobre o modelo de dados e as entidades que são usados para construir o bloco de conteúdo.

<a name="overview"></a>Visão Geral
--------

Bloco de conteúdo de teste de produção de compra do power BI Microsoft foi criado para os gerentes de compras e os gerentes responsáveis por orçamentos. Criado de ajudá-los a manter um olho de gastos de compra. Usa os dados transacionais de compra do Microsoft Dynamics 365 para operações, e uma visão agregada de valores comerciais de compra e uma divisão de gastos de compra por fornecedor e pelo produto. Destaque o relatórios em que compra muda gasta no tempo. Portanto, podem ser usados para alertar gerentes sobre tendências positivas e negativos de gastos para fornecedores individuais e produtos. Gráficos mostram gasto de compra para categorias de compras e diferentes grupos de fornecedores. A categoria e os gerentes podem regionais acredita que é útil usar esses elementos gráficos para ajudar a identificar alterações no comportamento de gastos. Bloco de conteúdo deixar gerentes de compra e os gerentes responsáveis por orçamentos a compra que analisam gastam das seguintes maneiras:

-   compra anual (por fornecedores do grupo e do indivíduo fornecedor, por produtos a categoria de compras e pessoa, local e por fornecedor)
-   Alteração ano após de compra (ano por grupo de fornecedores e a categoria de compras)

## <a name="accessing-the-content-pack"></a>Acessando o bloco de conteúdo
Bloco de conteúdo de teste de produção de compra for publicado como um ativo de implementação do Microsoft Dynamics lifecycle de serviço a (LCS) e pode ser acessado do Microsoft Dynamics 365 para as operações. Para obter mais informações sobre como acessar e abra relatórios de O power BI, consulte [conteúdo de O power BI em LCS Microsoft e seus parceiros (power-bi-content-microsoft-partners.md]).

## <a name="metrics-that-are-included-in-the-content-pack"></a>Medidor incluído no bloco de conteúdo
Bloco de conteúdo de teste de produção de compra contém um relatório que consiste em um conjunto de metro. Este são métricas visualizado como gráficos, caixas, e tabelas. A seguinte tabela fornece uma visão geral do bloco visualizações de conteúdo.

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
<th>Tiles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Compra por fornecedor</td>
<td><ul>
<li>Fornecedores a parte superior 10 por compra (gráfico de barras empilhado)</li>
<li>Compra total por grupo de fornecedores/país/nome (gráfico de pizza)</li>
<li>Compras por grupo de fornecedores/país/nome (gráfico de coluna)</li>
<li>Compra médio por grupo de fornecedores/país/nome (gráfico de coluna)</li>
</ul></td>
<td><ul>
<li>Total da Compra</li>
<li>Crescimento de compra de YOY</li>
<li>Total # fornecedores</li>
<li>Total de ativos # fornecedores</li>
</ul></td>
</tr>
<tr class="even">
<td>Subproduto de compra</td>
<td><ul>
<li>Compra por categoria de itens/nome do produto (gráfico de coluna)</li>
<li>Compra total por categoria de itens/nome do produto (gráfico de pizza)</li>
<li>Produtos de 10 melhores (por compra gráfico de barras empilhado)</li>
</ul></td>
<td><ul>
<li>Total # de produtos</li>
<li>Porcentagem total de produto ativo de # total de produtos</li>
<li>Número de produtos que para a compra de 80%</li>
</ul></td>
</tr>
<tr class="odd">
<td>Por compra period*</td>
<td><ul>
<li>Compra em (dia/mês gráfico de coluna)</li>
<li>Variação cumulativo de compra (YOY gráfico de cachoeira)</li>
<li>Crescimento total da compra (YOY gráfico de coluna)</li>
<li>Demonstrativo de compras (matriz)</li>
</ul></td>
<td><ul>
<li>Crescimento de compra de YOY</li>
<li>Crescimento % de compra de YOY</li>
</ul></td>
</tr>
<tr class="even">
<td>Local de compra por fornecedor</td>
<td><ul>
<li>Compra por cidade</li>
<li>Crescimento % de compra YOY</li>
<li>Compra por país</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Análise de custos da compra no momento</td>
<td><ul>
<li>O ano corrente de compra em (dia/mês gráfico de linhas)</li>
<li>Atual de compra e no ano passado gráfico (linha e de coluna)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Análise de gastos de compra por fornecedor</td>
<td><ul>
<li>Compra % de fornecedor em 10 melhores (compra de funil)</li>
<li>Fornecedores a parte superior 10 com o YOY de gasto acumulado</li>
<li>Fornecedores a parte superior 10 com o YOY de gasto diminuído</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

compra\* este ano\* e no ano passado e crescimento, por categoria de compras

## <a name="data-model-and-entities"></a>Modelo de dados e entidades
O dynamics 365 para dados de operações é usado para o relatório no bloco de conteúdo de teste de produção de compra. Esses dados são representadas como as medições agregadas que forem preparadas na entidade, um base de dados Microsoft SQL que é otimizada para análise. Para obter mais informações sobre o armazenamento de entidade, consulte [integração do POWER BI com o armazenamento de entidade em dynamics] (postagem de blog de https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Medidas agregadas esse bloco de conteúdo são o subconjunto de medições que estavam agregadas disponíveis no cubo de compra no Microsoft Dynamics AX 2012 e Microsoft Dynamics 365 para operações 2012 R3. Para preparar as medições de cubo agregadas na entidade, você deve deployable fazê-las. Para obter mais informações, consulte o procedimento para preparar medições agregadas na entidade em [integração do POWER BI com o armazenamento de entidade em dynamics] (postagem de blog de https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Estas medições agregação de chave disponíveis diretamente das linhas da entidade e são usadas como base de blocos de conteúdo.

| Entidade        | Key aggregate measurements | Fonte de dados para dynamics 365 para operações | Campo              | descrição                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Linhas da fatura | Compra                   | VendInvoiceTrans                            | SUM (LineAmountMST) | O valor na moeda contábil |

A tabela mostra medições principais que são calculadas no bloco de conteúdo das linhas da entidade.

| Medição               | Cálculo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| O ano corrente de compra | O ano corrente de compra SUM = ('compra do\]lines'entity_PLACEHOLDER \ [de nota fiscal)                                            |
| Compra no ano passado    | A compra no ano passado = CALCULA ('compra SUM (\]), SAMEPERIODLASTYEAR de lines'entity_PLACEHOLDER \ [data de faturamento (\]\[datas)) |
| Crescimento de compra de YOY   | Crescimento de compra de YOY = ano atual\] de compra do \[– compra no ano passado\]\[                            |

As seguintes dimensões principais no bloco de conteúdo são usadas como os filtros para cortar medições agregadas, para que você possa obter mais introspecções analíticas granularidade e mais profundas.

| Entidade                 | Exemplos de atributos                                |
|------------------------|-------------------------------------------------------|
| Fornecedores                | Grupos de fornecedores, país de fornecedor ou regiões, nome do fornecedor |
| Produtos               | Número do produto, nome do produto, nome de item        |
| Categorias de compras | Categoria de compras, nomes da categoria de compras      |
| Entidades legais         | Nome da entidade legal                                     |
| Datas                  | Datas, compensação do ano                                    |

Por padrão, o bloco de conteúdo exibe dados o ano civil atual. Entretanto, poderá modificar o filtro de data na seção filtros de relatório. Você também pode alterar o filtro de empresa.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](..\data-entities\data-entities.md)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](configure-power-bi-integration.md)



